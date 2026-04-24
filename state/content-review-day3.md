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

### LinkedIn (30 posts — structural hooks drafted 2026-04-23 D3-5 pull-forward; full body text pending D3-17)

| Artifact ID | Type | Hook (truncated) | Author | perplexity | claude-chat-opus | approved YAML? | Notes |
|---|---|---|---|---|---|---|---|
| li-001 | LinkedIn post | "MGMA 2025 IM benchmark: $245K median…" | Claude Code | pending | pending | no | post_date 2026-04-27; cells mgma-im-median-comp |
| li-002 | LinkedIn post | "MGMA $/wRVU median for outpatient IM is $51…" | Claude Code | pending | pending | no | post_date 2026-04-28; cells mgma-im-median-per-wrvu |
| li-003 | LinkedIn post | "Hospitalist math: $310K median ÷ 173 shifts…" | Claude Code | pending | pending | no | post_date 2026-04-29; cells mgma-hospitalist-median-comp |
| li-004 | LinkedIn post | "Tail coverage ranges $15K–$80K by specialty…" | Claude Code | pending | pending | no | post_date 2026-04-30; cells tail-coverage-market-range |
| li-005 | LinkedIn post | "HEDIS bonus range: 3–12% of base (ACP data)…" | Claude Code | pending | pending | no | post_date 2026-05-01; cells acp-hedis-bonus-range |
| li-006 | LinkedIn post | "Nocturnist differential: 15–25% SHM standard…" | Claude Code | pending | pending | no | post_date 2026-05-02; cells shm-nocturnist-differential |
| li-007 | LinkedIn post | "CMS 2026 CF is $33.40. If employer CF differs…" | Claude Code | pending | pending | no | post_date 2026-05-03; cells cms-2026-conversion-factor |
| li-008 | LinkedIn post | "Panel attribution is 3 sentences in your contract…" | Claude Code | pending | pending | no | post_date 2026-05-04; cells mgma-im-panel-median |
| li-009 | LinkedIn post | "MA PMPM capitation: $40 to $180 depending…" | Claude Code | pending | pending | no | post_date 2026-05-05; cells acp-capitation-pmpm-range |
| li-010 | LinkedIn post | "Locum hospitalist: $2,400/shift. Employed: $1,700…" | Claude Code | pending | pending | no | post_date 2026-05-06; cells locum-hospitalist-per-shift |
| li-011 | LinkedIn post | "7+ states restrict or ban physician non-competes…" | Claude Code | pending | pending | no | post_date 2026-05-07; state-law; Perplexity verifies multi-state |
| li-012 | LinkedIn post | "Unpaid call burden for outpatient IM: 50–100 hrs…" | Claude Code | pending | pending | no | post_date 2026-05-08; qualitative; Perplexity verifies |
| li-013 | LinkedIn post | "99214 vs 99215: $109 vs $148 at 2026 CMS rates…" | Claude Code | pending | pending | no | post_date 2026-05-09; cells cms-99214-non-facility |
| li-014 | LinkedIn post | "Academic IM asst professor: AAMC median ~$195K…" | Claude Code | pending | pending | no | post_date 2026-05-10; cells aamc-asst-prof-im-outpatient |
| li-015 | LinkedIn post | "Collections ratio: hospital-employed 55–70%…" | Claude Code | pending | pending | no | post_date 2026-05-11; cells collections-ratio-hospital-employed |
| li-016 | LinkedIn post | "MIPS 2026: ±9% of Medicare allowable…" | Claude Code | pending | pending | no | post_date 2026-05-12; cells mips-2026-adjustment-pct |
| li-017 | LinkedIn post | "wRVU cliffs: clause that cuts your rate at threshold…" | Claude Code | pending | pending | no | post_date 2026-05-13; cells mgma-im-median-per-wrvu |
| li-018 | LinkedIn post | "3 productivity formula traps most IM docs miss…" | Claude Code | pending | pending | no | post_date 2026-05-14; cells mgma-im-median-comp |
| li-019 | LinkedIn post | "Medicare Advantage penetration reshaping hospitalist…" | Claude Code | pending | pending | no | post_date 2026-05-15; cells mgma-hospitalist-median-comp |
| li-020 | LinkedIn post | "Commercial multiplier: 1.3–1.6× Medicare for IM…" | Claude Code | pending | pending | no | post_date 2026-05-16; cells commercial-mult-primary-care-im |
| li-021 | LinkedIn post | "MGMA $245K median doesn't include malpractice…" | Claude Code | pending | pending | no | post_date 2026-05-17; cells mgma-im-median-comp |
| li-022 | LinkedIn post | "Signing bonus repayment: pro-rata vs cliff…" | Claude Code | pending | pending | no | post_date 2026-05-18; qualitative; Perplexity verifies clause norms |
| li-023 | LinkedIn post | "Relocation assistance as lump sum: taxable income…" | Claude Code | pending | pending | no | post_date 2026-05-19; qualitative |
| li-024 | LinkedIn post | "Real partnership track vs 'preferred associate'…" | Claude Code | pending | pending | no | post_date 2026-05-20; qualitative |
| li-025 | LinkedIn post | "Hospitalist admission fees: $50–$150/admit SHM…" | Claude Code | pending | pending | no | post_date 2026-05-21; cells shm-admission-fee-range |
| li-026 | LinkedIn post | "EMR documentation averages 2–3 hrs/day for IM…" | Claude Code | pending | pending | no | post_date 2026-05-22; cells mgma-im-median-wrvu |
| li-027 | LinkedIn post | "99291: critical care 30–74 min, $375 facility…" | Claude Code | pending | pending | no | post_date 2026-05-23; cells cms-99291-facility |
| li-028 | LinkedIn post | "Telehealth for IM in 2026: CMS flexibilities…" | Claude Code | pending | pending | no | post_date 2026-05-24; cells cms-2026-conversion-factor |
| li-029 | LinkedIn post | "FTE definition trap: '0.8 FTE' + call + admin…" | Claude Code | pending | pending | no | post_date 2026-05-25; cells mgma-im-median-comp |
| li-030 | LinkedIn post | "5 numbers every IM doc needs before signing…" | Claude Code | pending | pending | no | post_date 2026-05-26; cells mgma-im-median-per-wrvu, mgma-im-panel-median |

