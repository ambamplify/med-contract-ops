# MedContractIntel — Claude Chat (Opus) PDF Content Prompts

**Created:** 2026-04-23 owner session
**Purpose:** Paste each prompt into Claude Chat (claude.ai, Opus model) to produce full text content for the 4 MedContractIntel product PDFs. Each output is the Gate 2 draft (Claude-chat-opus review). Perplexity runs Gate 1 fact-check after. Both gates must log PASS in `state/content-review-day3.md` before PDFs are generated and shipped.

**Brand:** MedContractIntel (medcontractintel.com) — NOT "IM Contract Intel"
**Primary audience:** Hospitalist physicians (employed, 7-on/7-off, nocturnist)
**Secondary audience:** Outpatient Internal Medicine physicians (employed group or private practice)

---

## Prompt 1 — Red Flag Checklist (free giveaway, calculator opt-in)

```
You are writing a product PDF for MedContractIntel (medcontractintel.com). The brand voice is direct, data-forward, and respects the physician's intelligence. Zero fluff. The audience is Internal Medicine physicians — primarily hospitalists, secondarily outpatient IM physicians in private or group practice.

You are producing the full text for: **The MedContractIntel Physician Contract Red Flag Checklist — 15 Provisions That Cost Internal Medicine Physicians Money, Mobility, and Leverage**

This is a 2-page free giveaway PDF (delivered after calculator opt-in). Model the structure exactly on the EMCI version below, but replace all EM-specific content with IM/hospitalist-specific content.

---
EMCI VERSION STRUCTURE (for reference only — do NOT copy any text):
- Intro paragraph explaining contracts are drafted by employer's counsel
- 15 numbered red flags, each with a title and 2–3 sentence explanation
- Each flag has a severity badge: CRITICAL, HIGH, or MODERATE
- Footer: "For informational purposes only. Does not constitute legal advice."
- Two pages
---

Write the MedContractIntel version using this structure:

**Intro paragraph** (~60 words): Internal Medicine physicians — whether you practice as a hospitalist, in an employed outpatient group, or in a private practice — face contracts drafted by the employer's legal team to protect the employer. The 15 provisions below are the ones most likely to cost you money, mobility, or leverage over the life of the agreement. Check each against your contract.

**15 Red Flags** — write each with a title and 2–3 sentence explanation. Assign severity (CRITICAL / HIGH / MODERATE). Use accurate IM and hospitalist contract specifics. Do not fabricate specific dollar figures; use ranges where appropriate and note the source type (e.g., "MGMA data," "SHM benchmarks"). The 15 should cover:

1. wRVU rate with no named benchmark — for outpatient IM, the multiplier with no MGMA or ACP reference anchor
2. Compensation model not specified (salary vs. wRVU vs. capitation vs. hybrid) — ambiguity lets employer switch models at renewal
3. Panel size with no cap or no productivity adjustment above cap — outpatient IM physicians with uncapped panels carry unpaid workload
4. HEDIS/quality bonus denominator controlled by employer — quality bonus targets set on metrics the physician can't influence
5. Advance draw reconciliation without a floor — hospitalists on production-based draws risk an annual true-up payback obligation
6. No minimum shift or census guarantee for hospitalists — employer controls income by controlling admissions or scheduling
7. Termination without cause under 90 days — leaves no time to credential elsewhere or relocate
8. Claims-made malpractice with no tail commitment — tail cost for IM can be $15,000–$40,000 on exit
9. Non-compete over 10 miles or 2 years in states where enforced — enforcement varies sharply by state; NJ: 1-year limit; CA: void
10. Nocturnist differential below 20% — industry standard for hospitalist nocturnist differential is 20–25%; below 15% is below market
11. Call coverage — in-hospital or remote, compensated or uncompensated — ambiguous language shifts unpaid call risk onto the physician
12. Moonlighting restriction that blocks locum work — restricts IM hospitalists from supplemental locum income ($2,200–$2,900/shift market rate)
13. Sign-on bonus clawback over 2 years or full repayment basis — standard is pro-rata; full repayment is aggressive
14. Productivity bonus threshold set above MGMA 75th percentile production — structurally unreachable for median performance
15. Stark Law / self-referral language touching hospital-affiliated services — any clause that conditions compensation on referral patterns requires attorney review

End with: "For informational purposes only. Does not constitute legal advice. Review any contract with a qualified physician-contract attorney before signing. © MedContractIntel. medcontractintel.com"

Output the full text ready to be formatted into a PDF. No markdown headers — use plain text with numbered items and severity labels in [CRITICAL] / [HIGH] / [MODERATE] format.
```

---

## Prompt 2 — Negotiation Script Pack ($67)

