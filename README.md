# med-contract-ops

Ops repo for MedContractIntel (MedCI) — parallel business to EMCI, focused on Internal Medicine / Hospitalist contract analysis. 5-day build window: 2026-04-23 → 2026-04-27 soft launch.

## What lives here

- `BUILD_STATUS.md` — one-glance health table
- `PHASE_STATUS.md` — live execution tracker (ops-controller updates every 4hr)
- `CLAUDE_RESPONSE.md` — Claude Code → Perplexity directive channel
- `COMPUTER_RESPONSE.md` — Perplexity → Claude Code directive channel
- `PAUSE_ALL.md` — kill switch (non-empty = halt all med-* scheduled tasks)
- `logs/DAILY_CHANGES.md` — audit trail, all material decisions
- `ESCALATED/` — owner-action queue
- `INBOX/` — pending input (paste-ready prompts, owner notes)
- `state/` — per-day state files (e.g., `content-review-day3.md` for Lesson #19 dual review ledger)
- `monitors/` — runtime health probes (populated Day 4+)

## Sibling repos

- `med-contract-content` — 30-day content calendar + approved posts
- `med-contract-site` — Railway-deployed public site

## Reference

Canonical blueprint: `/Users/ambamplify/MedContractIntel/MEDCONTRACTINTEL_BLUEPRINT.md` (v1.2, 19 pre-solved lessons, 18 launch gates).

Scheduled task: `~/.claude/scheduled-tasks/med-ops-controller/SKILL.md` — cron `7 */4 * * *`, 8:07 AM iMessage digest to owner.

## EMCI separation

This repo is strictly separate from EMCI. Never touch `/Users/ambamplify/Desktop/em-contract-*/` or `~/.claude/scheduled-tasks/em-*/`.
