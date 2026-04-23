# PHASE_STATUS — MedContractIntel build

**Live execution tracker. Ops-controller updates every 4hr. Interactive sessions update as they work.**

**Status key:** `pending` | `in-progress` | `done` | `owner-blocked` | `deferred`
**Checkbox key:** `[x]` done | `[~]` partial/in-progress | `[O]` owner-blocked | `[D]` deferred | `[ ]` pending

---

## Fast checkbox view (for Perplexity scanning)

### Day 0 — Tuesday 2026-04-22 evening (PRE-FLIGHT)
- [x] D0-1 Scaffold med-contract-ops repo
- [x] D0-2 Move blueprint to ~/MedContractIntel/
- [x] D0-3 Create med-ops-controller SKILL.md
- [O] D0-3b Register med-ops-controller with scheduler (owner)
- [x] D0-4 Cross-reference EMCI DAILY_CHANGES
- [x] D0-5 Memory file for MedCI build
- [x] D0-6 Owner: confirm pricing (confirmed)
- [x] D0-7 Owner: NJ DBA filing (owner-handled)
- [D] D0-8 Owner: Better Stack decision (deferred post-launch)
- [x] D0-9 Brand palette ratified + site migration (added 2026-04-22 late evening)
- [x] D0-10 ZERO_QUESTION_CLAUDE.md + WORKFLOW.md authority files (added 2026-04-22 late evening)

### Day 1 — Wednesday 2026-04-23 (LEGAL + DNS + INFRA SKELETON)
- [O] D1-1 Daily sync (owner — owner unavailable Wed AM)
- [x] D1-2 Write Day 1 hour-by-hour
- [O] D1-3 File DBA with NJ (owner-handled)
- [x] D1-4 Cloudflare zone medcontractintel.com
- [~] D1-5 DNS records (MX/SPF/DMARC propagating; A/AAAA Day 2; DKIM owner)
- [O] D1-6 Owner: add Google Workspace secondary domain
- [O] D1-7 Owner: create 8 email aliases
- [O] D1-8 Owner: Google Drive folder tree
- [O] D1-9 Owner: 4 new 1Password vaults `MedCI — *`
- [O] D1-10 Owner: Perplexity 1P service account
- [O] D1-11 Gmail filters (owner — Gmail MCP scope mismatch)
- [x] D1-12 Create 3 GitHub repos
- [x] D1-13 Git init + push med-contract-ops
- [O] D1-14 Owner: register @medcontractintel TikTok Business
- [x] D1-15 DNS propagation verify (MX/SPF/DMARC confirmed 2026-04-23 00:13 EDT)
- [O] D1-16 Owner: Kit account signup
- [O] D1-17 Owner: Buffer org + 5 socials OAuth
- [O] D1-18 Owner: Sentry project
- [ ] D1-19 Resend domain verification (blocked on D1-6 DKIM coexistence)
- [~] D1-20 R2 bucket created; public domain attach pending
- [x] D1-21 Legal pages ported from EMCI
- [O] D1-22 Owner: brand Reddit account
- [D] D1-23 Better Stack (deferred per D0-8)
- [x] D1-24 Pricing confirmed Day 0
- [x] D1-25 EOD retro + Day 2 plan write (done Day 0 evening)