```
You are writing a product PDF for MedContractIntel (medcontractintel.com). Brand voice: direct, data-forward, zero condescension, zero fluff. The audience is Internal Medicine physicians — primarily hospitalists, secondarily outpatient IM in private or group practice. These are intelligent professionals who have been kept in the dark about compensation data, not people who need motivation or inspiration.

You are producing the full text content for: **The MedContractIntel Negotiation Script Pack — 6 Word-for-Word Scripts, 6 Email Templates, and an Objection-Handling Guide for Internal Medicine Physicians**

Price: $67. This is a production-quality product document.

---
MODEL THIS STRUCTURE on the EMCI Negotiation Script Pack, but all content must be IM/hospitalist-specific:

**Disclaimer** (required, first page after cover):
"These scripts are for educational and informational purposes only. They do not constitute legal advice. Consult a licensed attorney in your state for advice specific to your contract. Compensation data throughout this pack is drawn from publicly available sources including MGMA Physician Compensation and Production Reports, SHM State of Hospital Medicine Survey, and ACP compensation data. Your situation will vary."

**Table of Contents**
1. Introduction — Why Most IM Physicians Negotiate Poorly
2. Script 1 — Requesting a wRVU Multiplier Increase at Renewal (outpatient IM)
3. Script 2 — Countering "This Contract Is Non-Negotiable"
4. Script 3 — Negotiating a Panel Size Cap and Productivity Adjustment
5. Script 4 — Responding to "The Hospital Budget Doesn't Allow For More"
6. Script 5 — Negotiating a Nocturnist Differential or Shift Differential (hospitalist)
7. Script 6 — Requesting an Annual Compensation Review Mechanism
8. Objection-Handling Quick Reference
9. Pre-Negotiation Preparation Checklist

---

**Introduction** (~600 words):
Write this in the voice of an experienced advisor speaking directly to an IM physician. Cover:
- The three things most IM physicians don't have going into a contract conversation: the language, the data, the objection prep
- Why "I feel underpaid" fails and "MGMA shows the 50th percentile for outpatient IM at X" works
- The specific disadvantage of IM vs. EM: IM contracts are longer-term, more complex (quality bonuses, panel attribution, capitation risk), so the stakes of a poor negotiation compound over years
- One core principle: you are not asking for a favor, you are re-anchoring to market

**Script 1 — wRVU Multiplier Increase (outpatient IM)** (~500 words):
The scenario: physician is at renewal, current multiplier is below MGMA 50th percentile for outpatient IM. Write the full word-for-word conversation — what to say when you walk in, how to present the data, how to make the specific ask, what to say if they push back. Include a follow-up email template.

**Script 2 — Countering "This Contract Is Non-Negotiable"** (~400 words):
This is the most common deflection. Write the exact language to redirect from the deflection back to data. Include the psychological reframe (non-negotiable means "we haven't moved yet"), and the specific follow-on ask. Include email template.

**Script 3 — Panel Size Cap and Productivity Adjustment** (~450 words):
Scenario: outpatient IM physician has a panel above MGMA median with no cap and no additional compensation above a certain threshold. Write the script for requesting either a panel cap or a per-patient-above-threshold payment. Include the data anchor. Include email template.

**Script 4 — Responding to "The Hospital Budget Doesn't Allow For More"** (~400 words):
The hospital-employed hospitalist version of the "non-negotiable" deflection. Write the exact language to redirect from institutional budget constraints to market benchmarks. Include the data pivot (SHM hospitalist benchmarks). Include email template.

**Script 5 — Nocturnist Differential (hospitalist)** (~450 words):
Scenario: hospitalist is being offered a nocturnist schedule with no differential, or a differential below 15%. Write the script for requesting a 20–25% differential with the industry benchmark anchor. Include what to say if they offer a one-time bonus instead of a rate adjustment. Include email template.

**Script 6 — Annual Compensation Review Mechanism** (~400 words):
Scenario: physician wants to add language requiring an annual compensation review tied to MGMA data, rather than discretionary employer adjustment. Write the script and the specific contract language to request. Include email template.

**Objection-Handling Quick Reference** (table format, plain text):
8 most common employer objections for IM/hospitalist physicians + the exact response to each. Cover: "The market is soft," "We pay everyone the same," "You just started here," "The MGMA data doesn't apply to us," "We can't change the standard contract," "Quality bonuses cover the gap," "You have great benefits," "This is just how hospital employment works."

**Pre-Negotiation Preparation Checklist**:
12-item checklist of what to have ready before the negotiation conversation: current contract terms, MGMA percentile position, panel size vs. group median, quality bonus structure and your actual performance vs. targets, tail coverage terms, non-compete geography mapped, comparable offers if any, etc.

End with full disclaimer and copyright: "© MedContractIntel. medcontractintel.com. For informational and educational purposes only. Not legal advice."

Write the complete text for all sections. Use plain prose — no markdown formatting. Write at the level of a smart physician reading carefully.
```

