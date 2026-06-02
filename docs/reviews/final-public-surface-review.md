# Final public-surface review

Review date: 2026-06-02.

## Checked file list

- `README.md`
- `case-studies/README.md`
- `case-studies/obscura-browser-runtime-fix.md`
- `case-studies/hermes-telegram-gateway.md`
- `case-studies/go-openrouter-llm-sdk.md`
- `case-studies/positions-agentic-workflow.md`
- `case-studies/linux-kubuntu-tweaks-runbook.md`
- `workflows/README.md`
- `workflows/ai-assisted-pr-loop.md`
- `workflows/task-package-template.md`
- `workflows/verification-checklist.md`
- `docs/README.md`
- `docs/audit/github-public-surface-audit.md`
- `docs/manual/pinned-repos-checklist.md`
- `docs/manual/profile-consistency-check.md`
- `docs/reviews/final-public-surface-review.md`
- `docs/final/github-portfolio-final-report.md`

## Public link evidence

- Lab repo is public: `gh repo view blockedby/agentic-engineering-lab` returned `visibility=PUBLIC`, `isPrivate=false`, URL `https://github.com/blockedby/agentic-engineering-lab`.
- Obscura PR #195: `https://github.com/h4ckf0r0day/obscura/pull/195`, state `OPEN`.
- Go OpenRouter PR #1: `https://github.com/blockedby/go-openrouter/pull/1`, state `MERGED`, merge commit `b9d174eea9384915a72cc741215f11f377bba853`.
- Linux/Kubuntu tweaks PR #1: `https://github.com/blockedby/linux-kubuntu-tweaks/pull/1`, state `MERGED`, merge commit `c031146b5177944209c50a9522f3d65df2f97cbb`; safety hotfix `1fb9935ff2c9032929a7b41927c3524378f52873`.
- Pi Codex PR #1: `https://github.com/blockedby/pi-codex/pull/1`, state `MERGED`, merge commit `768a5a7ce770788d9dda609e11b3a856410e70d6`.
- Hermes Agent attribution PR #23: `https://github.com/blockedby/hermes-agent/pull/23`, state `MERGED`, merge commit `53e6fbdb8e8401ff3fcc30393e84706469b190b2`.

## Scan scope

Changed lab markdown was scanned for secrets, private IPs, private URLs, chat IDs, tokens/cookies, overclaiming, and forbidden public phrase. The broad scan intentionally includes public-safety terms, so matches for words such as `token`, `cookie`, `secret`, `private`, and `chat ID` inside safety rules are false positives, not leaks.

## Blockers

No blockers found in the changed lab markdown. False positives are documented in the slice verification evidence and come from safety-rule wording or sanitized disclaimers.

## Notes

- The private-production case study is explicitly sanitized and contains no private repo link.
- Fork case studies attribute upstream projects and avoid original-authorship claims.
- Public PRs that were merged during root integration are described as merged, with merge commits.
