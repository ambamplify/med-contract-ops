# Content Review Ledger — Day 3 (Lesson #19)

**Purpose:** Every MedCI content artifact (TikTok scripts, YouTube scripts, LinkedIn / X / Threads posts, Kit emails, landing-page copy) must pass **two reviews** before it can be marked `approved` in content YAML and queued into Buffer/Kit/site:

1. **Perplexity Review (Gate 1)** — fact-check against IM_DATA_2026.md + source links. Catches: flawed source data, unsourced statistics, factually wrong claims.
2. **Claude chat opus-mode review (Gate 2)** — brand/voice/compliance pass. Catches: off-voice tone, missing compliance disclaimer, unsafe advice.

**Why this exists (Lesson #19):** EMCI shipped flawed source data in its initial content pass; the error was only caught when Claude chat (opus-mode web UI) reviewed it. MedCI will NOT repeat this failure mode. This ledger is Launch Gate 18 evidence.

---

## Status key
- `PASS` — reviewer signed off, no blocking issues
- `FAIL` — reviewer flagged blocking issues; artifact cannot advance
- `CONDITIONAL` — reviewer flagged edits that must be applied; re-review required
- `pending` — not yet reviewed

**An artifact advances to `approved` only when both `perplexity` AND `claude-chat-opus` columns are `PASS`.**

---

## Ledger

| Artifact ID | Type | Title / Hook | Author | perplexity | claude-chat-opus | approved YAML? | Notes |
|---|---|---|---|---|---|---|---|
| _(populated Day 3 morning as scripts are drafted)_ | | | | | | | |

---

## Day 3 review schedule (pulled from blueprint §10 Day 3)

| Time | Batch | Gate 1 owner | Gate 2 owner |
|---|---|---|---|
| 9:45 AM | 15 TikTok scripts | 🟣 Perplexity | — |
| 10:15 AM | 15 TikTok scripts | — | 🟣 Owner pastes to Claude chat (opus) |
| 4:45 PM | 3 YouTube scripts | 🟣 Perplexity | — |
| 5:15 PM | 3 YouTube scripts | — | 🟣 Owner pastes to Claude chat (opus) |
| 7:45 PM | 75 text posts (LI/X/Threads) | 🟣 Perplexity | — |
| 8:15 PM | 75 text posts | — | 🟣 Owner pastes to Claude chat (opus) |

---

## How to log a review

When Perplexity or the owner completes a review, append rows OR edit existing rows in the ledger above. For Perplexity reviews, Perplexity writes directly here via its lane. For Claude-chat-opus reviews, owner copy-pastes the verdict summary into this file (one-line verdict + notes).

**Example row (fully reviewed, approved):**
`tt-001 | TikTok script | "Panel size vs. pay — the math" | Claude Code | PASS | PASS | yes (content-tiktok YAML) | minor stat polish applied 2026-04-25 10:22 EDT`

**Example row (Gate 1 failed):**
`tt-007 | TikTok script | "Average hospitalist shift = 12h" | Claude Code | FAIL — MGMA 2025 shows median 10–11h, not 12h | pending | no | rewrite required before Gate 2`

---

**Ledger opened:** 2026-04-22 late evening EDT by Claude Code (thread session) on the same pass that added Lesson #19 to the blueprint. First entries expected Day 3 morning.
