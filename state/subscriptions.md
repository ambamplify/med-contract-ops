# MCI Subscriptions & Memberships

**Last updated:** 2026-04-26 (Claude Code, initial creation)
**Purpose:** Single reference for every paid service, free-tier account, and recurring membership tied to MedContractIntel. Companion file in EMCI repo: `~/Desktop/em-contract-ops/state/subscriptions.md`.

**How to use:** any time a service is added, renewed, upgraded, or cancelled, update this file AND append a line to `logs/DAILY_CHANGES.md`.

**Values flagged `[verify]`** were not directly confirmed in source state files at write time — owner should confirm plan tier / price on the next pass. **Items flagged `🟣 owner-gated`** have not been created yet (Day 1 build blockers per `PHASE_STATUS.md`).

---

## 1. MCI-exclusive subscriptions / memberships

| Service | What it does | Plan / tier | Cost | Status | Notes |
|---|---|---|---|---|---|
| **Domain — medcontractintel.com** | Registration | Cloudflare Registrar | ~$10/yr `[verify]` | 🟢 live (purchased 2026-04-09) | Auto-renew |
| **Railway — medci-production project** | Site + API hosting | Hobby / usage-based `[verify]` | ~$5–20/mo `[verify]` | 🟢 deployed 2026-04-23 | Project id `214a7540-b763-4a06-a21b-c9cb5158324e` |
| **R2 storage — `medci-social-media` bucket** | Public CDN for TikTok / IG / video | Cloudflare R2 free tier (10 GB/mo) | $0 | 🟢 created 2026-04-22 | Public domain `media.medcontractintel.com` future enhancement |
| **Resend (MCI sender)** | Transactional email | `[verify]` | `[verify]` | 🟣 owner-gated (D1) | Needs `admin@medcontractintel.com` mailbox first |
| **Kit (MCI list)** | Marketing email + sequences | `[verify]` | `[verify]` | 🟣 owner-gated (D1-16) | Account on `admin@medcontractintel.com` |
| **Sentry — `medcontractintel-production` project** | Error tracking | `[verify]` | `[verify]` | 🟣 owner-gated (D1-18) | DSN comes from owner |
| **Buffer — MCI org / 5 channels** | Social scheduling | `[verify]` | `[verify]` | 🟣 owner-gated (D1-17) | TikTok / IG / LinkedIn / X / Threads |
| **NJ DBA filing (AEMBD LLC d/b/a MedContractIntel)** | Legal / brand registration | one-time `[verify]` | one-time fee | 🟣 owner-handled | Annual report `[verify]` |

## 2. Shared subscriptions (both EMCI and MCI use the same billing seat)

| Service | What's shared | What's separated per business |
|---|---|---|
| **Stripe** | Same merchant of record `acct_1TEuuDRS3QYs0eSM` (AEMBD LLC) — same payout bank, same monthly statement | Separate products / prices / payment links / webhook. MCI webhook = `we_1TPM9sRS3QYs0eSMtH7Z6Dtt`. Transaction fees only — no flat sub. |
| **Cloudflare** | Same account (id `2d8b35536675961ba3cd0fc7b56fa3cb`) — same plan, same billing | Separate zones (`emcontractintel.com` / `medcontractintel.com`), separate R2 buckets |
| **GitHub** | Same owner `ambamplify`, same plan tier `[verify]` | Separate repos. Make.com OAuth connection `8477240` is reused across both |
| **Make.com** | Team `2160239` on us2.make.com, **Core plan (10,000 ops/mo, paid tier)** — both businesses share the ops budget | Separate scenarios: EMCI S1 = `4811574`, MCI M1 = `4846282` |
| **1Password** | Team `AMBAmplify` Business `[verify]` plan (~$7.99/seat/mo `[verify]`) | Separate vaults: MCI uses `MedCI — API Keys / OAuth Tokens / Accounts / Infrastructure`. All 4 are 🟣 owner-gated (D1-9). |
| **Google Workspace** | Primary `ambamplify@gmail.com`, `[verify]` plan | MCI = secondary domain `medcontractintel.com` (D1-6 🟣 owner-gated). 8 aliases planned: service / admin / billing / support / hello / legal / noreply / dmca |
| **Anthropic API** | Same key/account, usage-based | One key currently used across both Railway projects |
| **ElevenLabs** | Same account + shared character quota | Different default voice — MCI uses **Ryan** (per MCI Video Style Guide) |
| **Perplexity Pro** | Owner's account | Separate MCI Space; 1P service-account token 🟣 owner-gated (D1-10) |
| **Claude (Anthropic — Max / Code / Cowork)** | Owner's Claude.ai + Claude Code account | Working dir scopes the session |
| **Railway account** | Same login, same payment method | Separate projects |

