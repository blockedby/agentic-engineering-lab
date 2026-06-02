# AI-assisted pull request loop

## Summary

This is the repeatable loop used for the portfolio setup: keep humans accountable for scope and evidence, while using agents for bounded exploration, implementation, review, and reporting.

## Workflow

1. **Intake and constraints** — define the goal, acceptance criteria, do-not-touch boundaries, privacy rules, and expected report path.
2. **Evidence-first discovery** — collect deterministic facts from the repo, GitHub CLI, tests, diffs, and existing docs before asking an LLM to summarize.
3. **Task package** — create a repo-local package with `plan.md`, reports, verification notes, and progress artifacts.
4. **Slice or keep whole** — split only when there are independent ownership or verification stories. Otherwise keep one owner.
5. **Implement in a worktree** — use an isolated branch/worktree when practical; keep primary checkout on `main`.
6. **Verify acceptance** — run narrow checks that directly prove the change, then broader readiness checks before finalizing.
7. **Public-safety pass** — scan for secrets, private URLs/endpoints, user data, overclaiming, and attribution errors.
8. **Report and PR** — commit focused changes, push when safe, open/update a PR, and write a continuation report with evidence and blockers.

## Guardrails

- Agents do not own production claims; the slice owner decides done-state from evidence.
- Public portfolio docs must not include private repo links, raw logs, credentials, private endpoints, chat IDs, tokens, cookies, or real user data.
- Fork work is described as fork work, contribution work, or changes in a fork, with upstream maintainers attributed.

## Verification

A PR is ready when the task package maps acceptance criteria to fresh checks, `git diff --check` passes, local markdown links resolve, and the public-safety scan has no unresolved findings.