### X / Twitter (30 posts — structural thread openers drafted 2026-04-23 D3-5 pull-forward; full threads pending D3-17)

| Artifact ID | Type | Hook (truncated) | Author | perplexity | claude-chat-opus | approved YAML? | Notes |
|---|---|---|---|---|---|---|---|
| x-001 | X post | "MGMA 2025 IM median: $245K. 75th: $285K…" | Claude Code | pending | pending | no | post_date 2026-04-27 |
| x-002 | X post | "MGMA $/wRVU median for outpatient IM = $51…" | Claude Code | pending | pending | no | post_date 2026-04-28 |
| x-003 | X post | "Hospitalist pay math: $310K ÷ 173 shifts…" | Claude Code | pending | pending | no | post_date 2026-04-29 |
| x-004 | X post | "Your tail coverage clause is worth $15K–$80K…" | Claude Code | pending | pending | no | post_date 2026-04-30 |
| x-005 | X post | "HEDIS bonus range: 3–12% of base (ACP)…" | Claude Code | pending | pending | no | post_date 2026-05-01 |
| x-006 | X post | "SHM nocturnist differential standard: 15–25%…" | Claude Code | pending | pending | no | post_date 2026-05-02 |
| x-007 | X post | "CMS 2026 CF = $33.40. If group's internal CF differs…" | Claude Code | pending | pending | no | post_date 2026-05-03 |
| x-008 | X post | "Panel attribution: 3 sentences that determine…" | Claude Code | pending | pending | no | post_date 2026-05-04 |
| x-009 | X post | "MA capitation PMPM: $40 to $180…" | Claude Code | pending | pending | no | post_date 2026-05-05 |
| x-010 | X post | "Locum hospitalist: $2,400/shift. Employed: ~$1,700…" | Claude Code | pending | pending | no | post_date 2026-05-06 |
| x-011 | X post | "7+ states restrict or ban physician non-competes…" | Claude Code | pending | pending | no | post_date 2026-05-07 |
| x-012 | X post | "Unpaid call: 50–100 hrs/year uncompensated…" | Claude Code | pending | pending | no | post_date 2026-05-08 |
| x-013 | X post | "99214 = $109. 99215 = $148 (2026 CMS)…" | Claude Code | pending | pending | no | post_date 2026-05-09 |
| x-014 | X post | "Academic IM asst professor median ~$195K…" | Claude Code | pending | pending | no | post_date 2026-05-10 |
| x-015 | X post | "Collections ratio: hospital-employed 55–70%…" | Claude Code | pending | pending | no | post_date 2026-05-11 |
| x-016 | X post | "MIPS 2026: ±9% of Medicare allowable…" | Claude Code | pending | pending | no | post_date 2026-05-12 |
| x-017 | X post | "wRVU cliffs: clause that cuts per-RVU rate…" | Claude Code | pending | pending | no | post_date 2026-05-13 |
| x-018 | X post | "3 productivity formula traps…" | Claude Code | pending | pending | no | post_date 2026-05-14 |
| x-019 | X post | "High MA panel → lower CMI → downward wRVU…" | Claude Code | pending | pending | no | post_date 2026-05-15 |
| x-020 | X post | "Commercial multiplier: 1.3–1.6× Medicare for IM…" | Claude Code | pending | pending | no | post_date 2026-05-16 |
| x-021 | X post | "MGMA $245K median ≠ total comp…" | Claude Code | pending | pending | no | post_date 2026-05-17 |
| x-022 | X post | "Signing bonus repayment: pro-rata vs cliff…" | Claude Code | pending | pending | no | post_date 2026-05-18 |
| x-023 | X post | "Relocation as lump sum: taxable, $6K–8K diff…" | Claude Code | pending | pending | no | post_date 2026-05-19 |
| x-024 | X post | "Real partnership track: buy-in, capital, governance…" | Claude Code | pending | pending | no | post_date 2026-05-20 |
| x-025 | X post | "Hospitalist admission fee: $50–$150/admit…" | Claude Code | pending | pending | no | post_date 2026-05-21 |
| x-026 | X post | "EMR documentation: 2–3 hrs/day, 0 wRVU…" | Claude Code | pending | pending | no | post_date 2026-05-22 |
| x-027 | X post | "99291: 30–74 min critical care = $375 facility…" | Claude Code | pending | pending | no | post_date 2026-05-23 |
| x-028 | X post | "Telehealth for IM: CMS extended flexibilities…" | Claude Code | pending | pending | no | post_date 2026-05-24 |
| x-029 | X post | "'0.8 FTE' + call + admin = real FTE redefinition…" | Claude Code | pending | pending | no | post_date 2026-05-25 |
| x-030 | X post | "5 numbers every IM doc needs before signing…" | Claude Code | pending | pending | no | post_date 2026-05-26 |