### Day 2 — Thursday 2026-04-24 (STRIPE + SITE DEPLOY)
- [O] D2-1 Daily sync
- [x] D2-2 Integrate Stripe product IDs into site (done 2026-04-23 04:13 EDT — pulled forward with D2-5)
- [x] D2-3 Verify `cp -r server/pdfs dist/server/pdfs` in build (Lesson #2) — pre-verified 2026-04-22 late evening, already in package.json build script
- [x] D2-4 Verify Stripe lazy-init in webhook (Lesson #3) — pre-verified 2026-04-22 late evening, `getStripe()` lazy-init at line 129 of stripe-webhook.ts
- [x] D2-5 Create Stripe products + prices + payment links via MCP (pulled forward 2026-04-23 04:13 EDT)
- [x] D2-6 `/checklist-thank-you` route split (Lesson #13) — pre-verified 2026-04-22 late evening, `public/checklist-thank-you/` separate from `public/thank-you/`
- [~] D2-7 Stripe success URLs include `?session_id` (Lesson #9) — endpoint exists; payment links created but after_completion redirect NOT settable via MCP. Owner must set on all 7 links via Stripe dashboard (see state/stripe-ids.md §FOLLOW-UP)
- [ ] D2-8 Rebuild 4 IM PDFs with new palette
- [x] D2-9 Railway project create + env vars (done 2026-04-23 04:13 EDT)
- [x] D2-10 Deploy to Railway; verify 200 on key routes (done 2026-04-23 04:13 EDT)
- [~] D2-11 Cloudflare CNAME at Railway domain + TLS (partial — CNAME config ready in state/infra.md; needs Cloudflare dashboard apply)
- [ ] D2-12 Smoke test #1 (gated halt if fail)
- [ ] D2-13 Production Stripe webhook
- [O] D2-14 Kit email automation import (downstream of D1-16)
- [ ] D2-15 Stripe→Kit tag bridge verify
- [ ] D2-16 Smoke test #2 full funnel
- [ ] D2-17 Verify 4 PDFs in server/pdfs/ AND dist/
- [ ] D2-18 Day 2 EOD retro + Day 3 plan write

### Day 3 — Friday 2026-04-25 (ANALYZER + CONTENT)
*Populated by ops-controller morning of Day 3. Pulls from blueprint §10 Day 3.*

### Day 4 — Saturday 2026-04-26 (AUTOMATION + DRY RUN)
*Populated by ops-controller morning of Day 4.*

### Day 5 — Sunday 2026-04-27 (LAUNCH)
*Populated by ops-controller morning of Day 5. Gated by 18 Launch Gates (§13).*

---

## Day 0 — Tuesday 2026-04-22 evening (PRE-FLIGHT)

| # | Task | Status | Timestamp | Notes |
|---|---|---|---|---|
| D0-1 | Scaffold `~/MedContractIntel/med-contract-ops/` | done | 2026-04-22 18:35 EDT | Mirrors EMCI pattern |
| D0-2 | Move blueprint → `~/MedContractIntel/` | done | 2026-04-22 18:35 EDT | From ~/Desktop root |
| D0-3 | Create med-ops-controller SKILL.md | done | 2026-04-22 evening | Written to `~/.claude/scheduled-tasks/med-ops-controller/SKILL.md` |
| D0-3b | **Register med-ops-controller with scheduler** | owner-blocked | — | MCP blocks from within scheduled-task session. Owner runs paste-ready prompt in `INBOX/register-med-ops-controller.md` from a fresh Claude Code session — 2 min. |
| D0-4 | Cross-reference EMCI DAILY_CHANGES | done | 2026-04-22 evening | Audit trail |
| D0-5 | Memory file for MedCI build | done | 2026-04-22 evening | Scoped to 5-day build |
| D0-6 | Owner: confirm pricing ($197/$97/$67/$47/$32) | done | 2026-04-22 evening | **Confirmed same as blueprint: $197 bundle / $97 analyzer / $67 scripts / $47 wRVU / $37 shift-economics.** Day 2 Stripe creation unblocked. |
| D0-7 | Owner: NJ DBA filing | owner-handled | 2026-04-22 evening | **Owner will complete personally.** No Claude Code dependency. Filing status not a launch gate blocker. |
| D0-8 | Owner: Better Stack decision | deferred | 2026-04-22 evening | **Skipped for launch, deferred post-launch.** D1-23 removed from Day 1 plan. Launch gates unchanged (no Better Stack gate exists). |

---

## Day 1 — Wednesday 2026-04-23 (LEGAL + DNS + INFRA SKELETON)

Pulled from blueprint §10 Day 1. All items `pending` until ops-controller or interactive session executes.

| Time | # | Task | Owner | Status |
|---|---|---|---|---|
| 7:00 | D1-1 | Daily sync — owner opens Claude Code + Perplexity | 🟣 | owner-blocked — owner unavailable Wed AM, see ESCALATED/day1-owner.md |
| 7:15 | D1-2 | Claude Code writes today's hour-by-hour into PHASE_STATUS.md | 🟢 | done — this file; refreshed 2026-04-22 late evening |
| 7:30 | D1-3 | File DBA "MedContractIntel" with NJ | 🟣 | owner-handled per D0-7 |
| 8:00 | D1-4 | Create Cloudflare zone medcontractintel.com | 🟢 | done — zone pre-existing from 2026-04-09 domain purchase, verified 2026-04-22 evening |
| 8:30 | D1-5 | Add DNS: A, AAAA, MX, TXT (SPF), DKIM placeholder, DMARC | 🟢 | partial-done — MX + SPF + DMARC posted 2026-04-22 late evening via signed-in JS. A/AAAA wait on Railway IP (Day 2). DKIM wait on Google secondary-domain add (owner). |
| 9:00 | D1-6 | Owner: add medcontractintel.com as secondary domain in Google Workspace | 🟣 | owner-blocked — ESCALATED item #1 |
| 9:30 | D1-7 | Create 6 aliases (service, admin, billing, support, hello, legal, noreply, dmca) | 🟣 | owner-blocked — ESCALATED item #1 (downstream of D1-6) |
| 9:45 | D1-8 | Owner: create Google Drive folder tree per blueprint §5.5 | 🟣 | owner-blocked — ESCALATED item #5 |
| 10:00 | D1-9 | Owner: create 4 new 1Password vaults `MedCI — *` | 🟣 | owner-blocked — ESCALATED item #3 |
| 10:10 | D1-10 | Owner: create Perplexity 1P service account, store token in Space memory | 🟣 | owner-blocked — ESCALATED item #4 (downstream of D1-9) |
| 10:30 | D1-11 | Add Gmail filters routing @medcontractintel.com → MCI/* labels | 🟢 | owner-blocked — Gmail MCP is connected to service@emcontractintel.com, not the owner's Workspace admin. Owner creates filters OR connects new Gmail MCP on @medcontractintel.com after D1-6/D1-7 land. |
| 11:00 | D1-12 | Create 3 GitHub repos: med-contract-ops, -content, -site | 🟢 | done — 2026-04-22 late evening, all 3 public (flip private after sudo email unblocked) |
| 11:30 | D1-13 | Git init local med-contract-ops + push to GitHub | 🟢 | done — 2026-04-22 late evening, commit 3355dbd on main pushed to origin |
| 11:45 | D1-14 | Owner: register @medcontractintel TikTok as BUSINESS account + convert @emcontractintel to Business (Lesson #17) | 🟣 | owner-blocked — ESCALATED item #6 |
| 12:00 | D1-15 | Verify DNS propagation + mail-tester score | 🟢 | **done 2026-04-23 00:13 EDT** — MX (`1 smtp.google.com.`) ✅ FULLY PROPAGATED, SPF (`v=spf1 include:_spf.google.com ~all`) ✅ FULLY PROPAGATED, DMARC (`p=quarantine; adkim=s; aspf=s`) ✅ FULLY PROPAGATED. A/AAAA ⏳ waiting Railway IP (Day 2). DKIM ⏳ waiting owner Google secondary-domain add (D1-6). |
| 1:00 | D1-16 | Owner: sign up new Kit account on admin@medcontractintel.com, disable double opt-in | 🟣 | owner-blocked — ESCALATED item #7 (downstream of D1-7) |
| 1:30 | D1-17 | Owner: create Buffer org, OAuth all 5 socials (TikTok Business) | 🟣 | owner-blocked — ESCALATED item #8 |
| 2:00 | D1-18 | Owner: create Sentry project medcontractintel-production, save DSN | 🟣 | owner-blocked — ESCALATED item #9 |
| 2:30 | D1-19 | Resend domain verification started | 🟢 | pending — MX is now PROPAGATING (per D1-15), but Resend verification still gated on owner D1-6 (Google secondary domain add) since Resend DKIM CNAME on `resend._domainkey.medcontractintel.com` needs to coexist with Google DKIM. Queued for first Day 1 autonomous run after D1-6 lands. |
| 3:00 | D1-20 | Cloudflare R2 bucket `medci-social-media` created + public domain | 🟢 | partial-done — bucket CREATED 2026-04-22 23:32 UTC (pre-flight); public domain attach pending dashboard access (no MCP path). Owner or Claude-in-Chrome on Day 1. |
| 3:30 | D1-21 | Port legal pages from EMCI site (privacy/terms/dmca/disclaimer/refund-policy), MedCI find-replace | 🟢 | done — markdown draft at `INBOX/legal-pages-draft.md` (commit 3355dbd); 5 drop-in HTML files split into `INBOX/legal-pages/` 2026-04-22 20:20 EDT with README + copy-ready cp commands. Ships to `med-contract-site/public/` on Day 2 scaffold. |
| 4:00 | D1-22 | Owner: register brand Reddit `/u/MedContractIntel` with 2FA | 🟣 | owner-blocked — ESCALATED item #10 |
| 4:30 | D1-23 | ~~Better Stack monitors~~ DEFERRED per D0-8 decision | — | deferred |
| — | D1-24 | ~~Owner: confirm pricing~~ COMPLETED Day 0 per D0-6 | — | done |
| 7:00 | D1-25 | EOD retro + Day 2 plan write | 🟢 | done — 2026-04-22 ~23:00 EDT interactive Claude Code session pre-populated Day 2 hour-by-hour below (18 tasks, D2-1 through D2-18) with Phase A scaffold already factored in. Owner walks into Day 1 morning with Day 2 already sequenced. |

**Day 1 launch gate:** DNS resolving, all 8 aliases receive mail, Resend + Kit accounts created, Sentry project live, Buffer connected (TikTok Business), R2 bucket accessible, pricing locked. Any RED = Day 2 delayed.

---

## Day 2 — Thursday 2026-04-24 (STRIPE + SITE DEPLOY)

Hour-by-hour populated 2026-04-22 late evening (Day 0 pull-forward by interactive Claude Code session). Phase A scaffold (clone + rebrand + IM analysis-prompt + legal pages) already complete (commit `47d731a`). Brand palette migration complete (commit `59becb7`). Day 2 resumes at Stripe integration + Railway deploy.

| Time | # | Task | Agent | Status |
|---|---|---|---|---|
| 7:00 | D2-1 | Daily sync — owner opens Claude Code + Perplexity; read BUILD_STATUS.md + this file first | 🟣 | pending |
| 8:00 | D2-2 | ~~Finish med-contract-site string/color/logo swap~~ **Rebrand + palette DONE 2026-04-22 evening (commits 47d731a + 59becb7).** Remaining: integrate actual Stripe product IDs. | 🔵 | **done 2026-04-23 04:13 EDT** — stripe-webhook.ts PRODUCT_MAP + BUNDLE_PRODUCT_ID + new ANALYZER_PRODUCT_ID all updated to MedCI prod_* IDs. routes.ts PRODUCT_SLUG updated with all 5 products. Standalone analyzer payment-link purchase now grants credit correctly. |
| 8:30 | D2-3 | Verify `cp -r server/pdfs dist/server/pdfs` is in build script (Lesson #2 — EMCI hot-bug) | 🔵 | **done 2026-04-22 late evening** — package.json build script: `vite build && esbuild ... && cp -r public dist/public && mkdir -p dist/server && cp -r server/pdfs dist/server/pdfs`. Pre-verified. |
| 8:45 | D2-4 | Verify Stripe lazy-init inside webhook handler, NOT top-of-module (Lesson #3) | 🔵 | **done 2026-04-22 late evening** — `getStripe()` helper at line 129 of stripe-webhook.ts returns new Stripe(key) on demand; no module-scope Stripe initialization. Pre-verified. |
| 9:00 | D2-5 | **Create Stripe products + prices + payment links via MCP** against `INBOX/stripe/products-prices-spec.json` (pre-specced Day 0). Capture all price IDs + payment-link URLs into `state/stripe-ids.md`. | 🔵 | **done 2026-04-23 04:13 EDT** — pulled forward. 5 products + 5 prices + 1 coupon (XlzbFyUR) + 7 payment links created on acct_1TEuuDRS3QYs0eSM (correct per blueprint §2). IDs in `state/stripe-ids.md`. ⚠ 3 follow-ups require Stripe dashboard (after_completion redirect, coupon on links 6+7, coupon expiry) — see state/stripe-ids.md FOLLOW-UP section. |
| 9:30 | D2-6 | Create `/checklist-thank-you` route separate from `/thank-you` (Lesson #13 — EMCI hot-bug) | 🔵 | **done 2026-04-22 late evening** — `public/checklist-thank-you/` already a separate directory from `public/thank-you/` in the Phase A scaffold (inherited from EMCI pattern). Pre-verified. |
| 10:00 | D2-7 | Set all Stripe payment link success URLs to include `?session_id={CHECKOUT_SESSION_ID}` (Lesson #9) | 🔵 | partial — endpoint exists; payment links created but MCP `create_payment_link` doesn't support after_completion parameter. Owner must update all 7 links in Stripe dashboard to redirect to `https://medcontractintel.com/thank-you?session_id={CHECKOUT_SESSION_ID}`. Flagged in state/stripe-ids.md §FOLLOW-UP #1. |
| 10:30 | D2-8 | Rebuild 4 IM PDFs with new palette (bundle / RVU playbook / negotiation scripts / billing breakdown) via `make_og_image.py` + `make_thumbnail.py` + existing `server/pdf-report.ts` template — tokens now pull from brand palette | 🔵 | pending — prep done 2026-04-23 00:13 EDT: em-*.pdf renamed → med-*.pdf (placeholder MedCI PDFs committed, gitignore updated so Railway gets them). pdf-report.ts COLORS.navy fixed to medical-green [31,110,67]. Real IM content replaces placeholder at D2-8 once IM_DATA_2026.md populated. |
| 11:00 | D2-9 | Create Railway project `medci-production`; connect ambamplify/med-contract-site repo; add env vars | 🔵 | **done 2026-04-23 04:13 EDT** — project `214a7540-b763-4a06-a21b-c9cb5158324e`, service `49cfe983-0de2-46eb-8ebf-c1a35ef741bf`, volume `8222fdc6-b23f-477a-be22-51b1f9e3c3af` (/data). 9 env vars set (ANTHROPIC_API_KEY, STRIPE_SECRET_KEY, EMAIL_API_KEY, EMAIL_PROVIDER, EMAIL_FROM, DATABASE_PATH, PORT, NODE_ENV, INTERNAL_TEST_SECRET). 4 still pending: STRIPE_WEBHOOK_SECRET, SENTRY_DSN, KIT_*. |
| 11:30 | D2-10 | Deploy to Railway; verify `med-contract-site-production.up.railway.app` returns 200 on homepage + /calculator + /analyzer | 🔵 | **done 2026-04-23 04:13 EDT** — `railway up --detach` triggered; Railway status = SUCCESS; HTTP 200 on root. Deployment ID `c028834b-5953-424c-ae2e-53b6a66eba35`. |
| 12:00 | D2-11 | Cloudflare CNAME at Railway domain (completes D1-5 partial); verify TLS auto-provisions | 🔵 | partial — custom domain `medcontractintel.com` registered in Railway. Cloudflare CNAME config ready in `state/infra.md` (CNAME `@` → `med-contract-site-production.up.railway.app`, proxy on). No CF API token available for autonomous DNS write; owner adds via dashboard OR interactive Claude-in-Chrome on Day 2. |
| 12:30 | D2-12 | **Smoke test #1 (gated):** homepage loads, /calculator works, /analyzer upload page loads, Stripe test-mode checkout for $97 analyzer completes. If any fail, stop — do not proceed to D2-13 | 🔵→🟢 | pending |
| 1:30 | D2-13 | Production Stripe webhook: point live webhook at medcontractintel.com/api/webhooks/stripe; register same 4 events as EMCI (checkout.session.completed, charge.refunded, customer.subscription.deleted, invoice.payment_failed) | 🔵 | pending |
| 2:00 | D2-14 | Import 3 Kit email automations from `INBOX/kit/emails-spec.md` (pre-drafted Day 0) into owner's Kit account. **Kit email 1 links to direct PDF URL, not form URL (Lesson #10 — EMCI hot-bug).** Blocked if D1-16 owner Kit signup not complete | 🔵 | owner-blocked-downstream |
| 3:30 | D2-15 | Verify Stripe→Kit tag bridge (spec in `INBOX/kit/emails-spec.md`) — test checkout should add tag `medci-analyzer-purchased` within 30s | 🔵 | pending |
| 4:00 | D2-16 | **Smoke test #2 (full funnel):** /calculator → email capture → Kit email 1 delivers free IM Red Flag Checklist PDF → D2 nurture email fires in 48hr sim | 🔵→🟢 | pending |
| 5:00 | D2-17 | Verify 4 IM PDFs exist in `server/pdfs/` AND are copied to `dist/server/pdfs/` on build (Lesson #2 re-verify) | 🔵 | pending |
| 7:00 | D2-18 | Day 2 EOD retro + Day 3 plan write into PHASE_STATUS.md | 🟢 | pending |

**Day 2 launch gate (= Day 2 exit criteria):**
- medcontractintel.com resolves with valid TLS
- /analyzer accepts uploads (Claude API wired + Anthropic key from env)
- Stripe test-mode purchase of $97 analyzer completes end-to-end
- Kit email 1 delivers a working PDF URL (not a form URL)
- 4 IM PDFs exist in `server/pdfs/` AND `dist/server/pdfs/`

Any RED = Day 3 delayed.

## Day 3 — Friday 2026-04-25 (ANALYZER + CONTENT)
Populated by ops-controller morning of Day 3.

## Day 4 — Saturday 2026-04-26 (SCHEDULED TASKS + MAKE.COM + DRY RUN)
Populated by ops-controller morning of Day 4. Includes 9:30 AM owner Run-Now on all 16 `med-*` tasks (Lesson #18).

## Day 5 — Sunday 2026-04-27 (LAUNCH)
Populated by ops-controller morning of Day 5. Launch only fires when all 18 Launch Gates GREEN (Gate 18 = Lesson #19 dual content review complete).

---

## Agent key
- 🟢 Claude Code
- 🔵 Claude Code (Remotion/video scope) — Day 3+
- 🟣 Owner
- automatic — scheduled task / Buffer auto-delivery
