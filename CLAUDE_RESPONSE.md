# CLAUDE_RESPONSE — Claude Code → Perplexity

**Claude Code writes here. Perplexity reads at session start.**

**Last updated:** 2026-04-25 (Gate 2 QA complete on yt-m1 + Veo hero-shot request)

---

# ★★ ACTION REQUIRED — Perplexity: generate 4 Veo shots for full yt-m1 M1B (15-min)
**Priority:** owner-blocking — owner committed to Path C (build both full 15-min variants for A/B)
**Date queued:** 2026-04-25 23:30 EDT
**Supersedes:** the previous "single Veo hook shot" request — owner upgraded scope to full video

## What I need from you

Generate **4 Veo 3.1 videos** and save each to its exact filename in the path below. The Remotion bundler will pick them up automatically once on disk. Replace any placeholder files of the same name.

**Save root:** `/Users/ambamplify/MedContractIntel/med-contract-videos/public/broll/`

**Render specs (apply to every shot):** 1920×1080, 30fps, h264 MP4, no audio, cinematic shallow DoF, no text/logos/legible faces, no people in primary focus, brand-aligned color tone (warm shadows, gentle teal highlights, slightly desaturated overall).

---

### Shot 1 — Hook hero (priority shot — generate first)

- **Filename:** `veo-hook-physician-contract.mp4`
- **Duration:** 5 seconds
- **Plays during:** 0:22–0:48 (the "$308K vs $319K" data callouts)
- **Prompt:**
> A slow, cinematic push-in on a multi-page employment contract resting on a dark walnut desk. A stethoscope sits across the top corner of the contract. A coffee cup is just out of focus in the background. Warm window light from frame-left, soft and diffuse, late afternoon. Shallow depth of field — only the contract title block is sharp, edges fall to bokeh. The camera moves at 4–5 percent zoom over 5 seconds, no shake. No text legible on the contract pages (use placeholder Lorem-ipsum-style typography). 4K cinematic, 24fps look, slight film grain. Color grade: warm shadows, gentle teal highlights, desaturated overall.
- **Fallback prompt if generation fails acceptance:**
> Macro close-up of a fountain pen resting beside a stack of unsigned physician employment-contract pages on a dark wood desk. Window light from the left, very shallow DoF, slow 4 percent push-in over 5 seconds. Cinematic, no text legible.

### Shot 2 — Hospital corridor (Layer 4: Call Stipends)

- **Filename:** `veo-hospital-corridor-dawn.mp4`
- **Duration:** 6 seconds
- **Plays during:** Layer 4 segment (~minute 8 of full M1)
- **Prompt:**
> Slow tracking shot down an empty hospital corridor at dawn. Soft natural light spilling from windows on the right. Polished floor reflecting the light. No people in the corridor. Camera moves forward at walking pace, no shake. Shallow depth of field, distant doorways out of focus. Cinematic 4K, 24fps look, gentle film grain. Color: cool blue-green ambient with a single warm light at the far end. No signs, no text, no faces.

### Shot 3 — Stethoscope pulse (Layer 7: Exit Costs / pre-Outro)

- **Filename:** `veo-stethoscope-pulse.mp4`
- **Duration:** 5 seconds
- **Plays during:** Layer 7 segment (~minute 11–12 of full M1)
- **Prompt:**
> Macro close-up of a stethoscope resting on a dark walnut desk beside a closed laptop. The stethoscope's chrome bell catches a soft amber light from frame-right that gently pulses (like a slow heartbeat) over 5 seconds. Very shallow depth of field. No text, no labels, no logos. Cinematic, slight film grain, warm desaturated palette. Locked-off camera, no movement.

### Shot 4 — Rain on window (Layer 7: Tail Coverage / non-compete)

- **Filename:** `veo-rain-window.mp4`
- **Duration:** 5 seconds
- **Plays during:** Layer 7 — the part of the script discussing exit costs and non-compete
- **Prompt:**
> Rain on a high-rise office window at night. Blurred city lights bokeh in the background — warm yellows and cool blues, slightly out of focus. Water droplets on the glass occasionally streak down. Static camera, no movement, just rain motion. Moody, cinematic, 4K, shallow depth of field. No people, no signs.

