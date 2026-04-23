# PRICING_DECISIONS — MedContractIntel

**Status:** LOCKED 2026-04-22 evening EDT (per D0-6, owner-confirmed same as blueprint v1.2).
**Authority:** These prices are binding. Do not change without explicit owner or Perplexity directive.

---

## Product-level pricing (retail)

| Product | SKU | Price | Notes |
|---|---|---|---|
| **Contract Analyzer** | `medci-analyzer` | **$97** | Core flagship product — IM + Hospitalist contract analysis with RVU benchmark + red-flag callout + counter-proposal letter |
| **Negotiation Scripts** | `medci-scripts` | **$67** | Templated email + in-person scripts for top 15 IM negotiation moments |
| **wRVU Playbook** | `medci-rvu-playbook` | **$47** | RVU math + conversion-factor drills + threshold engineering for IM/Hospitalist comp |
| **Hospitalist Shift Economics** | `medci-shift-econ` | **$37** | Shift differentials, swing/float/moonlight math, block scheduling implications |
| **Bundle (all 4)** | `medci-bundle` | **$197** | $51 effective discount (22% off stack-price of $248) |

## Launch promotion

| Coupon code | Discount | Applies to | Valid |
|---|---|---|---|
| `LAUNCH` | 20% off | All products except bundle (bundle already discounted) | Day 5 → Day 19 (14 days post-launch) |

## Pricing rationale (for Perplexity reference)

- **Anchor price $97:** matches EMCI analyzer; physician audience price-sensitivity mirrors emergency medicine.
- **$37 shift econ tier:** entry-level, designed for residents + early-career hospitalists to capture first-impression data.
- **$197 bundle:** psychological threshold under $200; 22% stack discount feels generous without devaluing individual SKUs.
- **LAUNCH coupon:** 20% is owner-directed; deeper than typical SaaS launch (10–15%) to drive initial conversions in the 14-day window when social reach spikes.

## What IS NOT priced here (and won't launch Day 5)

- 1:1 consultation ($250+/hr) — deferred to Day 30+ once analyzer has produced enough case data to position consultation as "upgrade path"
- Group/institution licensing — deferred indefinitely; not in first 90 days
- White-label or affiliate tier — deferred indefinitely

## Stripe product/price/payment-link creation

Spec file: `INBOX/stripe/products-prices-spec.json` (pre-validated JSON)
Executed: D2-5 via Stripe MCP
Captured IDs: `state/site.md` Stripe product/price ID table + `state/stripe-ids.md` (to be created Day 2)

## Changes to this file

Any change requires explicit owner directive in `CLAUDE_RESPONSE.md` OR Perplexity directive in `COMPUTER_RESPONSE.md`. Append a "## Change log" section at the bottom of this file with timestamp + authority + rationale for any revision.
