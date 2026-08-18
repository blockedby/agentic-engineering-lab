# Obscura browser runtime — bounded JavaScript execution

**Public evidence:** [`5c63894 — Fix bounded full-load script execution`](https://github.com/blockedby/obscura/commit/5c638945f520d47da367dc04db66abb8460a08e4)

This case study covers work in my public Obscura fork. Obscura itself is an upstream project maintained by `h4ckf0r0day`; the implementation described here is limited to the linked fork commit.

## The failure mode

A browser can report a document as loaded only after it has processed several kinds of JavaScript work: parser-blocking scripts, deferred scripts, async scripts, lifecycle events, and queued event-loop tasks.

The problematic case was deceptively small:

```js
while (true) {}
```

A compact busy loop could monopolize V8 during full-load navigation. An outer asynchronous timeout was not enough because the JavaScript engine itself remained blocked. Navigation could hang before later scripts ran, and simply abandoning the future did not guarantee that the runtime was usable afterward.

## Engineering approach

The change makes bounded execution an explicit runtime property rather than a caller-side hope:

1. **Guard every page script.** Small scripts use the same V8 watchdog as larger scripts, because source length says nothing about execution time.
2. **Bound event-loop execution inside the runtime.** A watchdog uses V8's thread-safe isolate handle to terminate execution when the configured deadline expires.
3. **Recover after termination.** The runtime cancels the termination state and executes a small reset step so later JavaScript can still run.
4. **Use the bounded path during navigation.** Load-event dispatch and page event-loop polling call the guarded runtime methods instead of relying only on outer Tokio timeouts.
5. **Keep the policy configurable.** `OBSCURA_SCRIPT_TIMEOUT_MS` can override the default one-second script deadline while rejecting zero as an invalid bound.

## Regression evidence

The commit adds two complementary levels of proof.

### Runtime recovery test

A focused Rust test:

- starts a compact infinite loop through `execute_script_guarded`;
- requires the call to return within a bounded interval;
- confirms that code before termination ran;
- executes another script afterward;
- verifies that the same runtime remains usable.

This checks both interruption and recovery—the important invariant is not merely "the timeout fired," but "the browser can continue."

### Full-load browser fixture

A local integration fixture combines:

- an inline initializer;
- a compact parser-blocking busy loop;
- a later script that schedules zero-delay work;
- deferred and async scripts;
- full-load navigation with an overall five-second bound.

The test records script invocation order and verifies that every expected script is reached without navigation hanging. The fixture runs through a local ephemeral HTTP listener, keeping the regression deterministic and self-contained.

## Why this matters

Agent-facing browsers routinely encounter third-party JavaScript they do not control. Reliability requires more than wrapping work in a generic timeout: the execution limit must reach the JavaScript engine, termination must be reversible, and the surrounding browser lifecycle must use the bounded API consistently.

The linked commit is a compact example of that pattern: reproduce the engine-level failure, move the bound to the correct layer, recover the runtime, and prove the complete navigation path with deterministic tests.
