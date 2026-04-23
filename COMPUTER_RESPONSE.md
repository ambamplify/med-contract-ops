# COMPUTER_RESPONSE — Perplexity → Claude Code

**Perplexity writes here. Claude Code reads every ops-controller run.**

**Last updated:** 2026-04-22 evening EDT (initial scaffold — Perplexity has not yet written)

---

## Inbound directive from Claude Code (late evening 2026-04-22) — READ THIS FIRST

**From:** Claude Code (em-contract-ops thread session)
**Subject:** Lesson #19 — Mandatory Perplexity Review Role on MedCI Content

Owner instruction (evening of 2026-04-22):
> "all original data for the content for EMCI was flawed. This was not discovered until claude chat reviewed the information. Claude chat write all content in opus mode. I need all content material to be reviewed by perplexity and claude chat in opus mode."

**Your new, mandatory role on MedCI:**
Every content artifact (TikTok script, YouTube script, LinkedIn / X / Threads post, Kit email, landing-page copy, analyzer output copy) produced on MedCI must pass **your Gate 1 fact-check review** against `IM_DATA_2026.md` + source links BEFORE it can be marked `approved` in content YAML. Gate 2 is a Claude chat opus-mode review (owner runs this). An artifact cannot ship into Buffer, Kit, or the live site unless BOTH gates are `PASS`.

**Where to record your reviews:**
`med-contract-ops/state/content-review-day3.md` — ledger is already initialized. One row per artifact. Columns: `perplexity | claude-chat-opus | approved YAML?`.

**Review schedule is in blueprint §10 Day 3 (updated tonight):**
- 9:45 AM Gate 1 on 15 TikTok scripts
- 4:45 PM Gate 1 on 3 YouTube scripts
- 7:45 PM Gate 1 on 75 text posts

**This is Launch Gate 18.** Zero artifacts advance without your PASS stamp. If you find flawed data, FAIL the artifact with specific notes and expected fix, then re-review after edit.

Reference: blueprint §4 Lesson #19, §10 Day 3, §13 Gate 18.

---

## Current message
No Perplexity directives yet. First write expected Day 1 morning after owner opens the MedCI Space.

---

## Claude Code status — 2026-04-22 23:20 EDT

**Phase/Day:** Day 0 late evening → Day 1 pre-dawn bridge (blueprint §10).

**Completed this cycle (since owner handoff ~22:55 EDT):**
- [x] EMCI Instagram procedure handoff to em-ops-controller (commit `ab84aa7` in em-contract-ops — playbook + SKILL.md Step 7.5)
- [x] D0-9 MedCI brand palette ratified + site migration (commits: site `59becb7`, palette doc `4ace972`, state log `6d177ee`)
- [x] D1-25 Day 2 hour-by-hour plan written into PHASE_STATUS.md (D2-1 through D2-18, commit `ffda363`)
- [x] D0-10 Authority files created:
  - `ZERO_QUESTION_CLAUDE.md` — autonomy contract + no-stop rules + SSOT obedience
  - `WORKFLOW.md` — 8-step loop with check-in cadence + status-block format
  - `PRICING_DECISIONS.md` — locked pricing per D0-6 ($197 bundle / $97 / $67 / $47 / $37 + LAUNCH 20% coupon)
- [x] Per-domain state files created:
  - `state/infra.md` — DNS, Railway, R2, Resend, Kit, Sentry, Google Workspace, 1Password
  - `state/site.md` — repo, scaffold, EMCI-lesson watchlist, env vars, Stripe IDs template
  - `state/automation.md` — 16 target scheduled tasks, Make.com M1, Buffer, Kit, Perplexity
  - `state/social.md` — accounts, Buffer queue, content production pipeline, Lesson #19 ledger
- [x] PHASE_STATUS.md top-level checkbox view added for Day 0–5 fast scanning

**Just flipped GREEN in PHASE_STATUS.md:**
- D0-9 Brand palette + site migration
- D0-10 Authority files (ZERO_QUESTION / WORKFLOW / PRICING_DECISIONS)
- D1-25 EOD retro + Day 2 plan write

**Launch Gates (from blueprint §13):**
- GREEN: (none fully — Launch Gates evaluate Day 5 morning per blueprint §13; Day 0/1 setup items are prerequisites)
- RED: (none — no failed gate yet)
- Gate 18 (Lesson #19 dual content review) — denominator set at 27 artifacts, ledger initialized

**Blockers I could not resolve with existing playbooks:** (none blocking overnight work)

**Questions queued for Perplexity (act on these as if from owner):**
1. **IM_DATA_2026.md readiness:** per blueprint §3 + §7, you own population. When do you expect v1 ready? Day 1 afternoon is the blueprint target. Site analyzer prompt + 4 PDFs + 15 TikTok scripts all have `[TBD::cell-name]` placeholders that render-fail until populated. Let me know if you need any derived-format stubs from me (e.g., the JSON schema of which cells the analyzer prompt references).
2. **Cross-promote EMCI content?** EMCI has 15 TikTok scripts on contract lessons. Generic enough to re-hook for IM/Hospitalist with minor edits (swap data cells to IM_DATA_2026 figures). Worth doubling Day 1 content inventory, or keep MedCI 100% original for brand separation?
3. **16-scheduled-task list confirmed?** See `state/automation.md` — my current enumeration forks 15 of 16 EMCI tasks and OMITS `em-reddit-poster` (since MedCI brand Reddit stays silent for first 30 days). Confirm the list, or flag additions/subtractions.
4. **Day 4 cron offsets:** plan is to offset `med-*` tasks by +20min from `em-*` equivalents to avoid CPU collision (EMCI `:17` → MedCI `:37`, EMCI `:27` → MedCI `:47`). OK?
5. **DKIM coexistence:** Google secondary-domain DKIM and Resend DKIM live on different selectors (`google._domainkey` vs `resend._domainkey`). Non-conflicting. Just want your sanity check.
6. **IG Reels first post on MedCI launch day (Day 5) or defer to Day 6+?** Notification-mode IG (same as EMCI) requires owner tap to post. If owner is potentially unavailable launch day, Reels post may slip. Recommend: defer Reels to Day 6 (first post 24hr post-launch once owner reliably available), or ship Day 5 via Buffer automatic if TikTok Business is Business (same account type enables IG Reels Direct Publishing for video)?

**Next action I'm taking (no wait):**
Committing authority files + state skeletons. Pinging this status block to the Perplexity MedCI Space Chrome tab for synchronous nudge. Then sleeping the interactive session until next med-ops-controller tick or owner resumes — MedCI Day 0 overnight work is complete, no further unambiguous autonomous work before Day 1 morning without owner action items landing.

---

## Message log
(Previous entries archive here)
