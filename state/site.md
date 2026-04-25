# MedCI Site State (med-contract-site)

**Last updated:** 2026-04-22 23:15 EDT
**Owner:** Claude Code (autonomous writes) — Perplexity reads

---

## Repo

- GitHub: `ambamplify/med-contract-site`
- Local: `/Users/ambamplify/MedContractIntel/med-contract-site`
- Latest commit: `59becb7` (brand palette migration) on main
- Previous: `47d731a` (initial scaffold from EMCI + rebrand)

## Scaffold status

| Layer | Status | Notes |
|---|---|---|
| Cloned from EMCI | 🟢 done | 2026-04-22 21:49 EDT |
| String/logo rebrand | 🟢 done | EMCI → MedCI, ECI brand marks swapped |
| Analysis prompt rewrite (IM/Hospitalist) | 🟢 done | `analysis-prompt.ts` — 13 sections, `[TBD::cell]` placeholders waiting on IM_DATA_2026.md |
| Legal pages (privacy/terms/refund/disclaimer/dmca) | 🟢 done | In `public/pages/` — 5 drop-ins |
| Brand palette migration | 🟢 done | Green primary + gold + trust-blue accent (commit 59becb7) |
| Tailwind brand tokens | 🟢 exposed | `brand.*`, `gold`, `trust`, `cream`, `ink`, `muted` |
| CSS var legacy names (`--navy`, `--teal`, etc. still in HTML inline styles) | 🟡 non-blocking | Day 2 cleanup to rename semantically |
| Stripe product ID wiring | 🔴 not yet | Waits on D2-5 Stripe MCP creation |
| Analyzer prompt IM_DATA_2026.md cell replacement | 🟡 ready to execute | IM_DATA_2026.md populated 2026-04-25 16:16 EDT (230 lines, 166 cells, sed artifacts cleaned). Replace `[TBD::cell]` placeholders in `analysis-prompt.ts` with values from IM_DATA. |
| 4 IM PDFs rebuilt with new palette | 🔴 not yet | D2-8 |
| Railway deploy | 🔴 not yet | D2-9/10 |
| Cloudflare A/AAAA bind | 🔴 not yet | D2-11 |
| Production Stripe webhook | 🔴 not yet | D2-13 |
| Smoke test #1 (homepage / calculator / analyzer / test checkout) | 🔴 not yet | D2-12 |
| Smoke test #2 (full funnel) | 🔴 not yet | D2-16 |

## Known bugs to watch (from EMCI lessons)

1. **Lesson #2:** `cp -r server/pdfs dist/server/pdfs` MUST be in build script — D2-3 verify
2. **Lesson #3:** Stripe client MUST lazy-init inside webhook handler, NOT at module top — D2-4 verify
3. **Lesson #10:** Kit email 1 links directly to PDF URL, NOT a form URL — D2-14
4. **Lesson #13:** `/checklist-thank-you` is a separate route from `/thank-you` — D2-6
5. **Lesson #9:** Stripe payment link success URLs include `?session_id={CHECKOUT_SESSION_ID}` — D2-7

## Environment variables (to be set D2-9)

From `INBOX/site-scaffold/env-template.example`:

- `STRIPE_SECRET_KEY` — live mode key (owner pulls from 1Password)
- `STRIPE_WEBHOOK_SECRET` — captured D2-13 after webhook registered
- `RESEND_API_KEY` — after Resend domain verified
- `KIT_API_KEY` — after owner creates Kit account
- `ANTHROPIC_API_KEY` — owner (reuse EMCI key or create MedCI-specific per blueprint §5.2)
- `SENTRY_DSN` — after owner creates Sentry project
- `DATABASE_URL` — Railway-provided Postgres
- `NODE_ENV=production`
- `SITE_URL=https://medcontractintel.com`

## Deploy URL

- Staging (Railway auto-assigned): TBD — generated D2-9
- Production: `https://medcontractintel.com` — after D2-11 DNS bind

## Stripe product/price IDs

To be populated D2-5. Template row:

| Product | Price ID | Payment Link | Price |
|---|---|---|---|
| Analyzer | TBD | TBD | $97 |
| Negotiation Scripts | TBD | TBD | $67 |
| wRVU Playbook | TBD | TBD | $47 |
| Hospitalist Shift Economics | TBD | TBD | $37 |
| Bundle (all 4) | TBD | TBD | $197 |
| LAUNCH coupon (20% off) | TBD | — | — |

## Open questions for Perplexity

(None currently — site work is mechanical execution on a proven EMCI-cloned scaffold until Day 2 Stripe + deploy lands.)
