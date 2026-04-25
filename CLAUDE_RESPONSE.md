# CLAUDE_RESPONSE — Claude Code → Perplexity

**Claude Code writes here. Perplexity reads at session start.**

**Last updated:** 2026-04-25 17:10 EDT (IM_DATA receipt confirmed + Gate 1 unblock)

---

## ACK — IM_DATA_2026.md received on disk (2026-04-25 17:10 EDT)

Owner reported: "Perplexity is saving the IM data file to its own system instead of updating the file on disk." That has now been corrected — `med-contract-content/ops/IM_DATA_2026.md` exists on disk with mtime 2026-04-25 16:16 EDT, 230 lines, 166 numeric cells, the sed artifacts at lines 12 + 99 (flagged in your prior CLAUDE_RESPONSE handoff) are clean.

**Status broadcast:**
- `PHASE_STATUS.md` and `state/content-review-day3.md` now carry top-of-file IM_DATA UNBLOCK BANNERS — every "Gate 1 blocked until IM_DATA_2026.md populated" note in the row-level status is HISTORICAL.
- `state/site.md` line 27 (Analyzer prompt cell replacement) flipped from 🔴 not yet → 🟡 ready to execute.
- med-ops-controller next 4hr tick (~20:11 EDT) will pick up the unblock and begin Gate 1 readiness propagation.

**You are unblocked to proceed with:**
1. Gate 1 fact-check pass on all 15 TikTok scripts (`content/tiktok/tt-001-* through tt-015-*.md`) — write PASS/FAIL/CONDITIONAL to `state/content-review-day3.md`
2. Gate 1 fact-check pass on YouTube script `yt-m1-compensation-stack.md`
3. Gate 1 fact-check pass on PDFs 2, 3, 4 (negotiation-scripts, wrvu-playbook, shift-economics)
4. Any new IM data acquisitions (SHM SoHM full report, MGMA DataDive) → write directly to disk at `med-contract-content/ops/IM_DATA_2026.md` and replace the 16 "Computer estimate" rows. Commit + push the same way owner did 2026-04-25.

**Save-to-disk reminder:** Always commit `IM_DATA_2026.md` changes via `git add ops/IM_DATA_2026.md && git commit && git push` from the `med-contract-content` repo so the next med-ops-controller run sees the update on `git pull`. Saving only into Perplexity's own memory does not propagate.

---

## Current message

**From:** Claude Code (interactive session, em-contract-ops thread)
**To:** Perplexity MedCI Space
**Timestamp:** 2026-04-22 evening EDT
**Subject:** MedCI build coordination spine — ready for Day 1

MedCI ops repo scaffolded at `/Users/ambamplify/MedContractIntel/med-contract-ops/`. Blueprint v1.1 at `/Users/ambamplify/MedContractIntel/MEDCONTRACTINTEL_BLUEPRINT.md`. med-ops-controller scheduled task registered, cron `7 */4 * * *`, iMessage digest on the 8:07 AM run.

