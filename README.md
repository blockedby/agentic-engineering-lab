# Agentic Engineering Lab

Public portfolio hub for applied AI engineering, agent tooling, reusable skills, OSS contributions, and sanitized production engineering case studies by `blockedby`.

This repository is an index, not a product monorepo. The active work lives in the linked public repositories; this lab provides a concise map of the tools, operating model, and supporting evidence.

## Current focus

- Isolated Pi/Pipi environments and coding-agent runtime integration
- Multi-model delegation across Pi, Codex, Claude, Luna, and Terra
- Reusable Agent Skills for review, browser work, planning, and verification
- Deterministic evidence collection with bounded LLM-assisted interpretation
- Dependency-aware GitHub planning and conflict-safe parallel work
- Backend, Linux, browser-runtime, and operational automation

## Current agent toolkit

| Project | What it demonstrates |
|---|---|
| [`blockedby/my-pi-setup`](https://github.com/blockedby/my-pi-setup) | **Pipi**, my current isolated Pi environment: pinned runtime, separate state, subagent profiles, parallel workflows, background terminals, browser/Codex integration, and reusable skills. Maintained as a public fork of [`davis7dotsh/my-pi-setup`](https://github.com/davis7dotsh/my-pi-setup). |
| [`blockedby/plan-gh-backlog`](https://github.com/blockedby/plan-gh-backlog) | Agent Skill and Python CLI for validating roadmap structure, planning dependency-ready batches, and safely publishing idempotent GitHub issue backlogs. |
| [`blockedby/gpt5.6-reviewer`](https://github.com/blockedby/gpt5.6-reviewer) | Evidence-driven code-review contracts, routing, closure semantics, CLI validation, and a reusable review skill. |
| [`blockedby/pi-codex`](https://github.com/blockedby/pi-codex) | Deterministic web search/fetch plus bounded Codex summarization, patch handling, and delegated coding tools for Pi. |
| [`blockedby/browser-chrome-skill`](https://github.com/blockedby/browser-chrome-skill) | Portable Chrome DevTools skill with disposable headless sessions and an explicit persistent-browser boundary. |

Pipi composes the working environment around these capabilities: scoped implementation and audit agents, eight-way workflow fan-out, long-running background terminals, `fd`/`rg` discovery, ask-user interactions, browser MCP servers, and Codex/Claude/Pi delegation. The individual repositories keep each tool or skill inspectable and independently reusable.

## Reusable Agent Skills

The public [`skills/general`](https://github.com/blockedby/pi-agent-setup/tree/main/skills/general) collection contains the reusable engineering layer behind these workflows:

| Skill | Purpose |
|---|---|
| [`backend-quality`](https://github.com/blockedby/pi-agent-setup/tree/main/skills/general/backend-quality) | Backend, API, storage, validation, auth, idempotency, and data-safety evidence. |
| [`frontend-quality`](https://github.com/blockedby/pi-agent-setup/tree/main/skills/general/frontend-quality) | Frontend implementation and UI-quality checks. |
| [`devops-quality`](https://github.com/blockedby/pi-agent-setup/tree/main/skills/general/devops-quality) | Configuration, CI, container, deployment, and runtime readiness. |
| [`visual-composition`](https://github.com/blockedby/pi-agent-setup/tree/main/skills/general/visual-composition) | Product-quality hierarchy, responsive composition, complete states, and interaction polish. |
| [`completion-verification`](https://github.com/blockedby/pi-agent-setup/tree/main/skills/general/completion-verification) | Fresh acceptance evidence before readiness or completion claims. |
| [`git-branching`](https://github.com/blockedby/pi-agent-setup/tree/main/skills/general/git-branching) | Safe PR-first branches, worktrees, rebases, and target synchronization. |
| [`browser-chrome`](https://github.com/blockedby/browser-chrome-skill) | Controlled persistent and disposable Chrome automation. |
| [`explanatory-html-pages`](https://github.com/blockedby/pi-agent-setup/tree/main/skills/general/explanatory-html-pages) | Self-contained technical explainers with readable diagrams. |
| [`modern-skill-revising`](https://github.com/blockedby/pi-agent-setup/tree/main/skills/general/modern-skill-revising) | Focused context and instruction design for modern models. |

Standalone skills add specialized workflows: [`code-review`](https://github.com/blockedby/gpt5.6-reviewer/tree/main/skills/code-review) provides evidence-driven review and closure contracts, while [`plan-gh-backlog`](https://github.com/blockedby/plan-gh-backlog) validates and publishes dependency-aware GitHub backlogs.

## Additional public work

| Area | Public target | Notes |
|---|---|---|
| Voice tooling | [`blockedby/kwispr`](https://github.com/blockedby/kwispr) | Actively developed fork of [`MaksBoi/kwispr`](https://github.com/MaksBoi/kwispr): Wayland/KDE dictation with cloud, OpenRouter, and local/offline STT, plus a Rust inference runtime and native desktop integration. |
| Systems automation | [`blockedby/vibe-practicum-vpn`](https://github.com/blockedby/vibe-practicum-vpn) | Public-safe Linux/KDE VPN and routing tooling, container test labs, guarded operations, and redacted diagnostics. |
| LLM SDK work | [`blockedby/go-openrouter`](https://github.com/blockedby/go-openrouter) | Fork/contribution work around a Go OpenRouter SDK, with upstream attribution. |
| Linux automation | [`blockedby/linux-kubuntu-tweaks`](https://github.com/blockedby/linux-kubuntu-tweaks) | Personal Linux/Kubuntu automation and recovery runbook; environment-specific rather than a packaged product. |
| Browser runtime | [Obscura PR #195](https://github.com/h4ckf0r0day/obscura/pull/195) | Closed, unmerged Rust PR proposing bounded script/event-loop execution and regression tests for JS-heavy navigation. |

## Selected case studies

Start with [`case-studies/`](case-studies/) for the reading guide.

- [Obscura browser-runtime proposal](case-studies/obscura-browser-runtime-fix.md) — exact PR evidence, runtime failure mode, tests, constraints, and current closed/unmerged status.
- [Go OpenRouter SDK work](case-studies/go-openrouter-llm-sdk.md) — fork status, LLM API feature areas, and exact commit evidence.
- [Sanitized private-production workflow](case-studies/positions-agentic-workflow.md) — workflow patterns without private code, credentials, logs, domains, or user data.
- [Linux/Kubuntu automation runbook](case-studies/linux-kubuntu-tweaks-runbook.md) — practical systems debugging and recovery automation.

## Workflow references

- [AI-assisted PR loop](workflows/ai-assisted-pr-loop.md)
- [Task-package template](workflows/task-package-template.md)
- [Verification checklist](workflows/verification-checklist.md)
- [Pinned repositories checklist](docs/manual/pinned-repos-checklist.md)
- [Profile consistency check](docs/manual/profile-consistency-check.md)

## How I work

I use agents as engineering tools, not as unchecked decision makers:

1. define the problem, constraints, and acceptance criteria;
2. split work into bounded slices with explicit ownership and dependencies;
3. route exploration, implementation, and audit to the appropriate tool or model;
4. keep deterministic evidence separate from model summaries or opinions;
5. verify with tests, builds, static checks, browser evidence, or explicit manual checks;
6. record what changed, why it changed, and what remains risky.

## Optional public submodules

The `submodules/` directory contains optional references to selected public repositories. They are convenient review links, not vendored source or ownership claims over upstream projects.

```bash
git clone --recurse-submodules https://github.com/blockedby/agentic-engineering-lab.git
```

Only public repositories belong here. Private repositories must not be published or added as submodules.

## Public-safety rules

- No secrets, tokens, cookies, credentials, raw logs, chat IDs, webhook URLs, private endpoints, or real user data.
- No private repositories are published or linked as public evidence.
- Forks and contributions are described as fork work, contribution work, or my changes in a fork.
- Upstream projects and maintainers are attributed clearly.
