# server/analysis-prompt.ts — IM/Hospitalist Rewrite Spec

**Target file:** `/Users/ambamplify/MedContractIntel/med-contract-site/server/analysis-prompt.ts`
**Source file (EMCI):** `/Users/ambamplify/Desktop/em-contract-site/server/analysis-prompt.ts` (337 lines)
**Executes:** Day 2 afternoon after scaffold rsync + sed pass completes
**Dependencies:** `/Users/ambamplify/MedContractIntel/med-contract-content/ops/IM_DATA_2026.md` must have every referenced cell populated by Perplexity Day 1 Task 13. If a cell is still `TBD`, the analyzer still ships (the prompt tells Claude to caveat that benchmark), but a Day 4 verification pass updates the prompt with final numbers.
**Review gate:** Lesson #19 — `site-analysis-prompt` row in `state/content-review-day3.md`. Both Perplexity (fact-check) AND Claude-chat-opus (voice/compliance) must PASS before Day 5 launch.

---

## 1. What stays identical

- Function signature: `export function buildSystemPrompt(intake: IntakeData): string`
- Helper `getEmployerContext(employerType)` stays, but enum values change (see §4)
- `USER_PROMPT_TEMPLATE` export pattern
- Entire JSON output schema (`executiveSummary`, `compensation`, `clauseAnalysis`, `noncompete`, `malpractice`, `terminationProvisions`, `negotiationApproach`, `negotiationPriorities`, `contractStartDate`, `disclaimer`) — frontend expects these field names. DO NOT rename.
- Red-flag definitions structure
- Non-compete state enforceability list (state law is specialty-agnostic)
- Schema rules block at end

---

## 2. What changes — prose + language

| EM text | MedCI replacement |
|---|---|
| "expert emergency medicine physician contract analyst" | "expert internal medicine and hospitalist physician contract analyst" |
| "EM physician compensation models (hourly, RVU-based, collections-based, hybrid)" | "IM/hospitalist compensation models (salary, RVU-based, encounter-based, nocturnist/shift, hybrid)" |
| "Regional and national compensation benchmarks for emergency medicine" | "Regional and national compensation benchmarks for internal medicine (outpatient) and hospitalist medicine (inpatient)" |
| "emergency medicine physician employment contract" | "internal medicine or hospitalist physician employment contract" |
| Intake context variables | Add `panelSize`, `censusModel`, `nocturnistDifferential`, `shiftModel` intake fields (see §7) |
| "EM-SPECIFIC COMPENSATION DATA (2026) — VERIFIED EM-ONLY SOURCES" header | "IM/HOSPITALIST COMPENSATION DATA (2026) — VERIFIED MULTI-SOURCE" |
| "Sources: CMS CY2026 PFS Final Rule, ACEP 2025 Salary Survey (n=1,774), MGMA 2025 EM-segregated, Marit Health 2026, Daniel Stern 2024–2025" | "Sources: CMS CY2026 PFS Final Rule [cms-2026-pfs], MGMA 2025 Provider Compensation Survey IM-segregated + Hospitalist-segregated [mgma-2025], AAMC Faculty Salary Report 2024–2025 [aamc-2024-25], SHM State of Hospital Medicine 2024 [shm-2024], AMGA 2024 Comp & Productivity Survey [amga-2024], Doximity Physician Compensation Report 2024 [doximity-2024], ACP Practice Management 2024–2025 [acp-2024-25], Medscape Internist Compensation Report 2025 [medscape-2025-im]" |

**Blanket rules:**
- Remove every reference to ACEP survey data (EM-only).
- Remove every EM-specific CPT code table (99281–99285, 99291/99292 → drop the table).
- Remove every EM-specific setting: "freestanding ED", "Level I trauma center", "ED boarding".
- Remove the NSA 1.8× commercial multiplier block (EM-specific policy context).
- Remove the 2024 CF $32.74 reference — CMS 2026 CF $33.40 is current and applies to all physicians.

---

## 3. What changes — CPT codes and RVU mechanics

EM prompt lists 99281–99292 with wRVUs. IM/Hospitalist split into two CPT groups:

### IM outpatient CPT (2026 CMS, [cms-2026-pfs] cell) — for ambulatory IM contracts

| Code | Description | wRVU | Note |
|---|---|---|---|
| 99213 | Office/OP visit, est. pt., mod. complexity | [TBD from IM_DATA_2026.md::cms-99213-wrvu] | |
| 99214 | Office/OP visit, est. pt., mod-to-high complexity | [TBD::cms-99214-wrvu] | Headline outpatient IM code |
| 99215 | Office/OP visit, est. pt., high complexity | [TBD::cms-99215-wrvu] | |
| 99204 | New pt, mod complexity | [TBD::cms-99204-wrvu] | |
| 99205 | New pt, high complexity | [TBD::cms-99205-wrvu] | |
| G2211 | Complexity add-on | [TBD::cms-g2211-wrvu] | Applicable to primary-care evaluations; often missed in contract benchmarks |