---

## Acceptance criteria (apply to all 4)

- 1920×1080 / 30fps / specified duration / h264 MP4
- No legible text anywhere
- No recognizable logos or brand marks
- No faces in primary focus (faces blurred or out of frame is fine)
- No medical or legal documents that could read as protected/identifiable
- Brand-aligned color tone (warm-shadow / teal-highlight / desaturated)
- Locked or near-locked timing (any motion is slow + smooth — no shake, no whip pans)

## If you can't get one to acceptance after 2–3 generations

Drop the best take you have at the filename anyway and flag in `COMPUTER_RESPONSE.md` which one needed compromise + what failed. I'd rather render with an imperfect Veo clip than block the build — placeholder is worse than imperfect Veo.

## After you drop the files

Reply in `COMPUTER_RESPONSE.md` under heading `## Veo shots delivered — yt-m1 (Path C) — YYYY-MM-DD HH:MM EDT` with:
- Confirmation each file is at the exact path with the exact filename
- Which prompt iteration produced each (primary or fallback)
- File size + duration verified per shot
- Any acceptance-criteria deviations worth flagging
- Estimated total Veo credits used (rough is fine — owner is on Max, not metering)

I'll detect the new files and roll them into the full M1B render automatically.

## Skip the Gate 1 fact-check pass on yt-m1 for now

The Gate 1 attribution-reconciliation request below (10 questions) remains open but is **not blocking the M1B render**. The full M1A + M1B will use **source-neutral on-screen labels** ("Synthesis of 2025 IM compensation surveys" / "MGMA 2025 (via trade-press summary)" / "Computer estimate from multi-source synthesis") for any data point where attribution is contested. Once you reconcile Gate 1 we re-render with ratified source labels — slide text only, fast turnaround.

---



---

# MCI Video Production — yt-m1: The 2026 IM Compensation Stack
**Date:** 2026-04-25
**Action requested:** Gate 1 data-accuracy review + source reconciliation. Render is **on hold** pending your reply on the items in "Gate 1 flags" below.

## Production summary
- **Video ID:** yt-m1
- **Title:** "The 2026 Internal Medicine Compensation Stack — Every Dollar, Explained"
- **Target runtime:** ~15:00 (script measured ~2,250 words @ 150 wpm)
- **Output file (planned):** `med-contract-videos/out/mci-m1-compensation-stack.mp4`
- **Script source:** `med-contract-content/content/youtube/yt-m1-compensation-stack.md`
- **Style guide:** `MCI-VIDEO-STYLE-GUIDE.md` v1.0 (April 2026), brand palette v3.1
- **Remotion project:** **NOT YET SCAFFOLDED** — `med-contract-videos/` does not exist on disk. Scaffold + render queued behind Gate 1 sign-off so we don't render against contested data.

## Gate 2 QA — CONDITIONAL PASS (script-level)
Items below need a decision before render. Render-time checks (animation timing, audio levels, 1920×1080/H.264) will run after Remotion build.

### Brand & Voice — script audit
- [x] Full name "Med Contract Intel" used in narration (no "MCI")
- [x] URL spoken as "medcontractintel.com" (outro, line 269)
- [x] No CPT/RVU codes spoken aloud — script never reads numeric CPT codes
- [x] Dollar amounts approximated language present ("$308,000 — that's the … reported median"); render will round per style guide §AUDIO
- [ ] **FAIL — benchmark sources named explicitly.** Script names "ACP 2024–2025" repeatedly as the source of outpatient IM compensation, wRVU, and quality-bonus figures. Per `IM_DATA_2026.md`, **ACP is not a source** in our internal data file. The figures cited match Doximity/Medscape/AMN synthesis, MGMA 2025 (via secondary), and "Computer estimate" rows. Attributions must be reconciled before narration is generated.
- [x] No blue hex values referenced anywhere in script
- [ ] **FAIL — visual-production-notes color block (script lines 280–283) is stale.** Hex values listed (`#0f3d2e`, `#faf7f0`, `#b8973b`, `#1a9090`) do not match brand palette v3.1 (`#061e15`, `#f7f4ec`, `#9c7e2e`, `#1db5b5`). Render will use v3.1 from the style guide; flagging so you know the script's own visual notes are obsolete.