### Threads (15 posts — COMPLETE content drafted 2026-04-23 D3-5 pull-forward; hooks ARE the posts ≤500 chars)

| Artifact ID | Type | Hook (full — this IS the post) | Author | perplexity | claude-chat-opus | approved YAML? | Notes |
|---|---|---|---|---|---|---|---|
| th-001 | Threads post | "MGMA 2025: IM median $245K. 75th percentile $285K. That $40K gap is mostly a contract problem — not a productivity problem." | Claude Code | pending | pending | no | post_date 2026-04-27; complete content |
| th-002 | Threads post | "MGMA $/wRVU median = $51 for outpatient IM. If yours is $44, that's $33K/year underpaid at 4,800 wRVU. Calculate your rate first." | Claude Code | pending | pending | no | post_date 2026-04-28 |
| th-003 | Threads post | "$310K hospitalist median ÷ 173 shifts = $1,792/shift. Your employer bills $2,400+ for the same 12-hr slot. Know the spread." | Claude Code | pending | pending | no | post_date 2026-04-29 |
| th-004 | Threads post | "Tail coverage for IM: $15K–$80K range. You're on the low end. Which means your employer has almost no excuse for not covering it. Most still try." | Claude Code | pending | pending | no | post_date 2026-04-30 |
| th-005 | Threads post | "HEDIS bonus range: 3–12% of base (ACP data). Most contracts write the targets to pay at 3%. That's not an accident." | Claude Code | pending | pending | no | post_date 2026-05-01 |
| th-006 | Threads post | "Nocturnist differential: SHM standard 15–25%. Below 12%: you're subsidizing day shift. Above 25%: you negotiated. Which category are you in?" | Claude Code | pending | pending | no | post_date 2026-05-02 |
| th-007 | Threads post | "CMS 2026 CF = $33.40. If your group's internal CF is higher or lower and no one can explain why — that explanation is worth finding before you sign." | Claude Code | pending | pending | no | post_date 2026-05-03 |
| th-008 | Threads post | "Panel attribution: 3 sentences that determine who owns your patients when you leave. Read them before you sign. Most IM physicians don't." | Claude Code | pending | pending | no | post_date 2026-05-04 |
| th-009 | Threads post | "MA capitation PMPM: $40–$180. The spread is whether your employer understands risk scoring. If they can't show you the actuarial model, ask why." | Claude Code | pending | pending | no | post_date 2026-05-05 |
| th-010 | Threads post | "Locum: $2,400/shift. Employed: ~$1,700/shift equivalent. The $700 gap has to clear benefits and call burden. Run the math for your specific situation." | Claude Code | pending | pending | no | post_date 2026-05-06 |
| th-011 | Threads post | "7+ states restrict or ban physician non-competes. Your 15-mile / 2-year clause may already be unenforceable. Check your state before you stress about it." | Claude Code | pending | pending | no | post_date 2026-05-07 |
| th-012 | Threads post | "50–100 uncompensated call hours per year is common in employed IM. That's real labor. Your contract should name it and price it." | Claude Code | pending | pending | no | post_date 2026-05-08 |
| th-013 | Threads post | "99214 = $109. 99215 = $148. 2026 CMS rates. On 4,000 visits, the coding difference moves $156K in revenue. Code accurately — both under and over." | Claude Code | pending | pending | no | post_date 2026-05-09 |
| th-014 | Threads post | "Academic IM asst professor: ~$195K AAMC median. Research FTE reduces wRVU. Some contracts penalize you for time the institution assigned to non-clinical work." | Claude Code | pending | pending | no | post_date 2026-05-10 |
| th-015 | Threads post | "Collections ratio: hospital-employed IM 55–70%. Private practice 70–85%. The 15-point gap is your overhead rate — and partly what you negotiate." | Claude Code | pending | pending | no | post_date 2026-05-11 |

