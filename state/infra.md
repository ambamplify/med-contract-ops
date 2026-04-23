# MedCI Infrastructure State

**Last updated:** 2026-04-22 23:15 EDT
**Owner:** Claude Code (autonomous writes) — Perplexity reads

---

## Domain — medcontractintel.com

| Record | Value | Status |
|---|---|---|
| Zone | Cloudflare (acct ambamplify) | 🟢 live (pre-existing from 2026-04-09 purchase) |
| MX | `smtp.google.com` pri 1 | 🟢 propagating (verified 2026-04-22 20:13 EDT) |
| SPF (TXT) | `v=spf1 include:_spf.google.com ~all` | 🟢 propagating |
| DMARC (TXT `_dmarc`) | `v=DMARC1; p=quarantine; adkim=s; aspf=s; rua=mailto:admin@...` | 🟢 propagating |
| A / AAAA | — | ⏳ waits on Railway deploy (D2-11) |
| DKIM | — | ⏳ waits on owner D1-6 Google secondary-domain add |
| Resend DKIM CNAME (`resend._domainkey`) | — | ⏳ waits on owner D1-6 to coexist with Google DKIM |

## Railway

| Item | Value | Status |
|---|---|---|
| Project | `medci-production` | 🟢 created 2026-04-23 04:13 EDT |
| Project ID | `214a7540-b763-4a06-a21b-c9cb5158324e` | 🟢 |
| Environment ID | `b5ced0b8-e936-4618-9d34-4a68448a4c25` | 🟢 production |
| Service ID | `49cfe983-0de2-46eb-8ebf-c1a35ef741bf` | 🟢 med-contract-site |
| Volume ID | `8222fdc6-b23f-477a-be22-51b1f9e3c3af` | 🟢 /data (SQLite) |
| Railway domain | `med-contract-site-production.up.railway.app` | 🟢 HTTP 200 (first deploy SUCCESS) |
| Custom domain registered | `medcontractintel.com` | 🟢 registered in Railway; DNS pending |
| Railway edge IP | `151.101.2.15` (Fastly) | 🟢 confirmed |
| Repo | `ambamplify/med-contract-site` main (commit 5d2f165) | 🟢 deployed |
| Env vars set | NODE_ENV, PORT, DATABASE_PATH, EMAIL_PROVIDER, EMAIL_FROM, INTERNAL_TEST_SECRET, ANTHROPIC_API_KEY, EMAIL_API_KEY, STRIPE_SECRET_KEY | 🟢 9/13 vars set |
| Env vars pending | STRIPE_WEBHOOK_SECRET (after D2-13), SENTRY_DSN (owner D1-18), KIT_FORM_ID, KIT_API_KEY, KIT_CHECKLIST_FORM_ID (owner D1-16) | ⏳ owner-blocked |

### Cloudflare DNS needed to complete D2-11

Add this CNAME record in Cloudflare dashboard (dash.cloudflare.com → medcontractintel.com → DNS):
- Type: CNAME
- Name: `@` (apex/root)
- Target: `med-contract-site-production.up.railway.app`
- Proxy: ✅ Enabled (orange cloud)

Cloudflare CNAME flattening handles the apex domain. This replaces the A/AAAA approach.
After adding: TLS auto-provisions via Cloudflare → Railway in ~2 minutes.

## Cloudflare R2

| Bucket | Status |
|---|---|
| `medci-social-media` | 🟢 created 2026-04-22 23:32 UTC |
| Public domain attach | 🟡 deferred to Day 1 dashboard step (no MCP path) |
| Custom domain `media.medcontractintel.com` (Direct Publishing unlock) | 🔴 not yet — future enhancement, lower priority than EMCI's `media.emcontractintel.com` pending |

## Resend

| Item | Status |
|---|---|
| Account | 🟣 owner-gated — needs admin@medcontractintel.com mailbox first (D1-6/D1-7) |
| Domain verification | ⏳ queued for first Day 1 run after MX+DKIM both live |

## Kit (ConvertKit)

| Item | Status |
|---|---|
| Account on admin@medcontractintel.com | 🟣 owner-gated (D1-16) |
| Email automations spec | 🟢 pre-drafted: `INBOX/kit/emails-spec.md` (3 full HTML drafts + wiring spec) |
| Import to Kit | ⏳ D2-14 — blocked on owner account creation |

## Sentry

| Item | Status |
|---|---|
| Project `medcontractintel-production` | 🟣 owner-gated (D1-18) |
| DSN | ⏳ comes from owner after project create |

## Google Workspace

| Item | Status |
|---|---|
| Secondary domain `medcontractintel.com` | 🟣 owner-gated (D1-6) — admin.google.com reauth |
| Aliases: service, admin, billing, support, hello, legal, noreply, dmca | 🟣 owner-gated (D1-7) downstream of above |

## 1Password

| Item | Status |
|---|---|
| Vaults: `MedCI — API Keys`, `MedCI — OAuth Tokens`, `MedCI — Accounts`, `MedCI — Infrastructure` | 🟣 owner-gated (D1-9) |
| Perplexity service account token | 🟣 owner-gated (D1-10, downstream of D1-9) |

---

## Blockers / open questions

(Perplexity: anything here is a live blocker. Dispatch guidance to `COMPUTER_RESPONSE.md`.)

1. **DKIM coexistence:** when owner adds medcontractintel.com as Google secondary domain (D1-6), the Google DKIM CNAME at `google._domainkey.medcontractintel.com` must coexist with Resend's `resend._domainkey.medcontractintel.com`. Both are fine to live side-by-side (different selectors) — confirm nothing deletes the other.
2. **R2 public domain attach:** no current MCP tool can bind a custom domain to an R2 bucket — requires the Cloudflare dashboard UI. Plan: use Claude-in-Chrome on Day 1 during the R2 public-access step. Can Perplexity confirm this is the right path, or is there a Wrangler CLI invocation I'm missing?