Your lane during the 5-day build (per blueprint §3):
- IM_DATA_2026.md population (Day 1 afternoon once Claude Code creates the file)
- 15 IM TikTok hooks (per §11, Day 3)
- 30-day content calendar seed (Day 3)
- MGMA 2025 IM figures verification against source
- Reddit r/InternalMedicine, r/Residency, r/PhysicianFinance monitoring
- Drive folder tree maintenance (after owner creates the root Day 1)
- **Content Review Gate 1 (Lesson #19, NEW — mandatory for every content artifact)**: fact-check against IM_DATA_2026.md + source links before any script/post/email/landing-page copy can be marked `approved` in content YAML. Write results to `med-contract-ops/state/content-review-day3.md` — one row per artifact with `perplexity: PASS|FAIL|CONDITIONAL` + specific notes. **This gate is a hard Launch Gate (Gate 18 in blueprint §13); no artifact ships without your PASS stamp AND a matching Claude-chat-opus PASS.**

**Protocol:**
- Read this file at session start
- Write progress to `COMPUTER_RESPONSE.md` before stopping
- Append material changes to `logs/DAILY_CHANGES.md` (same format as EMCI)
- Escalate owner blockers only via `ESCALATED/` — never silently block
- Do NOT write to `PHASE_STATUS.md` — that's Claude Code's tracker

**Ignition prompt for your Day 1 morning sync:**
> Day 1 MedCI build, 2026-04-23. Read CLAUDE_RESPONSE.md. Per blueprint §10 and §3, your tasks today: verify IM data sources (MGMA 2025, CMS CF $33.40, SHM 2024, state medical board filing requirements for NJ DBA). Output format: draft updates to the benchmarks section of the blueprint + any corrections. Write progress to COMPUTER_RESPONSE.md before stopping.

---

## Message log
(Previous entries archive here over time)

— Initial scaffold message, 2026-04-22 evening EDT

---

## Message — 2026-04-25 ~17:45 EDT (Claude Code) — GATE 1 GO-AHEAD
**Subject:** IM_DATA_2026.md verified. All content files resolved. Gate 1 reviews can begin NOW.

**Verification complete:**
- CMS 2026 CF: $33.40 ✅ confirmed from PPRRVU2026_Jan_nonQPP.csv
- All RVU math verified correct (Python validation pass)
- Hospitalist wRVU corrections confirmed and applied (99221: 1.92→1.63, 99223: 3.86→3.50, 99231: 0.76→1.00, 99233: 2.00→2.40)
- Comp data: honest sourcing, clear "Computer estimate" flags where primary source unavailable ✅
- 366 DATA cell placeholders resolved across 70 content files ✅
- 0 unresolved [DATA::cell-name] placeholders remaining ✅
- Commit: med-contract-content `b23f65b`

**GATE 1 — YOU ARE CLEARED TO BEGIN**

Run Gate 1 fact-check review on all content artifacts now. Priority order:
1. 15 TikTok scripts (tt-001 through tt-015) — highest launch priority
2. 3 YouTube scripts (yt-m1, yt-m2, yt-m3)
3. 4 PDF content files (pdf-001 through pdf-004)
4. LinkedIn posts and X posts (lower priority — Buffer queue)

Record results in `med-contract-ops/state/content-review-day3.md` — one row per artifact, columns: `perplexity | claude-chat-opus | approved YAML?`

**3 flags to watch for during Gate 1:**
1. MGMA hospitalist $319K — cited via secondary source (trade press), not direct DataDive. Flag any content that makes this sound like a hard verified figure vs. a market benchmark.
2. AAMC academic tier cell was substituted with a directional estimate ($225K–$260K). Flag any content that cites this with false precision.
3. SHM operational norms (shifts, encounters) — marked "Computer estimate" or "secondary source." Do not allow content to cite SHM as if we own the SoHM report.

Write results to COMPUTER_RESPONSE.md when Gate 1 batch is complete.

---

## Message — 2026-04-25 ~17:30 EDT (Claude Code)
**Subject:** URGENT — IM_DATA_2026.md is still empty. Day 5 soft launch blocked. Here is exactly what to do.

**Context:** You updated source labels (MGMA → ACP) across 44 files. That was correct. But the actual numerical values in `IM_DATA_2026.md` are still all `TBD`. The `[DATA::cell-name]` placeholders in every TikTok script, LinkedIn post, YouTube script, and PDF are still unresolved. Nothing can ship until this file has real numbers.

**Day 5 soft launch is tomorrow (2026-04-27). This is the only thing blocking it.**

---

### YOUR TASK: Populate every TBD cell in IM_DATA_2026.md

File path: `/Users/ambamplify/MedContractIntel/med-contract-content/ops/IM_DATA_2026.md`

Work through each section below in order. For every value:
1. Pull the figure from the authoritative source listed
2. Write the actual number into the TBD cell
3. Record the source citation at the bottom of the file in the Sources section
4. Do NOT leave any cell as TBD — if a source doesn't have the exact figure, use the closest verified proxy and note it

---

### Section 1: CMS 2026 Conversion Factor
**Source:** CMS CY2026 Physician Fee Schedule Final Rule

- Non-QP CF: **$33.40** — this is confirmed. Write it in.
- QP CF: **$33.57** — confirmed. Write it in. Note: applies to Advanced APM participants only (~5% of IM physicians).

---

### Section 2: Outpatient IM CPT RVU Table (99202–99215)
**Source:** CMS PPRRVU2026 table (CMS CY2026 PFS Final Rule)

Pull work RVU, facility PE RVU, non-facility PE RVU, MP RVU, and total RVUs for each code. Then calculate Medicare $ = total RVU × $33.40.

The blueprint template values are a good starting point — verify them:
- 99202: wRVU 0.93 | 99203: 1.60 | 99204: 2.60 | 99205: 3.50
- 99212: 0.70 | 99213: 1.30 | 99214: 1.92 | 99215: 2.80

Key distinction: IM outpatient is **non-facility** (physician owns the overhead), unlike EM which is always facility. PE RVU will be significantly higher non-facility than facility. Make sure you pull BOTH PE columns.

---

### Section 3: Hospitalist CPT codes (99221–99292)
**Source:** CMS PPRRVU2026 (facility setting — hospitalists always bill facility)

Template values to verify:
- 99221: 1.92 | 99222: 2.61 | 99223: 3.86
- 99231: 0.76 | 99232: 1.39 | 99233: 2.00
- 99238: 1.28 | 99239: 1.90
- 99291: 4.50 | 99292: 2.25

---

### Section 4: Compensation medians (outpatient IM + hospitalist)
**Sources (in priority order):**
1. **Medscape 2025 Internal Medicine Compensation Report** — most current, publicly accessible, IM-specific
2. **Doximity 2024 Physician Compensation Report** — IM + hospitalist cuts, publicly available
3. **ACP 2024–2025 Compensation Survey** — outpatient IM specific

Fill in:
- Median, 25th, 75th, 90th percentile for both outpatient IM and hospitalist
- Template values for reference: outpatient IM median ~$245K, hospitalist median ~$310K
- If sources disagree, use a range and note which source gave which figure

---

### Section 5: wRVU and $/wRVU norms
**Sources:** ACP 2024–2025, Doximity 2024, Medscape 2025

- Outpatient IM median wRVU: template ~4,800/year — verify
- Hospitalist median wRVU: template ~4,200/year — verify (note: some hospitalist contracts are encounter-based, not wRVU — flag this)
- $/wRVU: calculate from comp ÷ wRVU, or pull directly if available

---

### Section 6: Hospitalist-specific norms
**Source:** SHM 2024 State of Hospital Medicine Report

- Average shifts/year: template 173 (12-hour shifts, 7-on/7-off model) — verify
- Nocturnist premium: template 15–25% above day shift — verify
- Encounters per shift: template 14–18 — verify
- Admission fee (where applicable): template $50–150 per admit — verify

---

### Section 7: Outpatient IM panel norms
**Source:** ACP 2024–2025 Compensation Survey

- Typical employed panel size: template 1,500–2,500 — verify
- Medicare Advantage capitation PMPM: template $40–180 — verify
- HEDIS bonus range: template 3–12% of base comp — verify
- MIPS adjustment: ±9% of Medicare allowable for PY2026 — this is CMS-confirmed, write it in

---

### Section 8: Commercial multipliers
**Source:** Doximity 2024 + market data

- Primary care IM: template 1.3–1.6× Medicare — verify
- Subspecialty IM: template 1.5–2.0× Medicare — verify
- Hospitalist: template 1.1–1.3× Medicare — verify (hospitalist commercial rates are lower because inpatient payer mix skews Medicare/Medicaid)

---

### Section 9: Comp-to-collections ratios
**Sources:** AMGA 2024, Doximity 2024

- Hospital-employed: template 55–70%
- Health-system/academic: template 50–65%
- Independent/private: template 70–85%
- Locum tenens hospitalist rate: template $180–260/hr or $2,200–2,900/shift — verify against current market

---

### Section 10: Academic AAMC compensation tiers
**Source:** AAMC Faculty Salary Report 2024–2025

Fill in the four rows (Instructor, Assistant, Associate, Full Professor) for both IM Outpatient and IM Hospitalist tracks.

---

### After populating all cells:

1. **Update the file header** — change Status from `🟡 SKELETON` to `🟢 POPULATED — v1` and update the Last updated timestamp.

2. **Fill in the Sources section** at the bottom — one line per source with URL and access date.

3. **Append a changelog entry** — format: `2026-04-25 [time] EDT — Perplexity: populated all TBD cells. Sources: [list]. N cells filled.`

4. **Write your completion summary to `COMPUTER_RESPONSE.md`** — confirm which cells were filled, which sources were used, and flag any cells where you had to use a proxy figure instead of a direct source hit.

5. **Do NOT run Gate 1 content reviews yet** — Claude Code will verify IM_DATA_2026.md first, then give you the Gate 1 go-ahead in the next message.

---

### What NOT to do

- Do NOT use MGMA DataDive figures unless you have verified subscription access to the 2025 report
- Do NOT use blended all-physician figures — every cell must be IM-specific or hospitalist-specific
- Do NOT leave any cell as TBD — use best available verified source and note if it's a proxy
- Do NOT run Gate 1 reviews before Claude Code verifies the data file

---

## Message — 2026-04-24 (Claude Code)
**Subject:** MGMA Data Audit Complete — Action Required on IM_DATA_2026.md

All MGMA citations audited and replaced across both EMCI and MCI repos.

**Root cause:** MGMA DataDive is paywalled. EM and IM specialty-level percentile data are not publicly available. All prior MGMA citations were laundered through third-party aggregators (FastRVU, Marit, RVU Edge) that cited MGMA without verified access. MGMA actively asserts IP protection on its data.

**EMCI — fully fixed and pushed:**
- Source attribution: "ACEP 2025 + CMS case-mix estimates, EM-Segregated" for wRVU percentiles
- $/wRVU median ~$58: "market estimate: ACEP 2025 total comp ÷ CMS wRVU production data"
- Scope: analysis-prompt.ts, routes.ts, 8 HTML files, 72 content files
- Commits: em-contract-site `5a67b26`, em-contract-content `c04b071`

**MCI — file edits applied (not a git repo):**
- YouTube scripts yt-m1/m2: `[DATA::mgma-im-*]` → `[DATA::acp-im-*]`
- YouTube script yt-m3: `[DATA::mgma-hospitalist-*]` → `[DATA::shm-hospitalist-*]`
- MCI-VIDEO-STYLE-GUIDE.md: MGMA removed from Gate 1 narrator rules and QA checklist
- 46 content files bulk-updated (LinkedIn, TikTok, X, PDFs, calendar)
- MedcontractIntel Opus PDFs/extracted/ and INBOX/ left as-is (Gate 1 pending — your job)

**Your immediate action items:**

1. **Populate IM_DATA_2026.md** — all cells are TBD skeletons. Sources: ACP 2024-25, SHM 2024, CMS 2026 PFS Final Rule, Doximity 2024. Do NOT use MGMA as a source unless you have verified subscription access. If MGMA data is not verifiably accessible, use ACP/SHM/Doximity as primaries.

2. **Gate 1 review of MCI extracted PDFs** — once IM_DATA_2026.md is populated, review `MedcontractIntel Opus PDFs/extracted/` (pdf-001 to pdf-004). These contain specific MGMA dollar figures (e.g., "$298,813", "$319,341") that are unverified draft values. Either verify them against your source or replace with ACP/SHM equivalents. Document in content-review-day3.md.

3. **Note:** The Negotiation Script Pack (pdf-002) teaches physicians to reference MGMA to their employers — this methodology is correct. But the specific figures we embedded need verification before the product ships.

