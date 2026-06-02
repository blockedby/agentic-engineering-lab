# Sanitized private-production agentic workflow

## Sanitized disclaimer

This case study is intentionally sanitized. It does not include private repository URLs, private domains, credentials, user data, chat IDs, raw logs, customer data, or deployment details. It describes a workflow pattern that can be discussed publicly without exposing the private system.

## Summary

The workflow uses AI agents as bounded engineering helpers around a human-owned delivery loop: task intake, evidence gathering, plan writing, implementation in isolated scopes, verification, review handling, and final reporting.

## Problem

Private production work often has ambiguous failures, sensitive data, and cross-cutting constraints. A useful agent workflow must improve throughput without leaking data, hiding uncertainty, or turning model output into an unverified source of truth.

## Solution

The operating model:

1. Normalize the goal, acceptance criteria, and do-not-touch boundaries.
2. Create a task package with plan, reports, verification notes, and progress.
3. Delegate narrow discovery or implementation tasks only when the scope is safe and independently verifiable.
4. Keep private details out of prompts and public reports unless explicitly approved and necessary.
5. Verify with deterministic commands, tests, diffs, browser checks, or manual evidence.
6. Classify findings as resolved now, follow-up issue, or unresolved blocker.
7. Produce a compact continuation report rather than a chat-only summary.

## Verification

The public portfolio setup itself used this pattern across slices: lab creation, README polish, fork attribution, Linux sanitization, and final public-surface review. The verification artifacts are public-safe and stored in this lab repo or linked public PRs; private implementation logs are not published.

## Why this matters

The value is not simply “using AI.” The value is disciplined delegation: agent speed combined with evidence, privacy boundaries, and human accountability for production claims.
