# Hermes Telegram gateway fork work

## Summary

This case study covers work in the public `blockedby/hermes-agent` fork. Hermes Agent is an upstream project by the NousResearch/Hermes maintainers; this portfolio entry describes Alexander Longov (`blockedby`) fork work and does not claim original authorship of Hermes Agent.

## Problem

The fork work focused on Telegram/business gateway behavior: approval flows, self-message filtering, DM topic/session fallback, session isolation, per-chat modes, dashboard API/UI/auth/session lease behavior, media ingestion, setup/config, and STT compatibility.

## Solution

Slice 3 added a public attribution file in the fork:

- Branch: `alex/github-portfolio-hermes-attribution`
- Commit: https://github.com/blockedby/hermes-agent/commit/dc688e32708b5050111d439ea8cdc1fdefc84264
- Suggested PR URL from push: https://github.com/blockedby/hermes-agent/pull/new/alex/github-portfolio-hermes-attribution

The attribution document lists exact commit links for the relevant Telegram/business gateway changes and summarizes touched areas such as `gateway/platforms/telegram.py`, `gateway/run.py`, `gateway/session.py`, Telegram business files, dashboard app, config/commands, tests, and docs.

## Verification

Slice 3 verification recorded:

- `git log --oneline --no-merges origin/main..HEAD` evidence in the fork task package.
- Diff-stat evidence over Telegram gateway, dashboard, tests, CLI config, and docs areas.
- First-lines attribution check passed.
- `git diff --check HEAD~1..HEAD` passed.
- Safety scan over `MY_CHANGES.md` found no raw logs, tokens, chat IDs, webhook URLs, private endpoints, real user data, forbidden public phrase, or upstream ownership claim.

## Why this matters

Gateway work is where agent systems meet messy production channels. This evidence shows scoped backend/platform changes, tests, attribution discipline, and privacy-aware public documentation.