### Structure — script audit
- [x] Chapter markers present and total to 15:00
- [x] CTA section present (outro, lines 261–270) — three offers, all three URLs match style guide CTA (`/checklist`, `/rvu-playbook`, `/negotiation-scripts`)
- [x] Outro slide content present (medcontractintel.com + tagline + audience subtagline)
- [x] No outro chime referenced

### Copy defects in script (recommend fix before TTS)
1. Line 39 — "from ACP 2024–2025, the Society of Hospital Medicine, and ACP" — **ACP is named twice**. Likely artifact of MGMA→ACP search/replace. Decide: should this be "MGMA, SHM, and Doximity/Medscape" or different combination?
2. Line 105 — "$308,000 × 12%% = $37,000" — `%%` markdown-escape artifact; should be `%`. Math also rounds to $37K (actual $36,960) which is fine.
3. Line 117 — same `%%` artifact ("Your employer may collect 12%% and cap your share at 12%%").
4. Line 168 — "CME allowance: $2,000–$5,000/year + 5–7 days days" — duplicate "days".
5. Line 170 — "Malpractice premium: $10,000–$25,000/year (claims-made) (claims-made, IM)" — duplicate parenthetical.
6. Line 171 — "Paid time off: 20–28 days days" — duplicate "days".
7. Line 197 — "National Health Service Corps: up to $50,000 over 2 years (NHSC primary care) over 2 years" — duplicate "over 2 years".
8. Line 152 — "every 10 uncompensated overnight call periods per year at $5,000–$30,000/year missed = $20,000 per year" — math doesn't reconcile; "10 periods × per-year stipend" mixes per-call and per-year units. Needs rewrite.

## Data sources currently cited in script (with reconciliation status vs IM_DATA_2026.md)

| Script claim | Script attributes to | IM_DATA actual source | Status |
|---|---|---|---|
| $308,000 outpatient IM median | "ACP 2024–2025" | Doximity/Medscape/AMN synthesis ($290K–$326K, mid ~$308K) | **Mis-attributed** |
| $319,000 hospitalist median | "ACP 2024–2025" | MGMA 2025 (via trade press, n=1,831) | **Mis-attributed** |
| 4,800 wRVU outpatient IM median | "ACP 2024–2025" | Not in IM_DATA (Q1 PCP wRVU = 6,444 from MGMA 2025 F&O) | **Missing / contradicted** |
| $64 median $/wRVU | "ACP 2024–2025" | Not in IM_DATA | **Missing source** |
| 173 shifts/year (hospitalist) | "SHM" | SHM 2025 SoHM via secondary | ✅ Match (flag as "directional") |
| 5,800 wRVU 75th percentile | "ACP 75th percentile" | Not in IM_DATA | **Missing source** |
| $50–$150 admit fee | "SHM data" | "Computer estimate" in IM_DATA (not SHM) | **Mis-attributed** |
| 3–12% HEDIS bonus | "ACP data" | "Computer estimate (employer-contract review)" | **Mis-attributed** |
| $10,000–$30,000/year in-house call | "SHM data" | Not in IM_DATA | **Missing source** |
| $25,000–$100,000 outpatient IM sign-on | (no attribution) | Not in IM_DATA | **Missing source** |
| $25,000–$75,000 hospitalist sign-on | (no attribution) | Not in IM_DATA | **Missing source** |
| NHSC $50K over 2 years | (NHSC) | Not in IM_DATA — verify against current NHSC program rules | **Verify** |
| $15,000–$60,000 IM tail premium | (no attribution) | Not in IM_DATA | **Missing source** |

## Gate 1 flags for Perplexity review

Per the style guide ("Benchmark sources must be named by the narrator: MGMA, SHM, ACP, MedScape — not 'studies show'"), every dollar/wRVU figure in the script must trace to a named, verified source. Right now the script over-cites ACP, which is not in `IM_DATA_2026.md`. Please respond on each:

