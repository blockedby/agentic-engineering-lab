# Agentic Engineering Lab

Public portfolio hub for applied AI engineering, agentic developer tooling, OSS contributions, and sanitized production engineering case studies by Alexander Longov (`blockedby`).

This repository is an index, not a product monorepo. It keeps public evidence, documentation, and optional links to related public repositories in one place.

## Focus areas

- Agentic developer tooling and bounded coding-agent workflows
- Deterministic evidence collection with LLM-assisted summarization
- Backend systems in Go and TypeScript/Node.js
- Production debugging, observability, CI/CD, and deployment automation
- Practical Linux and systems automation
- OSS fork work and contributions with clear upstream attribution

## Public work

| Area | Public target | Notes |
|---|---|---|
| AI tooling | [`blockedby/pi-codex`](https://github.com/blockedby/pi-codex) | Pi extension exposing Codex CLI through bounded tools for search/fetch, patch handling, and delegated coding tasks. |
| LLM SDK work | [`blockedby/go-openrouter`](https://github.com/blockedby/go-openrouter) | Fork work around a Go OpenRouter SDK; public materials should describe this as fork work, not original upstream authorship. |
| Agent gateway work | [`blockedby/hermes-agent`](https://github.com/blockedby/hermes-agent) | Fork/work around Hermes Agent gateway behavior; public materials should attribute the upstream Hermes Agent maintainers. |
| Systems automation | [`blockedby/linux-kubuntu-tweaks`](https://github.com/blockedby/linux-kubuntu-tweaks) | Personal Linux/Kubuntu automation and recovery runbook; environment-specific, not a packaged product. |
| OSS contribution | [Obscura PR #195](https://github.com/h4ckf0r0day/obscura/pull/195) | Browser-runtime contribution with bounded script/event-loop execution and regression tests. |

## Selected case studies

Case studies will be expanded as each public surface is polished and verified:

- [`case-studies/`](case-studies/) — reading guide and planned case-study index.
- Obscura browser-runtime fix — exact PR evidence, runtime failure mode, tests, and constraints.
- Hermes Agent Telegram/gateway work — my work in a fork, with upstream attribution and exact commit evidence.
- Go OpenRouter SDK work — fork status, LLM API feature areas, and exact commit evidence.
- Sanitized private-production workflow — no private code, credentials, logs, domains, or user data.
- Linux/Kubuntu automation runbook — practical systems debugging and recovery automation.

## How I work

I use agents as engineering tools, not as unchecked decision makers:

1. define the problem, constraints, and acceptance criteria;
2. split work into bounded slices with clear ownership;
3. use exploration agents for repo evidence and implementation agents for scoped changes;
4. keep deterministic evidence separate from model summaries or opinions;
5. verify with tests, builds, static checks, browser evidence, or explicit manual checks;
6. write down what changed, why it changed, and what remains risky.

## Optional public submodules

The `submodules/` directory contains optional references to confirmed public GitHub repositories. They are provided for convenient technical review; they are not vendored source and they are not ownership claims over upstream projects.

Clone with submodules:

```bash
git clone --recurse-submodules https://github.com/blockedby/agentic-engineering-lab.git
```

Or initialize after cloning:

```bash
git submodule update --init --recursive
```

Refresh submodules later:

```bash
git submodule update --remote --merge
```

Only public repositories belong here. Private repositories must not be made public or added as submodules.

## Public-safety rules

- No secrets, tokens, cookies, credentials, raw logs, chat IDs, webhook URLs, private endpoints, or real user data.
- No private repositories are published or linked as public evidence.
- Forks and contributions are described as fork work, contribution work, or my changes in a fork.
- Upstream projects and maintainers are attributed clearly.
