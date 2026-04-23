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

Rows for the 15 TikTok hooks + 3 YouTube scripts are pre-populated below (from calendar-template.yaml IDs). When Day 3 8:30 AM slot drafts the actual script bodies, add each script body to `med-contract-content/content/tiktok/<id>-script.md` or `youtube/<id>-*.md` and update the `Notes` column with the file path. Reviews fill the `perplexity` and `claude-chat-opus` columns on pass.

### TikTok (15 artifacts)

| Artifact ID | Type | Hook | Author | perplexity | claude-chat-opus | approved YAML? | Notes |
|---|---|---|---|---|---|---|---|
| tt-001 | TikTok script | "Your panel is 2,300 patients. MGMA median is 1,800. That's $62K/year of unpaid work." | Claude Code | pending | pending | no | refs mgma-im-panel-median, mgma-im-median-comp, mgma-im-median-per-wrvu |
| tt-002 | TikTok script | "Hospitalist pay looks the same at $310K. The shift math says otherwise." | Claude Code | pending | pending | no | refs mgma-hospitalist-median-comp, shm-shifts-per-year, shm-encounters-per-shift |
| tt-003 | TikTok script | "HEDIS bonus capped at 5%. Here's how the group kept the other 7%." | Claude Code | pending | pending | no | refs acp-hedis-bonus-range, mgma-im-median-comp |
| tt-004 | TikTok script | "99214 pays you $109. It pays the system $340. Know the gap." | Claude Code | pending | pending | no | refs cms-99214-non-facility, collections-ratio-hospital-employed |
| tt-005 | TikTok script | "Your tail coverage clause is worth $37K. Or it's worth zero. Read the comma." | Claude Code | pending | pending | no | refs tail-coverage-market-range (Perplexity adds section) |
| tt-006 | TikTok script | "Nocturnist differential: 25% industry standard. Your contract says 12%. That's $38K/year." | Claude Code | pending | pending | no | refs shm-nocturnist-differential, mgma-hospitalist-median-comp |
| tt-007 | TikTok script | "Outpatient IM median $/wRVU is $51. Your contract is $44. Over 4,800 wRVU, that's $33K." | Claude Code | pending | pending | no | refs mgma-im-median-per-wrvu, mgma-im-median-wrvu |
| tt-008 | TikTok script | "The 'quality bonus' that isn't. How HEDIS targets are written to fail." | Claude Code | pending | pending | no | refs acp-hedis-bonus-range |
| tt-009 | TikTok script | "Panel attribution rules: the clause that cost one IM doc $140K over 3 years." | Claude Code | pending | pending | no | refs mgma-im-panel-median, mgma-im-median-per-wrvu |
| tt-010 | TikTok script | "Capitation PMPM in Medicare Advantage: $40 vs $180. The spread is policy risk." | Claude Code | pending | pending | no | refs acp-capitation-pmpm-range |
| tt-011 | TikTok script | "Locum hospitalist: $2,400/shift. Employed hospitalist: $1,700/shift. The math on the switch." | Claude Code | pending | pending | no | refs locum-hospitalist-per-shift, shm-shifts-per-year, mgma-hospitalist-median-comp |
| tt-012 | TikTok script | "7-on / 7-off looks equal. It's not. Admission volume weights shift 1 vs shift 7 differently." | Claude Code | pending | pending | no | refs shm-encounters-per-shift, shm-admission-fee-range |
| tt-013 | TikTok script | "Your non-compete is 15 miles, 2 years. In NJ it's not enforceable past 1 year. Know your state." | Claude Code | pending | pending | no | state-law claim; Perplexity verifies NJ case law and any multi-state nuances |
| tt-014 | TikTok script | "Call coverage: paid or unpaid? The clause most IM contracts get wrong." | Claude Code | pending | pending | no | qualitative; Perplexity verifies SHM/ACP call-coverage norms |
| tt-015 | TikTok script | "CMS 2026 CF is $33.40. Your contract's internal CF is $34.50. That's a tell — your employer is making it up." | Claude Code | pending | pending | no | refs cms-2026-conversion-factor |

### YouTube (3 artifacts)

| Artifact ID | Type | Title | Author | perplexity | claude-chat-opus | approved YAML? | Notes |
|---|---|---|---|---|---|---|---|
| yt-m1 | YouTube script | "The 2026 Internal Medicine Compensation Stack — Every Dollar, Explained" | Claude Code | pending | pending | no | ~15min; script_file content/youtube/yt-m1-compensation-stack.md |
| yt-m2 | YouTube script | "Panel Size Math: How Your Employer Values Your Time" | Claude Code | pending | pending | no | ~12min; script_file content/youtube/yt-m2-panel-size-math.md |
| yt-m3 | YouTube script | "Hospitalist Shift Economics — 7-on/7-off, Nocturnist Diff, Admit Fees, and the $47K Gap Nobody Talks About" | Claude Code | pending | pending | no | ~18min; script_file content/youtube/yt-m3-hospitalist-shift-economics.md |

### LinkedIn / X / Threads / Substack (populated Day 3 7:00 PM)

| Artifact ID | Type | Title / Hook | Author | perplexity | claude-chat-opus | approved YAML? | Notes |
|---|---|---|---|---|---|---|---|
| _(Day 3 7:00 PM text-lane draft adds ~75 text posts here)_ | | | | | | | |

### Site user-facing copy (per RUNBOOK Section 4 — Lesson #19 gating)

| Artifact ID | Type | Title | Author | perplexity | claude-chat-opus | approved YAML? | Notes |
|---|---|---|---|---|---|---|---|
| site-hero | Site copy | Homepage hero + value bullets | Claude Code | pending | pending | no | Day 2 site scaffold; Day 4 review |
| site-product-grid | Site copy | 5 product-card descriptions | Claude Code | pending | pending | no | Day 2 site scaffold; Day 4 review |
| site-analyzer-faq | Site copy | /analyzer FAQ + form helper text | Claude Code | pending | pending | no | Day 2 site scaffold; Day 4 review |
| site-about | Site copy | /about founder bio + narrative | 🟣 Owner + Claude Code | pending | pending | no | Day 2 afternoon; requires owner input |
| site-analysis-prompt | System prompt | server/analysis-prompt.ts (IM/Hospitalist rewrite) | Claude Code | pending | pending | no | Day 2 site scaffold RUNBOOK §4; blueprint §8.3 |
| site-letter-template | System prompt | server/letter-docx.ts counter-proposal template | Claude Code | pending | pending | no | Day 2 site scaffold RUNBOOK §4 |
| site-email-welcome | Email copy | Kit welcome email (post-checklist download) | Claude Code | pending | pending | no | Day 3 Kit setup |
| site-email-twoweek | Email copy | 2-week analyzer follow-up automation | Claude Code | pending | pending | no | Day 3 Kit setup |

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
