# Stripe Products / Prices Spec — Drop-in for Day 2

## Purpose

`products-prices-spec.json` is the complete input contract for the Day 2 Stripe-products-creation block. Drafted Day 0 evening autonomously so Day 2 can execute without re-deriving copy, pricing, or metadata.

## Day 2 runner — what it does

1. **Verify Stripe account scope**
   - `mcp__7cf0a85b-...__get_stripe_account_info` — confirm MedCI account (NOT EMCI account).
   - If missing: escalate to owner (Stripe account setup is a Day 1/2 owner task if not already done).

2. **Test mode first**
   - Create all 5 products + prices in **test mode**.
   - Create coupon `MEDCI-LAUNCH-20` with auto-computed `redeem_by` epoch (Day 12 end-of-day).
   - Create all 7 Payment Links per the `payment_links[]` array.
   - Save each `product_id`, `price_id`, and Payment Link URL to 1Password vault `MedCI — Stripe` (owner creates vault Day 1 — ESCALATED #3).

3. **Wire into site**
   - Write `med-contract-site/server/product-data.ts` (or the EMCI-equivalent) with the 5 product records.
   - Each product grid card on `/` and each dedicated product page links to its Payment Link URL.
   - Kit welcome email uses the bundle Payment Link with `coupon=MEDCI-LAUNCH-20` appended.

4. **Live cutover Day 4 late afternoon**
   - Only after Day 4 end-to-end dry run passes: flip create to live mode.
   - Archive test artifacts; update 1P with live IDs.
   - Update site's product-data.ts with live Payment Link URLs.
   - Commit + push.

## Pricing lock (per D0-6, owner confirmed 2026-04-22 evening)

| Slug | Display | Stripe unit_amount |
|---|---|---|
| bundle | $197 | 19700 |
| analyzer | $97 | 9700 |
| scripts | $67 | 6700 |
| wrvu | $47 | 4700 |
| shift-economics | $37 | 3700 |

**Note on $32 vs $37:** PHASE_STATUS D0-6 task label cites "$32" but the confirmation line resolves to "$37". Spec uses **$37** as canonical. If owner wants $32, they can edit this spec before Day 2 runner fires.

## Sanity checks the Day 2 runner MUST perform before `create_product`

- [ ] `get_stripe_account_info` returns MedCI account, NOT EMCI.
- [ ] `list_products` returns 0 existing products (fresh account) OR owner confirms re-creation is intended.
- [ ] `/Users/ambamplify/MedContractIntel/med-contract-ops/INBOX/stripe/products-prices-spec.json` parses as valid JSON.
- [ ] 1P vault `MedCI — Stripe` exists and is writable (owner ESCALATED #3 done).
- [ ] If any check fails: halt, write diagnosis to `ESCALATED/day2-stripe-blocker-YYYY-MM-DD.md`.

## Open items (flag to owner if still unresolved Day 2 morning)

- **Stripe account creation**: is the MedCI Stripe account created? Connected bank? Business details filed?
- **1P vault `MedCI — Stripe`**: exists? Perplexity service account has write access?
- **Tax code `txcd_10000000`**: generic digital goods. Owner confirms this is correct for MedCI jurisdiction (Delaware LLC, NJ operations).

Drafted: 2026-04-22 20:25 EDT
Executed: Day 2 Thursday 2026-04-24 (autonomously by Claude Code or ops-controller)