---

## Prompt 3 — wRVU Playbook ($47)

```
You are writing a product PDF for MedContractIntel (medcontractintel.com). Brand voice: direct, data-forward, no fluff, maximum respect for the physician's intelligence. Audience: Internal Medicine physicians — primarily outpatient IM in employed or private-group settings, secondarily hospitalists who have RVU components in their contracts.

You are producing the complete text content for: **The MedContractIntel wRVU Playbook — Understand Your Pay. Know Your Worth. Negotiate What You've Earned.**

Price: $47. This is a full product document, not a summary.

Model the structure on the EMCI RVU Playbook (5 parts, multiple chapters), but all content must be specific to Internal Medicine outpatient and employed physician contracts. Do NOT use EM CPT codes, ACEP data, or EM-specific framing.

---

**Disclaimer** (required):
"This guide is for educational purposes only. It does not constitute legal, financial, or employment advice. Consult a licensed attorney and/or financial advisor for guidance specific to your situation. Compensation data cited throughout reflects publicly available survey and regulatory sources including MGMA, SHM, ACP, and CMS Medicare Physician Fee Schedule. Individual contract outcomes will vary."

**Table of Contents:**

Part I — The Foundation
1. The Information Gap: Why IM Physicians Negotiate Blind
2. wRVU Fundamentals: The Only Explanation You Need
3. The Compensation Equation: How Your Pay Is Actually Calculated

Part II — The Market
4. Benchmarking Your Contract: Are You Being Paid Fairly?
5. The Employer Model: The Margin Between What They Collect and What You Earn
6. How Reimbursement Works for IM: Medicare, Commercial, Medicaid, and MA
7. Reading Your Contract's Compensation Schedule

Part III — The IM-Specific Mechanisms
8. The Panel Size Trap
9. The Quality Bonus That Isn't
10. The Compensation Model Switch

Part IV — Action
11. Building Your Leverage File: A 90-Day Action Plan

Appendices:
A. wRVU Reference Table — Key IM and Hospitalist CPT Codes (2026 Medicare Rates)
B. Benchmark Reference Card
C. Contract Red Flag Quick Reference
D. State Non-Compete Enforceability Summary (focus on high-density IM states: NJ, NY, CA, TX, FL, IL, PA, OH)
E. Glossary of Contract Terms
F. Recommended Resources

---

Write the complete text for each chapter. Length guidance:
- Chapters 1–3: ~800–1,000 words each
- Chapters 4–7: ~600–900 words each
- Chapters 8–10: ~500–700 words each
- Chapter 11: ~800 words with a specific week-by-week 90-day action plan
- Appendix A: List the most important IM CPT codes with their 2026 Medicare wRVU values — use real CMS 2026 values. Include: 99213, 99214, 99215 (outpatient E&M); 99221, 99222, 99223 (initial hospital care); 99231, 99232, 99233 (subsequent hospital care); 99238, 99239 (discharge); G2211 (complexity add-on). If you are uncertain of the exact 2026 value for any code, state "verify against 2026 CMS PFS" rather than fabricating.
- Appendix B: MGMA 2025 IM compensation benchmarks (25th / 50th / 75th percentile total compensation and wRVU production for outpatient IM and hospitalists). If you are uncertain of the exact figures, use ranges and note "verify against MGMA 2025 Physician Compensation and Production Report."

Key concepts to cover accurately:
- The difference between total RVU, work RVU (wRVU), practice expense RVU, and malpractice RVU — and why only wRVUs appear in compensation contracts
- The 2026 CMS conversion factor — if uncertain, note source and instruct reader to verify
- How the dollar-per-wRVU multiplier in an IM contract translates to annual income at different production levels
- Panel size as a hidden wRVU ceiling: how a large panel with 99214-weighted visits translates to a theoretical annual wRVU range
- The HEDIS/quality bonus problem: how targets are often set at the system level and why physician-level performance doesn't linearly produce the bonus
- The compensation model switch risk: employer moves from salary to production at renewal without corresponding rate increase
- The advance draw reconciliation trap for hospitalist production contracts

End with: "© MedContractIntel. medcontractintel.com. All content for educational purposes only. Not legal or financial advice."

Write the complete text for every section listed. If you reach a data point you cannot verify with confidence, write "[VERIFY: description of what to verify]" as a placeholder rather than fabricating a number.
```

---

## Prompt 4 — Hospitalist Shift Economics Analyzer ($37)

