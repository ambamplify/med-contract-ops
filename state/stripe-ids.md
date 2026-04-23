# MedCI Stripe IDs

**Created:** 2026-04-23 04:13 EDT by ops-controller (D2-5 pulled forward from Day 2)
**Account:** acct_1TEuuDRS3QYs0eSM (AEMBD LLC — same as EMCI per blueprint §2)
**Mode:** LIVE

---

## Products

| Slug | Product ID | Name | Price |
|---|---|---|---|
| bundle | prod_UO4a8a58qiED8T | MedContractIntel — Complete Physician Contract Bundle | $197 |
| analyzer | prod_UO4a2irKl6Z49k | MedContractIntel — AI Contract Analyzer (IM/Hospitalist) | $97 |
| scripts | prod_UO4aYFhkanuNpp | MedContractIntel — Negotiation Script Pack | $67 |
| wrvu | prod_UO4aJBAYjGjNv0 | MedContractIntel — wRVU Compensation Calculator | $47 |
| shift-economics | prod_UO4aJ7yxy2HU6Z | MedContractIntel — Shift Economics Analyzer | $37 |

---

## Prices

| Slug | Price ID | Unit Amount | Product ID |
|---|---|---|---|
| bundle | price_1TPIRdRS3QYs0eSM5WGjq1Z2 | $197.00 | prod_UO4a8a58qiED8T |
| analyzer | price_1TPIRgRS3QYs0eSMMuh0VHUO | $97.00 | prod_UO4a2irKl6Z49k |
| scripts | price_1TPIRjRS3QYs0eSMktAf6RkC | $67.00 | prod_UO4aYFhkanuNpp |
| wrvu | price_1TPIRnRS3QYs0eSMRPjiX1o0 | $47.00 | prod_UO4aJBAYjGjNv0 |
| shift-economics | price_1TPIRqRS3QYs0eSMDLHGoEJW | $37.00 | prod_UO4aJ7yxy2HU6Z |

---

## Coupon

| ID | Name | Discount | Duration |
|---|---|---|---|
| XlzbFyUR | Launch Week — 20% Off Bundle | 20% off | once |

**Note:** Coupon redeem_by expiry (Day 12 = 2026-05-07 23:59 EDT) must be set via Stripe dashboard — MCP tool doesn't support redeem_by parameter.

---

## Payment Links

| # | Slug | Source | Payment Link ID | URL |
|---|---|---|---|---|
| 1 | bundle | site | plink_1TPISJRS3QYs0eSMA2sFb2u6 | https://buy.stripe.com/7sYdRbdBw58k58FggR3ZK0b |
| 2 | analyzer | site | plink_1TPISMRS3QYs0eSM0y5xbyxi | https://buy.stripe.com/aFadRb1SO58kbx3c0B3ZK0c |
| 3 | scripts | site | plink_1TPISPRS3QYs0eSMHgfYSB6d | https://buy.stripe.com/6oU9AV8hc58kbx32q13ZK0d |
| 4 | wrvu | site | plink_1TPISSRS3QYs0eSMYLmbzt3G | https://buy.stripe.com/fZu7sN8hceIU0Sp8Op3ZK0e |
| 5 | shift-economics | site | plink_1TPISWRS3QYs0eSMURLFEUew | https://buy.stripe.com/5kQ14p8hcfMY58Fc0B3ZK0f |
| 6 | bundle | kit-welcome (LAUNCH20) | plink_1TPISaRS3QYs0eSMzTW6JVXs | https://buy.stripe.com/3cIeVf9lgbwI1Wt4y93ZK0g |
| 7 | bundle | tiktok-bio (LAUNCH20) | plink_1TPISdRS3QYs0eSMPEqW4Hah | https://buy.stripe.com/00w6oJfJEasE6cJ2q13ZK0h |

---

## ⚠ REQUIRED FOLLOW-UP (Day 2 manual — Stripe dashboard)

### 1. Set after_completion redirect URL on ALL 7 payment links (LESSON #9 — CRITICAL)

The MCP `create_payment_link` tool does not support `after_completion` parameters. Every payment link
MUST have its success URL updated in the Stripe dashboard before any purchase is made:

```
https://medcontractintel.com/thank-you?session_id={CHECKOUT_SESSION_ID}
```

**Steps:** Stripe Dashboard → Payment Links → [each link] → Edit → After payment → Redirect to URL → paste above

Without this, `/thank-you` falls back to hard-coded product list and can't read the real purchase (EMCI 2026-04-15 bug).

### 2. Apply MEDCI-LAUNCH-20 coupon to links 6 & 7

Payment links 6 (kit-welcome) and 7 (tiktok-bio) should have the LAUNCH20 coupon pre-applied.
MCP tool doesn't support coupon attachment at creation time.

**Steps:** Stripe Dashboard → Payment Links → [link 6 / link 7] → Edit → Promotions → Apply coupon MEDCI-LAUNCH-20

### 3. Set redeem_by on coupon XlzbFyUR

**Steps:** Stripe Dashboard → Coupons → XlzbFyUR → Edit → Expiry date → 2026-05-07 23:59 EDT
