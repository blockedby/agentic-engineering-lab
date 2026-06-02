# GitHub public-surface audit

Source: AAD explorer audit for the GitHub portfolio setup, 2026-06-02.

## Safety rule

Private repositories must not be made public, linked as public evidence, or added as submodules. Public materials must not include secrets, raw logs, credentials, private IPs, private URLs, chat IDs, tokens, cookies, webhook URLs, or real user data.

## Repo table

| Repo | Local path | Visibility | Portfolio role | Required action | Risk |
|---|---|---|---|---|---|
| `blockedby/blockedby` | `/home/kcnc/code/blockedby` | Public, not fork | GitHub profile README / first impression | Keep concise; link only to real public targets | Existing untracked local `profile-check.png` must not be committed |
| `blockedby/agentic-engineering-lab` | `/home/kcnc/code/agentic-engineering-lab` | Public, not fork | Main public portfolio hub | Maintain hub scaffold, public-only docs, optional public submodules | Must not become a dumping ground for private artifacts |
| `blockedby/pi-codex` | `/home/kcnc/code/tools/pi-codex` | Public, not fork | Main AI tooling proof | Polish README in separate slice | Existing local metadata drift must not be mixed into unrelated commits |
| `blockedby/go-openrouter` | not cloned under `/home/kcnc/code` during audit | Public fork of `reVrost/go-openrouter` | OSS fork / LLM SDK evidence | Add fork-status / my-changes attribution in separate slice before detailed case study | Overclaiming upstream authorship |
| `blockedby/hermes-agent` | `/home/kcnc/code/hermes/hermes-agent` | Public fork of `NousResearch/hermes-agent` | Telegram/gateway agent-workflow case study | Add `MY_CHANGES.md` or equivalent in separate slice | Overclaiming upstream authorship; avoid bot/webhook/chat data |
| `blockedby/linux-kubuntu-tweaks` | `/home/kcnc/code/tools/linux-kubuntu-tweaks` | Public, not fork | Practical systems recovery / automation proof | Sanitize public README in separate slice before featuring deeply | Environment-specific notes can expose private operational details |
| `blockedby/positions` | `/home/kcnc/code/positions` | Public repo status was visible during audit, but used here only as separate product/private-work context | Sanitized production workflow case-study source only | Keep separate from hub; do not add as submodule | Private-work details, logs, users, credentials, and endpoints must not leak |
| `h4ckf0r0day/obscura` PR context | `/home/kcnc/code/tools/obscura` | Public upstream plus `blockedby` fork remote | Strong OSS contribution case study | Cite PR #195 and avoid local build/artifact clutter | Do not publish raw build outputs or unrelated untracked artifacts |

## Public submodule decision

The following repositories were confirmed public with `gh repo view` before being added as optional submodules:

- `https://github.com/blockedby/pi-codex.git`
- `https://github.com/blockedby/go-openrouter.git`
- `https://github.com/blockedby/hermes-agent.git`
- `https://github.com/blockedby/linux-kubuntu-tweaks.git`

No private repositories should be added to `.gitmodules`.

## Attribution rules

- `hermes-agent` must be described as fork/work around Hermes Agent, with upstream maintainers attributed.
- `go-openrouter` must be described as fork work / my changes in a fork, not original upstream authorship.
- Obscura should be described as a contribution or opened PR unless/until merge status proves otherwise.

## Repos to polish before deeper portfolio use

- `pi-codex`: README polish for AI tooling proof.
- `hermes-agent`: upstream attribution and exact change list.
- `go-openrouter`: fork status / my changes section.
- `linux-kubuntu-tweaks`: public README top-note/sanitization.

## Repos to keep private or sanitized-only

Private or sensitive work must remain private. If discussed, it should appear only as sanitized case studies that omit code, credentials, raw logs, private domains, endpoints, user data, screenshots with data, and operational identifiers.
