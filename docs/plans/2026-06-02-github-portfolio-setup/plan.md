# Slice 1 plan — Profile + portfolio hub + public-surface scaffolding

## Task intake
Goal: create the public `blockedby/agentic-engineering-lab` hub and keep the `blockedby/blockedby` profile README pointing only to real public targets.
In scope: hub README/index scaffold, public-only submodules, audit report copy, task package artifacts, profile README safety/professionalism check.
Out of scope: private repo publication, case-study body writing beyond placeholders, modifying private repos, publishing raw local logs/artifacts.
Done state: lab repo exists locally and remotely public if auth permits; scaffold and README meet Slice 1 acceptance; profile README has no broken lab link.
Blocking unknowns: none currently; GitHub repo creation succeeded if `gh repo view` confirms public visibility.

## Repo orientation
- Profile repo: `/home/kcnc/code/blockedby`, branch `main`, dirty untracked `profile-check.png` that must not be committed.
- Lab repo: `/home/kcnc/code/agentic-engineering-lab`, newly created via `gh repo create blockedby/agentic-engineering-lab --public --clone`; branch currently `master` because empty repo defaulted there.
- Relevant verification: `gh repo view blockedby/agentic-engineering-lab --json nameWithOwner,visibility,isPrivate,url`; `git submodule status`; `git diff --check`; markdown `rg` scans for secrets/overclaiming/forbidden phrase; `git status --short --branch`.
- No repo-root AGENTS.md/README.md exists at `/home/kcnc/code`; no child AGENTS.md exists in new lab repo; profile repo has no AGENTS.md.

## Reuse discovery
- Root plan and explorer audit from `/tmp/github-portfolio-backlog.vBLiBN/` provide repo table and exact public/private boundaries.
- Existing profile README already contains required headline and links to lab; after remote creation that link should be real.
- Public submodule candidates verified by `gh repo view`: `blockedby/pi-codex`, `blockedby/go-openrouter`, `blockedby/hermes-agent`, `blockedby/linux-kubuntu-tweaks` are public GitHub repos.
- Explorer audit explicitly warns that private repos must not be published and notes profile untracked `profile-check.png`.

## Missing pieces
- Hub root README with required sections and public-only submodule instructions.
- Placeholder indexes: `case-studies/README.md`, `workflows/README.md`, `docs/README.md`.
- Audit document under `docs/audit/github-public-surface-audit.md` including repo table and private-repo warning.
- Optional public submodules under `submodules/` and `.gitmodules` only if URLs are public.
- Verification evidence under `verification/local.md` and final report.

## Plan tasks

### Task 1: Hub scaffold and public-only submodules
Goal:
- Make the lab repo a cloneable public hub with required docs, optional public submodules, and careful attribution language.
Boundary:
- System area: markdown/docs and git submodule metadata in `/home/kcnc/code/agentic-engineering-lab`.
- Primary verification: `git submodule status`, `.gitmodules` URL inspection, `git diff --check`, markdown safety scan.
Existing pattern / reuse:
- Use root/backlog context files for section language and public repo list.
Missing change:
- Add README/index files, audit report copy, `.gitmodules` with only confirmed public URLs.
Scope / likely files:
- `README.md`, `case-studies/README.md`, `workflows/README.md`, `docs/README.md`, `docs/audit/github-public-surface-audit.md`, `.gitmodules`, `submodules/*`, task-package progress/report files.
Acceptance criteria:
- README contains Focus areas, Public work, Selected case studies, How I work, submodule clone/update instructions, and fork/contribution wording.
- `.gitmodules` exists only with public GitHub URLs; no private repos are added.
- Audit report includes repo table and says private repos must not be made public.
Test plan:
- `gh repo view blockedby/agentic-engineering-lab --json nameWithOwner,visibility,isPrivate,url`
- `git submodule status`
- `git diff --check`
- `rg` scan for secrets/private URLs/overclaiming/forbidden phrase in changed markdown.
Dependencies: none.
Executor: aad-implementer.

### Task 2: Profile README link safety check/update
Goal:
- Ensure `/home/kcnc/code/blockedby/README.md` remains professional, has the required headline, and no broken link to the lab repo.
Boundary:
- System area: profile README only; do not touch or commit `profile-check.png`.
- Primary verification: `gh repo view` confirms lab link target; `rg` scans README for required/forbidden language.
Existing pattern / reuse:
- Current profile README already has concise professional sections and required headline.
Missing change:
- Only adjust if needed after lab repo creation.
Acceptance criteria:
- Required headline present; lab URL points to real public repo; no forbidden phrase; no overclaiming upstream ownership.
Test plan:
- `rg` profile README checks; `git diff --check`; `git status --short --branch`.
Dependencies: Task 1 remote existence check.
Executor: aad-implementer (or no-op report if already satisfied).

## Dependency graph
- Task 1 can run now and blocks final verification.
- Task 2 can run after remote existence is confirmed; likely no-op.
- No child sub-slices needed; slice stays whole with one implementer execution task plus owner verification.

## Execution ledger
- 2026-06-02: Created remote/local lab repo via `gh repo create`; wrote initial task package and plan.

## Final slice evidence
- Lab remote: `https://github.com/blockedby/agentic-engineering-lab`, public, default branch `main`.
- Lab commit: `e7938d5 Create public portfolio hub scaffold` pushed to `origin/main`.
- Profile README required no edit; link to lab now resolves because the public repo exists.
- Verification evidence: `verification/local.md`.
- Done-state: Slice 1 accepted by owner based on local/remote verification, with no unresolved blockers.
