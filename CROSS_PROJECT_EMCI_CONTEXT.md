# Cross-Project Context — EM Contract Intel (EMCI)

**Read-only digest for the MCI Perplexity Space. Maintained by Claude Code on every routine run.**
**You may NOT clone, read, or modify any EMCI repo or file directly. This file is your only window into EMCI.**

**Last refreshed:** 2026-04-25 ~20:25 EDT (perplexity-tab-poll routine)

---

## What EMCI is

Emergency-medicine contract analyzer SaaS + content engine + 4 PDF products. Live for ~9 days. Brand identity: navy/gold palette, physician-voice content, domain `emcontractintel.com`, Stripe account separate from MCI.

Hard rule: EMCI and MCI never cross-reference, share customers, or link sites without explicit owner authorization.

## Where EMCI is right now

- **Phase:** All Phase 1a–1g foundation work ✅ complete (security, monitoring, intelligence, content engine, YouTube auto-upload, playbooks)
- **Operating mode:** Steady-state — autonomous content production + scheduled tasks running, awaiting first revenue signals
- **Stripe Daily Monitor:** 🔴 offline since Apr 17 (~8 days) — owner-blocked on `STRIPE_SECRET_KEY` env var
- **Item 14 (TikTok Business conversion):** 🔴 owner-blocked — TikTok channel paused until conversion + Buffer reconnect
- **Better Stack:** 🟡 5 monitors live, webhook upgrade ($29/mo) deferred — owner decision pending

## Current EMCI content velocity

| Channel | Status | Cadence |
|---|---|---|
| X / Twitter (@EMContractIntel) | ✅ live | Daily through May 19 |
| LinkedIn | ✅ live | 90+ posts queued across 5 batches |
| Instagram | ✅ live | Mix of static (auto-publish) + Reels (notification mode), through May 6 |
| Threads | ✅ live | Daily through May 21 |
| TikTok | ⏸ paused | 15 videos in Buffer queue, awaiting Item 14 unblock |
| YouTube | ✅ A1 live | A2/A3 awaiting owner approval |
| Reddit | 🟡 manual | Personal account `u/boarded_and_tired`, physician-voice, no brand mentions; reply drafts queued in `reddit/approved-replies-{date}.md` |

## Active EMCI directives in flight

- IDEA-042–081 (40 content ideas from 2026-04-22 Monday ideation run) — awaiting EMCI Perplexity Space ranking + approval. Stale ~3 days.
- Reddit reply drafts in `reddit/approved-replies-2026-04-25.md` — awaiting owner manual post (time-sensitive).

## Shared resources (touch carefully)

- 1Password vaults: separate per-project, both in same `AMBAmplify` team
- ElevenLabs voice quota: shared, EMCI default voice `4e32WqNVWRquDa1OcRYZ`
- Google Workspace: ambamplify@gmail.com primary
- Owner attention: heavily on MCI launch through Apr 27 — EMCI is in autonomous-coast mode this weekend

## Implications for MCI strategy

- EMCI's 9 days of operating data is your closest analog. Patterns that worked on EMCI are good prior probability for MCI (same owner, similar audience, parallel funnel). Patterns that failed on EMCI are worth flagging before MCI repeats them.
- EMCI's IM_DATA_2026.md analog is `EM_DATA_2026.md` — different specialty, different numbers, but the data-discipline and citation patterns transfer directly.
- 19 hard-won EMCI lessons are baked into the MCI blueprint (`MEDCONTRACTINTEL_BLUEPRINT.md` §4). Don't re-derive them.
- EMCI's Sentry ESM auto-instrumentation incompatibility with drizzle-orm + esbuild (PHASE_STATUS.md "Known Incompatibilities") applies to MCI's site too. Do not enable Sentry auto-instrumentation in MCI without a tested workaround.

---

## How to update this file

Claude Code refreshes this on every perplexity-tab-poll routine run (every 4 hours) by reading `/Users/ambamplify/Desktop/em-contract-ops/PHASE_STATUS.md` and `em-contract-content/ops/SOCIAL_STATUS.md`. If you (MCI Perplexity) need richer EMCI context not present here, request it explicitly: tell the owner "I need a refreshed cross-project digest with X". Owner will instruct Claude Code to extend the digest. **You will not be granted direct read access to EMCI repos.**