### Hospitalist inpatient CPT (2026 CMS) — for hospital medicine contracts

| Code | Description | wRVU | Note |
|---|---|---|---|
| 99221 | Initial hospital care, low complexity | [TBD::cms-99221-wrvu] | |
| 99222 | Initial hospital care, moderate | [TBD::cms-99222-wrvu] | |
| 99223 | Initial hospital care, high | [TBD::cms-99223-wrvu] | Headline hospitalist admission code |
| 99231 | Subsequent hospital care, low | [TBD::cms-99231-wrvu] | |
| 99232 | Subsequent hospital care, mod | [TBD::cms-99232-wrvu] | |
| 99233 | Subsequent hospital care, high | [TBD::cms-99233-wrvu] | Headline hospitalist daily code |
| 99238 | Discharge, ≤30 min | [TBD::cms-99238-wrvu] | |
| 99239 | Discharge, >30 min | [TBD::cms-99239-wrvu] | |
| 99291 | Critical care, first 30-74 min | [TBD::cms-99291-wrvu] | Applies when hospitalist does ICU coverage |

**Drop the "facility EM blended PE+MP ratio 0.28" block.** IM outpatient is non-facility setting (different PE weights than facility EM). Hospitalist is facility setting but the professional-fee economics are structurally different (admit fee + daily fee vs. ED per-encounter). Replace with:

```
PRACTICE-SETTING PE MECHANICS (brief):
- Outpatient IM (non-facility): Total RVU ≈ 2.5–3× wRVU. PE+MP the dominant share.
- Hospitalist (facility): Total RVU ≈ 1.4–1.6× wRVU. wRVU is the dominant share. See [mgma-2025], [shm-2024] sections for setting-specific totals.
- DO NOT apply one ratio across both. If the contract does not state setting, ask or flag as ambiguous.
```

---

## 4. getEmployerContext — enum and prose updates

**Old enum:** `Large National Staffing Company | Regional Staffing Company | Hospital Employed | Independent Democratic Group`

**New enum for IM:**
- `Hospital System Employed (Outpatient IM)` — academic, community
- `Hospital Medicine Group (Hospitalist — Hospital Employed)`
- `Contract Management Group / Staffing Company (Hospitalist)` — TeamHealth, Sound, IPC, Apogee, etc.
- `Private Internal Medicine Group` — independent / partnership-track
- `Concierge / DPC` — subscription-based outpatient IM
- `Academic / University-Affiliated` — AAMC-tracked compensation bands
- `Federal / VA / Military` — separate comp schedule
- `Locum / Independent Contractor` — 1099, per-diem

**For each enum value, getEmployerContext returns a 2–4 sentence block referencing SHM/MGMA/AMGA median comp % of collections AND the specific red flags that employer type typically carries.** Don't reproduce the full EMCI block — write from scratch using the IM_DATA_2026.md benchmarks. Example for Hospitalist CMG:

> "Note: Contract Management Group hospitalist contracts (TeamHealth/Sound/IPC/Apogee) typically pay [TBD::cmg-hospitalist-comp-pct-collections]% of net professional collections to physicians. Flag any comp language that obscures the relationship between admission volume, census, and pay. Pay special attention to shift reassignment rights, overhead allocation, census caps + what happens at cap, and billing reconciliation clawback."

---

## 5. Compensation model adaptation block

EM had three branches: HOURLY / SALARY / RVU-based.

IM/Hospitalist has five:

