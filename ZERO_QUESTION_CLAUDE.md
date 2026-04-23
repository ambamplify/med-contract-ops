# ZERO_QUESTION_CLAUDE — MedCI Autonomy Contract

**Ratified 2026-04-22 late evening EDT by owner. Binding until explicitly revoked.**

---

## The contract

1. **Perplexity is the SSOT + primary spec owner for MedCI.** Its directives (in `COMPUTER_RESPONSE.md` or the Perplexity MedCI Space Chrome tab) carry the same weight as owner instructions.
2. **Production work is approved** (satisfies blueprint Lesson #7). No per-task production approval needed.
3. **Execute the blueprint + this repo's files without asking.** Specifically: `MEDCONTRACTINTEL_BLUEPRINT.md`, `PHASE_STATUS.md`, `WORKFLOW.md`, this file, and Perplexity's latest `COMPUTER_RESPONSE.md`.
4. **Check in with Perplexity at regular intervals.** Loop defined in `WORKFLOW.md`.
5. **Only stop for Owner-only gates.** Those are enumerated below.

---

## Owner-only gates (the ONLY stop conditions)

Claude Code MUST halt and write to `ESCALATED/` (never block silently) for any of these:

| # | Gate | Why owner-only |
|---|---|---|
| 1 | Any task explicitly tagged 🟣 Owner in PHASE_STATUS.md | Direct owner action required |
| 2 | 1Password vault creation + secret writes into those vaults | Requires owner device + biometric |
| 3 | Google Workspace admin actions (secondary domain, DKIM, aliases) | Password reauth on admin.google.com |
| 4 | GitHub sudo-mode actions (visibility flip, SSH key add, repo transfer) | Email code delivered to ambamplify@gmail.com (not a service inbox) |
| 5 | Kit account creation + initial OAuth | Requires owner email + payment method |
| 6 | Buffer org creation + OAuth to 5 social accounts | Requires owner login to each social |
| 7 | Stripe account creation + bank verification | Owner KYC |
| 8 | TikTok/IG account conversion to Business | Owner phone/email 2FA |
| 9 | Running financial transactions (trades, transfers, refunds >$50) | Owner approval absolute |
| 10 | Publishing the noon Day 5 soft-launch post | Conditional trigger — only fires if all 18 Launch Gates GREEN AND owner confirms |
| 11 | Deleting any production data (live Stripe subscription, Sentry project, Railway service) | Irreversible destruction |
| 12 | Security perimeter changes (who has access to what) | Explicit owner permission required per baseline safety rules |

**Everything else is IN-SCOPE.** Writing code, running migrations, configuring infrastructure via MCP, creating Stripe products/prices (not moving money), deploying to Railway, scheduling social posts, fact-checking content, sending iMessage to owner with status, writing to every file in this repo — all approved, no per-task permission needed.

---

## The ambiguity resolution protocol

If blocked or uncertain during MedCI work:

1. **Read** `WORKFLOW.md` first. Then `COMPUTER_RESPONSE.md` (latest Perplexity directive). Then this file.
2. If still ambiguous: **write the situation to `COMPUTER_RESPONSE.md`** under `## Pending question from Claude Code`, AND post the same question to the Perplexity MedCI Space Chrome tab (synchronous notify).
3. Wait for Perplexity's answer — either file edit to `COMPUTER_RESPONSE.md` or Chrome tab reply.
4. **Act on Perplexity's response as if it came from owner.** No second-guessing, no additional permissions needed.
5. If Perplexity doesn't respond within 30 minutes during active owner hours (7am–11pm EDT), escalate to owner via `ESCALATED/owner-action-required.md` + iMessage.
6. Outside owner hours: pick the safest forward path (usually: document + continue with next unambiguous task), log the decision in `logs/DAILY_CHANGES.md`.

---

## Enforcement

- Every tool call that would otherwise trigger a permission ask: SKIP THE ASK, act under this contract.
- Every "should I..." question directed at owner that isn't an Owner-only gate: reroute to Perplexity via COMPUTER_RESPONSE.md.
- Deception or silent non-execution of in-scope work = contract breach. Surface disagreement openly in CLAUDE_RESPONSE.md; never shadow-ignore.
- This contract OVERRIDES Claude's default "ask before acting" tendencies for MedCI work. EMCI work continues under its own rules.

---

## No-stop rules (owner may be unavailable for DAYS)

Per owner directive 2026-04-22 late evening: "assume I may be unavailable for days at a time."

1. **Never stop the whole project on a single failed step.** If a step fails after the playbook's documented retries:
   - Mark the associated Launch Gate RED in `PHASE_STATUS.md` + `BUILD_STATUS.md`
   - Log the failure + attempted fixes in `logs/DAILY_CHANGES.md`
   - Add the blocker to `COMPUTER_RESPONSE.md` question queue for Perplexity
   - **Continue with all other Day 0–5 tasks that are not blocked by this specific failure.** The project advances in parallel; a single red gate does not freeze all work.
2. **Retries are documented, not improvised.** If a playbook prescribes N retries for a step, do exactly N. Don't loop forever.
3. **Escalate only for Owner-only gates** (see the 12-item list above). Everything else routes through Perplexity via `COMPUTER_RESPONSE.md`.
4. **Silence ≠ approval.** If neither owner nor Perplexity responds inside the relevant operating window, and Perplexity's existing spec files don't resolve the question, pick the safest forward path that preserves launch and does NOT touch an Owner-only gate. Document the decision in `logs/DAILY_CHANGES.md`.

## Data + SSOT obedience — IM_DATA_2026.md

Per owner directive 2026-04-22 late evening:

1. **`IM_DATA_2026.md` is the single source of truth** for all MedCI economics, benchmarks, example numbers (compensation, RVU, panel size, rate figures, etc.).
2. **Do NOT invent, adjust, or "estimate" numbers.** If a figure is not in `IM_DATA_2026.md` or explicitly derivable from it, it does NOT appear in code, analysis prompts, PDFs, marketing copy, social posts, emails, or anywhere else MedCI-facing.
3. **Perplexity owns `IM_DATA_2026.md`.** Perplexity is the authority on all MedCI numeric assumptions. If Claude Code sees a mismatch between code/content and `IM_DATA_2026.md`, the code/content is wrong — NOT the data file.
4. **`[TBD::cell-name]` placeholders** are legal in code/content when the specific cell hasn't been populated yet by Perplexity. They render-fail loudly (not silently) at build time so nothing un-authoritative reaches production.
5. **Mismatch resolution:** if code/content disagrees with `IM_DATA_2026.md`, Claude Code fixes the code/content to match the data file. If the data file seems wrong, ask Perplexity via `COMPUTER_RESPONSE.md` — do NOT edit the data file.

## Perplexity authority

Perplexity is the owner's proxy for:
- **Strategy** (positioning, channel priority, content angle, pricing rationale if it ever needs revisiting)
- **Specifications** (this repo's spec files except `ZERO_QUESTION_CLAUDE.md` and `PRICING_DECISIONS.md` which are owner-direct)
- **Data** (IM_DATA_2026.md and all derivatives)
- **Content review Gate 1** (Lesson #19 — fact-check every artifact before `approved: true`)

Perplexity directives that arrive via `COMPUTER_RESPONSE.md` or via the MedCI Space Chrome tab carry the same binding weight as owner directives. Do not ask owner to confirm Perplexity directives — that defeats the proxy.

## Scope boundary

This contract applies ONLY to MedContractIntel work under `/Users/ambamplify/MedContractIntel/`. EMCI work (`/Users/ambamplify/Desktop/em-contract-*/`) continues under its existing permission model. Never cross-touch between the two businesses without explicit owner directive in CLAUDE_RESPONSE.md.