```
You are writing a product PDF for MedContractIntel (medcontractintel.com). Brand voice: direct, data-forward, no fluff. Audience: Hospitalist physicians — employed hospitalists at hospitals and health systems, nocturnists, and 7-on/7-off block schedulers. This is the audience that most needs this content.

You are producing the complete text content for: **The MedContractIntel Hospitalist Shift Economics Analyzer — The Math Behind 7-on/7-off, Nocturnist Pay, Admission Fees, and the Gap Nobody Talks About**

Price: $37. Focused, practical product — not a textbook. The most useful thing a hospitalist could read before their first contract negotiation.

---

**Disclaimer** (required):
"This guide is for educational and informational purposes only. It does not constitute legal, financial, or employment advice. Numbers in this guide reflect publicly available survey data from SHM, MGMA, and CMS Medicare data, and are provided for illustrative purposes. Your contract terms and market will vary. Consult a licensed attorney and/or financial advisor before making contract decisions."

---

**Structure — write complete text for each section:**

**Introduction: The Information Gap** (~500 words)
You completed residency, you are running a hospital service, managing admissions. Someone handed you a contract. What you don't know: what the hospital collects on those same admissions, what the math looks like across a full schedule year, what "7-on/7-off" means in terms of billable encounters per year, and what the difference is between your annual income at the 25th vs. 75th SHM benchmark percentile. This guide covers all of it.

**Part 1 — The 7-on/7-off Schedule: The Math That Determines Your Real Compensation** (~700 words)
Cover:
- How many working days 7-on/7-off produces in a year (calculate from 26 blocks × 7 days — note if uncertain)
- How to calculate your effective hourly rate from an annual salary or per-shift rate
- The admission volume question: census reality by Day 7 of a block vs. Day 1
- The per-admission fee model: flat per-admission fee structures and when they help vs. hurt
- The Day 1 vs. Day 7 admission weighting problem on production contracts

**Part 2 — Nocturnist Pay: The Differential They Don't Offer Until You Ask** (~600 words)
Cover:
- What nocturnist means in practice (7 PM–7 AM, varies by system)
- Industry benchmarks for nocturnist differential (SHM data — write [VERIFY: SHM nocturnist differential benchmark] if uncertain of exact figure)
- How to calculate the annual income difference between a 15% and a 25% differential on a given base salary
- The "you get used to nights" trap
- The correct ask with the benchmark anchor

**Part 3 — Two Revenue Streams for Every Hospitalist Encounter** (~600 words)
Cover:
- The professional fee vs. facility fee split for hospital medicine
- What the hospital collects in facility fees on an admission your team manages
- What the physician professional fee represents as a percentage of total revenue
- Why this information is strategically useful for compensation conversations
- Where this data is publicly available (CMS cost reports, Medicare PFS)
- Do not fabricate specific facility fee dollar amounts — use ranges, point to public sources

**Part 4 — Benchmark Yourself: 25th, 50th, or 75th Percentile?** (~500 words)
Cover:
- SHM State of Hospital Medicine Survey benchmark structure
- How to calculate your percentile position
- The compounding math of percentile gap over a 5-year career
- Private-group vs. hospital-employed hospitalist compensation difference

**Part 5 — The Contract Terms That Move the Number Most** (~500 words)
Five specific contract terms, in order of financial impact, for hospitalists:
1. Base salary vs. production-only model
2. Nocturnist differential percentage
3. Shift guarantee minimum
4. Tail coverage responsibility on exit
5. Non-compete geography

**Closing Action Section** (~300 words):
Three things to do before you sign:
1. Pull your offer against SHM benchmarks
2. Calculate your effective hourly rate across a full working-day year
3. Identify which of the 5 contract terms above is most below-market in your specific offer

End with: "© MedContractIntel. medcontractintel.com. For educational purposes only. Not legal or financial advice."

---

Write complete text for all sections. Where you cite a specific number (differential percentages, SHM benchmarks, CMS rates), either use accurate publicly available data or write "[VERIFY: source and figure description]" rather than fabricating. The physician audience will notice incorrect data immediately.
```

---

## Review workflow (Lesson #19)

After Claude Chat produces content for each PDF:

1. **Gate 1 (Perplexity):** Paste content into Perplexity MedCI Space with prompt: "Fact-check this MedContractIntel PDF draft against IM_DATA_2026.md and publicly available 2026 sources. Flag any unverifiable stat, any [VERIFY] placeholder still open, and any EM-specific content that slipped through. Write PASS or FAIL with specific notes for each section." Log result in `state/content-review-day3.md`.

2. **Gate 2 (Claude Chat Opus — this session):** The Claude Chat session that produced the content IS the Gate 2 review. Log as PASS with session date.

3. **Advance to approved:** Only after both gates logged as PASS in `state/content-review-day3.md`. Claude Code then generates the actual PDF files.