### IF THE CONTRACT IS SALARY (most common in IM outpatient, partial-hospitalist)
- Compare fixed salary to [TBD::mgma-im-median-comp], [TBD::aamc-<rank>-im-median-comp], [TBD::doximity-im-median] by region.
- Focus on: annual increase mechanism, bonus structure (wRVU + quality + citizenship), workload-without-adjustment risk (if volume grows but pay doesn't).
- Set rvu.multiplier to 0, rvuType to "NOT_APPLICABLE" unless there's a stacked productivity bonus.

### IF THE CONTRACT IS RVU-BASED (common in hospital-employed IM, some hospitalist groups)
- Full RVU multiplier analysis (see §6 below).

### IF THE CONTRACT IS ENCOUNTER-BASED (common for hospitalists — $X per admission, $Y per subsequent day)
- NEW analysis mode (doesn't exist in EM prompt):
  - Extract admission fee, subsequent-day fee, discharge fee, night differential.
  - Multiply by [TBD::shm-encounters-per-shift] × [TBD::shm-shifts-per-year] to estimate annual comp.
  - Compare total to [TBD::mgma-hospitalist-median-comp].
  - Flag ratcheted census thresholds (pay per encounter drops above N admits per shift) as a red flag.

### IF THE CONTRACT IS SHIFT/NOCTURNIST (common in hospitalist)
- Apply shift economics:
  - Day rate + night rate differential ([TBD::shm-nocturnist-differential] industry standard = ~25% premium).
  - 7-on/7-off schedule = ~182.5 shifts/yr. Verify against [TBD::shm-shifts-per-year].
  - Total annual comp = day_rate × day_shifts + night_rate × night_shifts + differentials + sign-on amortized.
  - Flag any nocturnist-only contract without premium differential ≥ 20% as a red flag.

### IF THE CONTRACT IS CAPITATION / PMPM (rare — concierge, DPC, ACO-embedded IM)
- NEW analysis mode:
  - Extract PMPM rate + attributed-patient count.
  - Compare to [TBD::acp-capitation-pmpm-range] and [TBD::medicare-advantage-pmpm-range].
  - Flag risk-pool/downside-risk provisions — physician can owe money in bad-outcome year.

### IF HYBRID
- Compose the above modes; emphasize what share of total comp comes from each layer.

---

## 6. RVU multiplier analysis block (RVU-based / hybrid only)

Structurally mirrors EMCI block but with IM/Hospitalist benchmarks.

```
SETTING                                   | $/wRVU RANGE  | BELOW-MARKET THRESHOLD
Outpatient IM (hospital-employed)         | [TBD::mgma-im-outpt-per-wrvu-25-50-75] | [TBD::mgma-im-outpt-below-market]
Outpatient IM (academic)                  | [TBD::aamc-asst-prof-im-per-wrvu-25-50-75] | [TBD::aamc-below-market]
Outpatient IM (private group)             | [TBD::mgma-im-priv-per-wrvu-25-50-75] | [TBD::mgma-im-priv-below-market]
Hospitalist (hospital-employed)           | [TBD::mgma-hosp-emp-per-wrvu-25-50-75] | [TBD::mgma-hosp-below-market]
Hospitalist (CMG — TeamHealth/Sound/IPC)  | [TBD::mgma-hosp-cmg-per-wrvu-25-50-75] | [TBD::mgma-hosp-cmg-below-market]
Academic hospitalist                      | [TBD::aamc-asst-prof-hosp-per-wrvu-25-50-75] | [TBD::aamc-hosp-below-market]
Critical-access / rural hospitalist       | [TBD::cah-hospitalist-per-wrvu-25-50-75] | [TBD::cah-hospitalist-below-market]
Concierge / DPC                           | [TBD::concierge-per-member-comp] | N/A — use PMPM
```

Dollar-gap scale at IM median wRVU ([TBD::mgma-im-median-wrvu] wRVUs): $10/wRVU gap = [TBD::derived] annual shortfall.
Dollar-gap scale at hospitalist median ([TBD::mgma-hospitalist-median-encounters] × avg wRVU/encounter): $10/wRVU gap = [TBD::derived] annual shortfall.

---

## 7. IntakeData schema extensions

EMCI intake has: `state, region, employerType, compensationModel, yearsExperience, settingType, apcSupervision`.

**Add to MedCI intake (client-side form + shared/schema):**
- `specialty: "internal-medicine" | "hospitalist" | "nocturnist" | "med-peds" | "outpatient-only" | "inpatient-only" | "mixed"`
- `panelSize: number | null` — outpatient IM; compare to [TBD::mgma-im-panel-median]
- `censusModel: "dedicated" | "rounded" | "service-shared" | "n/a"` — hospitalist
- `encountersPerShift: number | null` — hospitalist
- `shiftPattern: "7-on-7-off" | "block" | "mixed" | "salaried-no-shift" | "other"` — hospitalist
- `nocturnistRatio: number | null` — 0.0 to 1.0, fraction of nights
- `academicRank: "instructor" | "assistant" | "associate" | "full" | "clinical-only" | "n/a"` — for AAMC bench
- `teachingService: boolean` — affects AAMC vs. MGMA benchmark choice

These feed into `buildSystemPrompt` as additional PHYSICIAN CONTEXT lines.

---

## 8. Red-flag definitions (IM/Hospitalist-specific additions)

Keep EMCI red flags that are generic (non-compete radius, termination notice, tail coverage, arbitration, etc.). Remove EM-specific ones (shift differentials absence — that's hospitalist-only). ADD:

- Panel size commitment above [TBD::mgma-im-panel-median] with no pay adjustment
- Census cap without overflow compensation (hospitalist)
- Nocturnist differential below 20% when ≥50% of shifts are nights
- Observation billing counted under different RVU scheme than inpatient (reduces effective pay)
- Post-discharge encounter attribution rules that exclude 48-hour readmissions from RVU credit
- Teaching/admin responsibilities without protected non-clinical time
- Admit-cap clause that enables shift extension without additional pay
- Recalculated wRVU in mid-year based on CMS adjustments that aren't passed through
- APC-supervised patient visits credited below 20% (academic settings often 15%)
- No stipend for quality-reporting work (MIPS, HEDIS) the physician is required to perform

---

## 9. Non-compete block

Reuse EMCI state list verbatim (state law is specialty-agnostic). Append note:

> "IM/Hospitalist-specific: non-compete geographic scope is often written as 'hospital system + affiliated clinics' rather than 'miles.' Parse carefully — a hospital system with 20 locations spans the same effective footprint as a 30-mile radius. Flag this."

---

## 10. JSON schema additions (breaks no existing fields; adds optional fields)

Add under `compensation`:
```
"encounterBased": {
  "admissionFee": <number or null>,
  "subsequentDayFee": <number or null>,
  "dischargeFee": <number or null>,
  "projectedAnnualEncounters": <number or null>,
  "projectedAnnualComp": "<string or null: pseudocode breakdown>",
  "marketComparison": "<string or null>"
} | null,

"shiftBased": {
  "dayRate": <number or null>,
  "nightRate": <number or null>,
  "nocturnistDifferentialPct": <number or null>,
  "annualShifts": <number or null>,
  "projectedAnnualComp": "<string or null>",
  "marketComparison": "<string or null>"
} | null,

"capitation": {
  "pmpmRate": <number or null>,
  "attributedPatients": <number or null>,
  "downsideRisk": "<string or null>",
  "marketComparison": "<string or null>"
} | null
```

Frontend updated to render these conditionally (RUNBOOK §4 client/src/** manual rewrite).

Add under `compensation.rvu`:
```
"panelSizeCommitment": <number or null>,
"censusCap": <number or null>,
"apcSupervisedCreditPct": <number or null>,     // already exists; ensure retained for IM (academic clinics)
```

---

## 11. USER_PROMPT_TEMPLATE

```ts
export const USER_PROMPT_TEMPLATE = `Analyze the following internal medicine or hospitalist physician employment contract. Return your analysis as a single JSON object matching the schema described in your instructions.

CONTRACT TEXT:
{CONTRACT_TEXT}
`;
```

---

## 12. Fallback values when IM_DATA_2026.md cells are still TBD

If Day 2 PM scaffold runs and a `[TBD::cell]` reference is not yet populated, the runner injects a **fallback note** into the prompt instead of a number:

```
BENCHMARK NOTE: Primary comp benchmark for this employer/setting combination is pending Perplexity Day 1 Task 13 verification.
In the current analysis, cite this as "benchmark verification in progress" and recommend the physician check back for an updated report within 48 hours. Do NOT fabricate a number.
```

This protects Lesson #19 integrity — analyzer never ships flawed data just to meet a launch deadline.

---

## 13. Day 2 PM executor checklist

- [ ] Verify `med-contract-content/ops/IM_DATA_2026.md` exists and list TBD vs PASS cells.
- [ ] Open `med-contract-site/server/analysis-prompt.ts` (already scaffolded by rsync + sed pass).
- [ ] Rewrite Header + PHYSICIAN CONTEXT block per §2.
- [ ] Replace benchmark data block per §3.
- [ ] Rewrite getEmployerContext per §4.
- [ ] Rewrite compensation-model adaptation block per §5.
- [ ] Rewrite RVU multiplier analysis block per §6.
- [ ] Extend IntakeData schema per §7 (also update shared/schema.ts and client/src/**/AnalyzerForm.tsx).
- [ ] Update RED FLAGS block per §8.
- [ ] Append non-compete IM/Hospitalist note per §9.
- [ ] Extend JSON output schema per §10.
- [ ] Update USER_PROMPT_TEMPLATE per §11.
- [ ] For each remaining [TBD::] placeholder: resolve to IM_DATA_2026 cell OR insert fallback per §12.
- [ ] Register `site-analysis-prompt` artifact in `state/content-review-day3.md` for Lesson #19 review (row already exists).
- [ ] Commit + push to `med-contract-site`.

---

**Drafted:** 2026-04-22 20:45 EDT
**Executed:** Day 2 afternoon
**Review:** Perplexity (Gate 1, factcheck) + Claude-chat-opus (Gate 2, voice/compliance) before Day 5 launch.
