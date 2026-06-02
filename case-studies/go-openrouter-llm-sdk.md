# Go OpenRouter LLM SDK fork contribution

## Summary

This case study covers public fork/contribution work around the Go OpenRouter SDK. The upstream project is `reVrost/go-openrouter`; this is not an original-authorship claim.

Public evidence:

- Merged fork PR: https://github.com/blockedby/go-openrouter/pull/1
- Fork merge commit: https://github.com/blockedby/go-openrouter/commit/b9d174eea9384915a72cc741215f11f377bba853
- Upstream PR: https://github.com/reVrost/go-openrouter/pull/50
- Upstream merged commit: https://github.com/reVrost/go-openrouter/commit/016ba045a0facdd208102c9f25c8fc9515771e92
- Fork branch commit: https://github.com/blockedby/go-openrouter/commit/8251ecf

## Problem

Fork README/badge/module-path surfaces can easily overclaim ownership. The portfolio needed a precise explanation of what was upstream SDK work, what was confirmed `blockedby` contribution work, and why the module path still points to upstream.

## Solution

Slice 4 added `## Fork status / My changes` near the top of the README. It attributes upstream ownership to `reVrost/go-openrouter`, explains upstream-oriented badges/module path, and lists confirmed contribution links. It also describes portfolio-relevant SDK surfaces: typed chat completions/streaming, embeddings, reasoning controls, tool calling, structured outputs, prompt caching, web search options, multimodal content, and usage/cost metadata.

## Verification

Slice 4 verification recorded:

- `gh repo view blockedby/go-openrouter` showed public fork, parent owner `reVrost`.
- `gh pr list --repo reVrost/go-openrouter --author blockedby --state all` showed PR #50 as merged.
- `git diff --check origin/main..HEAD` passed.
- Safety/overclaim scan of the added attribution section passed; broad scan false positives were pre-existing upstream README examples such as API-key instructions.
- Current PR evidence on 2026-06-02: `gh pr view 1 -R blockedby/go-openrouter` returned state `MERGED`, merge commit `b9d174eea9384915a72cc741215f11f377bba853`.

## Why this matters

This shows backend/LLM SDK familiarity while keeping public claims tight: the signal is contribution quality, API-surface understanding, and attribution accuracy, not rebranding upstream work.