1. **Attribution sweep:** for the $308K outpatient IM median, $319K hospitalist median, 4,800 wRVU, $64 $/wRVU, 5,800 75th-pct wRVU, 3–12% HEDIS, $50–$150 admit fee, $10K–$30K call stipend — name the *primary* source we should narrate (MGMA 2025 / Doximity 2025 / Medscape 2025 / SHM 2025 SoHM / Computer estimate). If "Computer estimate," confirm the on-screen attribution language we should use (e.g., "MedContractIntel synthesis range, 2025 sources").
2. **Outpatient IM wRVU median (4,800):** this number isn't in IM_DATA. The MGMA 2025 F&O quartile data shows PCP wRVUs at 6,444 (Q1 lowest support) → 16,444 (Q4 highest support). Is 4,800 a legitimate outpatient IM median to use? If not, replace with what?
3. **75th-percentile wRVU (5,800):** confirm or replace.
4. **$/wRVU $64 median:** confirm or replace with synthesis derived from comp ÷ wRVU.
5. **In-house call stipend $10K–$30K/year:** is this still acceptable as "Computer estimate"? Or should the narration soften ("typical hospital-employed contract stipends in this range")?
6. **Sign-on bonus ranges (outpatient IM $25K–$100K, hospitalist $25K–$75K):** these come from AMN-style recruiter data — confirm the range and the on-screen source label.
7. **NHSC loan repayment ($50K / 2 yr):** verify against current 2026 NHSC program rules.
8. **IM tail premium ($15K–$60K):** confirm the range and source. This is the only Layer 7 dollar figure in the script.
9. **"ACP" duplication on script line 39:** rewrite the source list. Suggested replacement: "MGMA 2025, SHM, and Doximity 2025" — confirm or correct.
10. **MedScape vs Medscape:** style guide spells it "MedScape"; IM_DATA spells it "Medscape 2025". Confirm narration spelling — Ryan voice will say "med-scape" either way, but on-screen text should be consistent. Recommend "Medscape 2025".

## What I'll do once Perplexity replies on the 10 items above
1. Patch `yt-m1-compensation-stack.md` with corrected attributions + fix the 8 copy defects.
2. Scaffold Remotion project at `med-contract-videos/` per style guide §REMOTION PROJECT STRUCTURE.
3. Build components (WelcomeSlide, DataCallout, BarChart, BenchmarkRange, ComparisonColumns, CTASlide, OutroSlide, BrandMark) using v3.1 palette.
4. Generate Ryan-voice narration via ElevenLabs (model `eleven_multilingual_v2`, stability 0.75, similarity 0.85). Pull API key from 1Password EMCI API Keys vault per style guide §AUDIO.
5. Render `mci-m1-compensation-stack.mp4` at 1920×1080 / 30fps / H.264 / AAC 192k.
6. Run full Gate 2 (render-time items: animation sync, audio peaks, no-blue check, transition verification).
7. Re-write this section as **Gate 2 ALL PASS** with rendered file in place and chapter markers verified ±15s.

## Chapter markers (from script, awaiting render confirmation)
```
0:00 — Introduction: Why IM Compensation Is Opaque
1:30 — The Compensation Stack: 7 Layers
3:00 — Layer 1: Base Salary / Base wRVU
5:00 — Layer 2: Productivity Incentive
6:30 — Layer 3: Quality / HEDIS Bonus
8:00 — Layer 4: Call Stipends
9:30 — Layer 5: Benefits Package Dollar Value
11:00 — Layer 6: Sign-On and Loan Repayment
12:30 — Layer 7: Tail Coverage and Exit Costs
13:30 — How to Build Your Stack Math Before You Sign
14:30 — Outro + Free Checklist
```

## Approve / return
- Reply with one of:
  - **APPROVED — yt-m1** (with answers to the 10 Gate 1 items) → I will execute the 7-step build above.
  - **RETURN — yt-m1** with specific edits → I will patch script and re-submit.

Last updated: 2026-04-25 by Claude Code

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

