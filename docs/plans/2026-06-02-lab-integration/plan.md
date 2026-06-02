# Slice 6 plan — lab integration docs

## Task intake
Goal: fill the public Agentic Engineering Lab repo with case studies, workflow/manual docs, a final public-surface review, and a final portfolio report using prior slice evidence and public links.

In scope: requested markdown files under `workflows/`, `case-studies/`, `docs/manual/`, `docs/reviews/`, `docs/final/`, plus root/doc index link updates and repo-local task-package evidence.

Out of scope / do-not-touch: private repos; private URLs/domains/logs/user data; private submodules; automatic GitHub profile changes; upstream ownership claims; forbidden public phrase in public files.

Done state: all required files exist, local links work, safety scans pass or only match safety-rule wording, GitHub/public evidence is recorded, commit/push attempted if safe, final report written to `/tmp/github-portfolio-backlog.vBLiBN/slice-6-lab-integration-report.md`.

Blocking unknowns: exact current GitHub profile values and PR states depend on `gh` availability.

## Repo orientation
Lab repo is a public markdown portfolio hub. Existing files: `README.md`, `case-studies/README.md`, `workflows/README.md`, `docs/README.md`, `docs/audit/github-public-surface-audit.md`, optional public submodules. No root `AGENTS.md` exists in this repo; nearest child AGENTS only inside submodules, which are not edited.

Relevant verification commands: `gh repo view`, `gh pr view`, `gh api user`, `gh user status`; `git diff --check`; local markdown relative-link script; secret/private/overclaim scan over changed lab markdown; `git submodule status`; `git status --short --branch`.

## Reuse discovery
Use prior slice reports in `/tmp/github-portfolio-backlog.vBLiBN/` as evidence. Existing README copy establishes attribution and safety rules. Existing docs indexes should link to new material.

Evidence to reuse:
- Obscura PR `https://github.com/h4ckf0r0day/obscura/pull/195`, state open unless `gh` says otherwise, head commit `5c638945f520d47da367dc04db66abb8460a08e4`.
- Hermes Slice 3: branch `alex/github-portfolio-hermes-attribution`, commit `dc688e32708b5050111d439ea8cdc1fdefc84264`, suggested PR URL.
- Go OpenRouter Slice 4: PR `https://github.com/blockedby/go-openrouter/pull/1`, upstream PR `https://github.com/reVrost/go-openrouter/pull/50`, upstream commit `016ba045a0facdd208102c9f25c8fc9515771e92`, fork commit `8251ecf`, latest commit `ee13834`.
- Linux Slice 5: PR `https://github.com/blockedby/linux-kubuntu-tweaks/pull/1`, branch `portfolio-linux-sanitization`, commit `1e4e70e`, main implementation commit `b28e981`.
- Slice 1: public lab `blockedby/agentic-engineering-lab`, commits `e7938d5`, `2de0a24`.
- Slice 2: pi-codex PR `https://github.com/blockedby/pi-codex/pull/1`, commit `df41d1b`.

## Missing pieces
Add required case studies, workflow docs, manual docs, final review, final report, and update indexes. Record profile current values if available without changing them.

## Plan tasks and dependency graph
Task A — docs authoring and index updates
- Acceptance: required files exist; case studies include requested sections; private-work disclaimer present; exact public evidence links included; indexes link to files.
- Test plan: file existence scan, local markdown link check, content grep for exact URLs/required sections.
- Executor: owner direct (docs-only integration; delegation overhead higher than direct execution).
- Depends on: none.

Task B — public-surface evidence and safety review
- Acceptance: gh evidence recorded where possible; final review lists checked files and blockers/no blockers; safety scan checks secrets/private IPs/private URLs/chat IDs/tokens/cookies/overclaiming/forbidden phrase; false positives documented.
- Test plan: gh commands, scan commands, `git diff --check`, `git submodule status`, `git status`.
- Executor: owner direct; optional auditor if needed.
- Depends on: Task A.

Execution: keep slice whole. No child slices; no implementer dispatch because the task is a bounded docs integration with one verification story and exact prior evidence.

## Execution ledger
- Worktree created at `.worktrees/slice-6-lab-integration` from `origin/main`; `.worktrees/` ignored locally in `.git/info/exclude` because repo did not already ignore it.
