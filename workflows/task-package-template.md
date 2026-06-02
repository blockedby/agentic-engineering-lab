# Task package template

Use this structure for repo-local AAD work packages.

```text
docs/plans/YYYY-MM-DD-short-slug/
  README.md
  plan.md
  reports/
  verification/
  artifacts/
  progress/
```

## README.md

```md
# <task name>

Status: <planned | in progress | blocked | done>
Owner: <root owner | slice owner | implementer>
Branch/worktree: <branch and path>
PR: <URL or not opened>
Report: <final report path>
```

## plan.md sections

- Task intake: goal, in-scope behavior, out-of-scope boundaries, done-state, blocking unknowns.
- Repo orientation: project shape, local guidance, likely files, verification commands.
- Reuse discovery: existing components, docs, APIs, tests, or prior reports to reuse.
- Missing pieces: concrete files/features/evidence still needed.
- Plan tasks: acceptance criteria, test plan, dependencies, executor candidate, report path.
- Dependency graph: what can run in parallel, what must wait, and what is too large for one implementer.
- Execution ledger: dispatches, results, verification evidence, blockers, follow-ups.

## Report template

Each delegated report should include: task, context, spec compliance, acceptance verification, system readiness, verification run, issues (`R-*`, `F-*`, `U-*`), verdict, and next-agent brief.
