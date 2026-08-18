# Obscura — CDP click and navigation parity

**Upstream commit:** [`6dd1e4e — Fix CDP click submit navigation parity`](https://github.com/h4ckf0r0day/obscura/commit/6dd1e4e65f5b91c58a2bf85d584aadf31f4eab6a)

This contribution is part of the upstream Obscura repository. GitHub attributes the commit to `blockedby`, and its metadata also credits `SGavrl` as co-author.

## The browser-automation gap

CDP clients do not interact with a page through only one path. They evaluate expressions, call functions on remote objects, dispatch input events, await promises, and expect any resulting browser navigation to become visible through the same session.

The missing connection was between JavaScript side effects and the CDP request lifecycle:

- `Runtime.evaluate` did not fully honor `awaitPromise`;
- a click handler could call `preventDefault()` and assign `location.href`, but the resulting pending navigation was not processed after the CDP command;
- DOM event propagation and cancellation behavior differed from browser expectations;
- form actions and repeated query parameters needed more browser-compatible handling.

Individually these look like small compatibility details. Together they determine whether an agent can click a real submit button and observe the page that follows.

## Engineering approach

### 1. Settle promises in `Runtime.evaluate`

The CDP evaluation path became asynchronous and now reads the `awaitPromise` flag. Awaited expressions run through the JavaScript event loop, return settled values when requested by value, and surface promise rejection instead of silently treating it as an ordinary result.

Coverage includes:

- an immediately resolved promise;
- a timer-backed promise;
- an async function;
- a rejected promise.

### 2. Turn JavaScript navigation into page navigation

The page layer gained one explicit operation for consuming pending JavaScript navigation and running it through normal load navigation.

CDP handlers invoke that operation after:

- `Runtime.evaluate`;
- `Runtime.callFunctionOn`;
- click dispatch through the Input domain.

This keeps evaluation, remote-object calls, and synthesized clicks consistent: if page JavaScript changes location, the session advances to the resulting document before the command completes.

### 3. Bring DOM events closer to browser behavior

The JavaScript bootstrap was tightened around the semantics that submission handlers depend on:

- preserve the original `event.target` while an event bubbles;
- track `stopPropagation()` and `stopImmediatePropagation()` separately;
- let `preventDefault()` affect only cancelable events;
- continue propagation independently from default-action cancellation;
- resolve relative form actions against the document URL;
- preserve repeated `URLSearchParams` entries instead of collapsing them into a map.

The navigation operation also updates runtime URL state when it records a pending transition, keeping script-visible state and browser-visible state aligned.

## End-to-end regression

The commit adds a deterministic CDP integration test backed by an ephemeral local HTTP server. The served page contains a real form with a hidden field, textarea, checked checkbox, submit button, and inline click handler.

The test then exercises the same sequence an automation client would use:

1. navigate through CDP;
2. confirm the inline handler exists through `Runtime.evaluate`;
3. obtain the actual button as a remote object;
4. invoke `this.click()` through `Runtime.callFunctionOn`;
5. verify navigation to `/submitted`;
6. verify the encoded form values and resulting document body.

Loopback access remains opt-in through `OBSCURA_ALLOW_PRIVATE_NETWORK`, so the fixture can run locally without weakening the default private-network boundary.

## Why this matters

Agentic browser workflows fail when each layer is "almost" compatible but their side effects do not connect. A DOM click is useful only if its handler runs; an awaited expression is useful only if its promise settles; a location change is useful only if the browser session processes it.

This contribution closes that chain across the JavaScript runtime, DOM model, page lifecycle, CDP Runtime domain, and CDP Input domain—and proves the complete behavior with a browser-level regression rather than isolated mocks alone.
