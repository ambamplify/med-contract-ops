# MedCI Automation State

**Last updated:** 2026-04-22 23:15 EDT
**Owner:** Claude Code (autonomous writes) — Perplexity reads

---

## Scheduled tasks (med-*)

| Task | Status | Path |
|---|---|---|
| med-ops-controller | 🟢 SKILL.md written, cron `7 */4 * * *` | `~/.claude/scheduled-tasks/med-ops-controller/SKILL.md` |
| med-ops-controller (registration) | 🟣 owner-blocked — owner runs paste-ready prompt in `INBOX/register-med-ops-controller.md` from fresh session | — |
| med-daily-digest | 🔴 not yet — Day 4 forking from EMCI equivalent | D4 |
| med-content-ideator | 🔴 not yet — Day 4 | D4 |
| med-gmail-triager-morning / -afternoon / -evening | 🔴 not yet — Day 4 | D4 |
| med-linkedin-poster | 🔴 not yet — Day 4 | D4 |
| med-x-poster | 🔴 not yet — Day 4 | D4 |
| med-threads-poster | 🔴 not yet — Day 4 | D4 |
| med-tiktok-poster | 🔴 not yet — Day 4 | D4 |
| med-instagram-poster | 🔴 not yet — Day 4 — inherit the EMCI notification-mode playbook from `em-contract-ops/playbooks/instagram-posting.md` | D4 |
| med-youtube-poster | 🔴 not yet — Day 4 | D4 |
| med-stripe-daily-monitor | 🔴 not yet — Day 4 | D4 |
| med-social-listener | 🔴 not yet — Day 4 | D4 |
| med-weekly-reporter | 🔴 not yet — Day 4 | D4 |

**Total target:** 16 scheduled tasks by Day 4 end per blueprint §10 Day 4 7:30 AM. Staggered cron offsets to avoid EMCI collision (EMCI `17 */4` → MedCI `7 */4`; other daily crons will offset similarly).

## Make.com

| Item | Status | Notes |
|---|---|---|
| M1 scenario (content→Buffer) | 🔴 not yet | D4-10:00 scaffold Modules 1–2 via MCP; Modules 3–9 built in UI (Lesson #6 — UI-only after API bootstrap) |
| Scenario ID | — | Capture here after creation |
| Connected GitHub account | 🟣 owner-gated (downstream of D1-9 1P vaults for OAuth tokens) |
| Connected Buffer org | 🟣 owner-gated (D1-17) |

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
