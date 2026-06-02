# Linux/Kubuntu tweaks runbook

## Summary

Public repo: https://github.com/blockedby/linux-kubuntu-tweaks. Slice 5 sanitized the README for public portfolio use while preserving the practical systems runbook value.

Evidence:

- Merged PR #1: https://github.com/blockedby/linux-kubuntu-tweaks/pull/1
- Merge commit: https://github.com/blockedby/linux-kubuntu-tweaks/commit/c031146b5177944209c50a9522f3d65df2f97cbb; safety hotfix https://github.com/blockedby/linux-kubuntu-tweaks/commit/1fb9935ff2c9032929a7b41927c3524378f52873
- Branch: `portfolio-linux-sanitization`
- Latest slice commit: `1e4e70e`
- Main implementation commit: `b28e981`

## Problem

The repo contained useful personal Linux/Kubuntu automation notes, but public portfolio docs needed to avoid machine-specific private LAN details and private-repo bootstrap instructions.

## Solution

Slice 5 reframed the README as a personal automation and recovery runbook, not a product or universal installer. It preserved useful areas: Network/VPN, Pixel camera/v4l2loopback, Handy/Wayland, and KDE/Solaar. It generalized the camera endpoint to `WS_URL="ws://<phone-or-camera-host>:<port>"` guidance and removed the old private repository bootstrap note.

## Verification

Slice 5 verification recorded:

- Final README scan for private IP patterns, token/cookie/secret wording, `--private`, and forbidden public phrase passed with no matches.
- `git diff --check` passed.
- `git status --short --branch` was clean on `portfolio-linux-sanitization...origin/portfolio-linux-sanitization`.
- Current PR evidence on 2026-06-02: `gh pr view 1 -R blockedby/linux-kubuntu-tweaks` returned state `MERGED`, merge commit `c031146b5177944209c50a9522f3d65df2f97cbb`; safety hotfix `1fb9935ff2c9032929a7b41927c3524378f52873`.

## Why this matters

It shows practical systems debugging and automation while demonstrating the same public-safety discipline used for code-facing portfolio work.