### Site user-facing copy (per RUNBOOK Section 4 — Lesson #19 gating)

| Artifact ID | Type | Title | Author | perplexity | claude-chat-opus | approved YAML? | Notes |
|---|---|---|---|---|---|---|---|
| site-hero | Site copy | Homepage hero + value bullets | Claude Code | pending | pending | no | Day 2 site scaffold; Day 4 review |
| site-product-grid | Site copy | 5 product-card descriptions | Claude Code | pending | pending | no | Day 2 site scaffold; Day 4 review |
| site-analyzer-faq | Site copy | /analyzer FAQ + form helper text | Claude Code | pending | pending | no | Day 2 site scaffold; Day 4 review |
| site-about | Site copy | /about founder bio + narrative | 🟣 Owner + Claude Code | pending | pending | no | Day 2 afternoon; requires owner input |
| site-analysis-prompt | System prompt | server/analysis-prompt.ts (IM/Hospitalist rewrite) | Claude Code | pending | pending | no | Day 2 site scaffold RUNBOOK §4; blueprint §8.3 |
| site-letter-template | System prompt | server/letter-docx.ts counter-proposal template | Claude Code | pending | pending | no | Day 2 site scaffold RUNBOOK §4 |
| site-email-welcome | Email copy | Kit welcome email (post-checklist download) | Claude Code | pending | pending | no | Day 3 Kit setup; drafted INBOX/kit/emails-spec.md §1 |
| site-email-twoweek | Email copy | 2-week analyzer follow-up automation | Claude Code | pending | pending | no | Day 3 Kit setup; drafted INBOX/kit/emails-spec.md §2 |
| site-email-bundle-welcome | Email copy | Bundle-purchase welcome automation | Claude Code | pending | pending | no | Day 3 Kit setup; drafted INBOX/kit/emails-spec.md §3 |

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