## 3. Free-tier accounts / memberships (no recurring charge)

| Account | Handle / id | Status |
|---|---|---|
| **TikTok @medcontractintel** | must be Business from day 1 | 🟣 owner-gated (D1-14) — Lesson #17 |
| **Instagram @medcontractintel** | Business | 🟣 owner-gated |
| **LinkedIn Company Page MedContractIntel** | — | 🟣 owner-gated |
| **X (Twitter) @medcontractintel** | — | 🟣 owner-gated |
| **Threads @medcontractintel** | inherits IG | 🟣 owner-gated |
| **YouTube `@medcontractintel`** | Brand Account under `ambamplify@gmail.com` | 🟣 owner-gated (D3-2) |
| **Reddit `/u/MedContractIntel`** | brand | 🟣 owner-gated (D1-22). 0 brand posts first 30 days — karma-build only. |
| **Reddit (personal, value-add only)** | follows EMCI `u/boarded_and_tired` pattern | owner-managed |
| **Substack `medcontractintel.substack.com`** | weekly long-form | 🟣 owner-gated |
| **Pexels API** | shared key with EMCI | free |

## 4. Estimated total monthly burn (MCI side, before usage-based)

| Bucket | Confirmed | Estimated |
|---|---|---|
| Cloudflare (zone + R2) | ✅ | $0 (under free tier) |
| Stripe | ✅ | $0 fixed (per-transaction only) |
| Railway hosting | partial | ~$5–20/mo `[verify]` |
| Resend | unknown | `[verify]` (after D1) |
| Kit | unknown | `[verify]` (after D1) |
| Sentry | unknown | `[verify]` (after D1) |
| Buffer | unknown | `[verify]` (after D1) |
| Domain renewal (~$10/yr ÷ 12) | ✅ | <$1/mo |
| **Project-exclusive subtotal (post-launch)** | | **`[verify]`** |
| Allocated share of shared subs (1P / Workspace / Perplexity / Make.com / Anthropic / ElevenLabs) | | `[verify]` |

## 5. Renewal / billing watchlist

| Date | Item | Action |
|---|---|---|
| `[verify]` | Domain medcontractintel.com expiry (purchased 2026-04-09) | Confirm auto-renew |
| ongoing | Make.com ops budget (10,000/mo, shared with EMCI) | M1 scenario consumption — monitor |
| ongoing | R2 storage (10 GB free) | Currently ~0 MB |
| ongoing | ElevenLabs character quota | Shared with EMCI — monitor when MCI starts producing video |
| `[verify]` | NJ DBA annual report | Owner |

---

## 6. What this file is NOT

- **Not a credentials file.** Never paste keys, passwords, or service-account tokens here. Those live in 1Password (vaults: `MedCI — API Keys / OAuth Tokens / Accounts / Infrastructure`).
- **Not a billing log.** Actual invoices / receipts will go to `billing@medcontractintel.com` Gmail label. This file lists *what we're subscribed to*, not the line items.
- **Not authoritative for account ownership.** That's `state/infra.md` — this file just tracks the subscription plan + cost.

---

**To update:** edit this file → commit → append a line to `logs/DAILY_CHANGES.md` describing what changed.
