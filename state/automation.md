# MedCI Automation State

**Last updated:** 2026-04-22 23:15 EDT
**Owner:** Claude Code (autonomous writes) — Perplexity reads

---

## Scheduled tasks (med-*)

| Task | Status | Path |
|---|---|---|
| med-ops-controller | 🟢 SKILL.md written, cron `7 */4 * * *` | `~/.claude/scheduled-tasks/med-ops-controller/SKILL.md` |
| med-ops-controller (registration) | 🟢 REGISTERED — cron `7 */4 * * *`, taskId med-ops-controller | live |
| 14 med-* tasks (registration) | 🟣 owner-blocked — paste-ready prompt in `INBOX/register-med-tasks.md`. Run from fresh Claude Code session. | D4-3 |
| med-daily-digest | 🟢 SKILL.md written `42 7 * * *` | D4-2 done 2026-04-24 |
| med-content-ideator | 🟢 SKILL.md written `10 9 * * 1` (Monday) | D4-2 done 2026-04-24 |
| med-gmail-triager-morning | 🟢 SKILL.md written `40 8 * * *` | D4-2 done 2026-04-24 |
| med-gmail-triager-afternoon | 🟢 SKILL.md written `40 13 * * *` | D4-2 done 2026-04-24 |
| med-gmail-triager-evening | 🟢 SKILL.md written `40 18 * * *` | D4-2 done 2026-04-24 |
| med-linkedin-poster | 🟢 SKILL.md written `40 7 * * *` | Buffer channelId = PLACEHOLDER |
| med-x-poster | 🟢 SKILL.md written `45 7 * * *` | Buffer channelId = PLACEHOLDER |
| med-threads-poster | 🟢 SKILL.md written `55 7 * * *` | Buffer channelId = PLACEHOLDER |
| med-tiktok-poster | 🟢 SKILL.md written `0 8 * * *` | Direct Publishing per Lesson #17 |
| med-instagram-poster | 🟢 SKILL.md written `50 7 * * *` | Buffer channelId = PLACEHOLDER |
| med-youtube-poster | 🟢 SKILL.md written `5 8 * * *` | OAuth token = PLACEHOLDER |
| med-stripe-daily-monitor | 🟢 SKILL.md written `40 9 * * *` | 1P vault: `MedCI — Secrets` |
| med-social-listener | 🟢 SKILL.md written `40 11 * * *` | Reddit + IM subreddits |
| med-weekly-reporter | 🟢 SKILL.md written `10 19 * * 0` (Sunday) | D4-2 done 2026-04-24 |

**Total target:** 14 scheduled tasks (+ med-ops-controller = 15 total) by Day 4 end per blueprint §10 Day 4 7:30 AM. All SKILL.md files written (D4-2 done). Registration (D4-3) owner-blocked — paste-ready prompt in INBOX/register-med-tasks.md. Crons staggered :40–:05 to avoid EMCI :00–:35 collision.

## Make.com

| Item | Status | Notes |
|---|---|---|
| M1 scenario (content→Buffer) | 🟢 SCAFFOLDED | MedCI-S1-GitHub-to-Buffer — Modules 1+2 live. Modules 3–9 built in UI (D4-6, owner-gated on D1-17 Buffer). Lesson #6: no API after Module 2. |
| Scenario ID | **4846282** | us2.make.com team 2160239 |
| Module 1 | github:makeAnAPICall v4 — GraphQL query to `ambamplify/med-contract-content` `main:content/approved`. Connection ID 8477240 (same GitHub account as EMCI). |
| Module 2 | builtin:BasicFeeder v1 — iterator over `1.Body.data.repository.object.entries` |
| Modules 3–9 | 🟣 owner-builds in Make.com UI (D4-6) — Parser + Router + Filter + Buffer×5 platforms. Lesson #6: API after Module 2 clobbers UI values. |
| Connected GitHub account | 🟢 REUSING EMCI connection ID 8477240 (same ambamplify@gmail.com account, points to med-contract-content) |
| Connected Buffer org | 🟣 owner-gated (D1-17) — needed for Modules 4–9 buffer posts |

## Buffer

| Item | Status |
|---|---|
| Org | 🟣 owner-gated (D1-17) |
| Channels: MedCI TikTok / IG / LinkedIn / X / Threads / YouTube | 🔴 not yet — owner OAuths each Day 1 |
| Org ID / channel IDs | Populated Day 2+ |

## Kit

| Item | Status |
|---|---|
| Account | 🟣 owner-gated (D1-16) |
| Automations specced | 🟢 `INBOX/kit/emails-spec.md` — 3 sequences, full HTML |
| Automations imported | ⏳ D2-14 |

## Perplexity

| Item | Status |
|---|---|
| Space | 🟢 assumed live (owner opens MedCI Space; one tab in Chrome = notify target) |
| 1P service account | 🟣 owner-gated (D1-10) |
| IM_DATA_2026.md population | 🟡 in progress — Perplexity lane, populates Day 1 afternoon per blueprint §3 |

## Open questions for Perplexity

1. **16-task list confirmed?** The EMCI parallel has 16 `em-*` scheduled tasks. Blueprint §10 Day 4 7:30 AM says "Fork 16 EMCI scheduled-task SKILL.md files." Perplexity: confirm the current enumerated list above matches your expectation, OR flag any that should NOT be forked (e.g., `em-reddit-poster` — blueprint says MedCI Reddit brand account posts zero for first 30 days, so `med-reddit-poster` may be omitted).
2. **Day 4 cron offsets:** EMCI `em-*` tasks mostly run at `:17` or `:27` past the hour. Claude Code will offset `med-*` by +20 minutes (to `:37` / `:47`) to avoid Mac CPU collision. OK?
