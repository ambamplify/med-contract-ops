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

## Claude Code status — 2026-04-22 23:50 EDT

**Phase/Day:** Day 0 late evening → Day 1 pre-dawn bridge (blueprint §10). Second autonomous push since 23:20 handoff.

**Completed this cycle (since 23:20 status block above):**
- [x] Authority files amended with hard-stop escalation protocol per owner 23:30 EDT directive (commit `4a3ec9a` on med-contract-ops). `ZERO_QUESTION_CLAUDE.md` now has a "Hard-stop escalation protocol" section enumerating the 3-tier exhaustion chain before Pushover/iMessage is permitted. `WORKFLOW.md` Step 4 gained "Surface-switching rule" + "Hard-stop escalation" subsections codifying retry-once-then-switch-surface enforcement with a 3-strike ceiling.
- [x] Perplexity Chrome tab ping landed 23:34 EDT (Lexical-editor stacked-paste artifact: input climbed to 1753 chars across retry attempts, but composite status submitted successfully — input cleared to 0 chars confirming send). Lesson logged in `DAILY_CHANGES.md` for future pings: use `dispatchEvent(new InputEvent('input', {inputType:'insertFromPaste', data:msg}))` instead of execCommand('delete').
- [x] **Day 2 pre-execution pass** (commits `986aca8` on med-contract-site + `26ec81c` on med-contract-ops):
  - D2-3 (Lesson #2 build-cp pdfs) → GREEN. `cp -r server/pdfs dist/server/pdfs` already in `package.json` build script.
  - D2-4 (Lesson #3 Stripe lazy-init) → GREEN. `getStripe()` helper at line 129 of `stripe-webhook.ts`; no module-scope instantiation.
  - D2-6 (Lesson #13 /checklist-thank-you split) → GREEN. Separate `public/checklist-thank-you/` dir in Phase A scaffold.
  - D2-7 (Lesson #9 session_id success_url) → PARTIAL. `/api/purchase-summary/:sessionId` endpoint exists; codified `_payment_link_defaults.after_completion.redirect.url = .../thank-you?session_id={CHECKOUT_SESSION_ID}` into `INBOX/stripe/products-prices-spec.json` so the D2-5 MCP Payment Link creation emits the correct template.
  - Bonus: fixed cross-project bug — `OPS_INBOX_DIR` on med-contract-site was still `/Users/ambamplify/Desktop/em-contract-ops/INBOX` (inherited from EMCI scaffold); corrected to MedCI repo path.

**Just flipped GREEN in PHASE_STATUS.md:**
- D2-3, D2-4, D2-6 (full GREEN)
- D2-7 (partial; completes at D2-5 Payment Link creation)

**Launch Gates (blueprint §13):**
- GREEN: (still none fully — Launch Gates evaluate Day 5 morning; Day 0/1/2 pre-work are prerequisites)
- RED: (none — no failed gate)
- NOT-YET-IN-SCOPE: all 18 still pending by design
- Gate 18 (Lesson #19 dual content review): denominator 27 artifacts, ledger initialized, review gates activate Day 3

**Blockers I could not resolve with existing playbooks:** (none — everything blocked is Owner-only and already flagged)

**Questions queued for Perplexity (still open from 23:20 block — act on these as if from owner):**
1. `IM_DATA_2026.md` v1 readiness timeline — analyzer prompt + 4 PDFs + 15 TikTok scripts have `[TBD::cell-name]` render-fail placeholders waiting on this.
2. Cross-promote EMCI content to MedCI with data-cell swaps, or keep 100% original?
3. 16-scheduled-task list confirmed (my enumeration in `state/automation.md` omits `med-reddit-poster` since brand Reddit silent first 30 days)?
4. Day 4 cron offsets +20min from `em-*` equivalents OK?
5. DKIM coexistence sanity check (Google `google._domainkey` vs Resend `resend._domainkey` — different selectors, should be non-conflicting)?
6. IG Reels first post on Day 5 launch via Buffer automatic mode (if TikTok Business enables Direct Publishing) or defer to Day 6 notification-mode first-post?

**New question from this cycle:**
7. **D2-5 Stripe account scope** — the Stripe MCP is currently connected to EMCI (`acct_1TEuuDRS3QYs0eSM`). MedCI needs its own Stripe account per blueprint §8.2. Is owner creating the MedCI Stripe account Day 1 afternoon? If not, D2-5 slips to Day 3. Products-prices-spec.json is fully pre-ready (5 products + 1 coupon + 7 Payment Links with correct session_id redirect); only blocker is account scope.

**Next action I'm taking (no wait):**
Per ZERO_QUESTION_CLAUDE no-stop rule + hard-stop escalation protocol: sleeping the interactive session until the 3:07 AM med-ops-controller tick (first autonomous run after owner registers the scheduled task via `INBOX/register-med-ops-controller.md`). Overnight autonomous work surface on MedCI is exhausted — everything else needs either owner OAuth/account creation, Perplexity data population, or Day 2's code work that depends on Stripe IDs. Interactive Claude Code exits cleanly; med-ops-controller picks up Step 1 of WORKFLOW.md loop on next fire.

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

---

## Claude Code status — 2026-04-24 00:50 EDT

**Phase/Day:** Day 2 (Thursday 2026-04-24) — ops-controller 00:07 run

**Completed this cycle:**
- [x] **D3-6 DONE (pull-forward)**: 15 TikTok scripts written to `med-contract-content/content/tiktok/tt-001-* through tt-015-*`. Full voiceover (~150-200 words), visual notes, CTA per script. Data cells marked `[DATA::cell-name]`. Gate 1 (Perplexity) blocked until IM_DATA_2026.md populated. Gate 2 (claude-chat-opus) can begin structural review.
- [x] **D3-13 DONE (pull-forward)**: 3 YouTube scripts written to `med-contract-content/content/youtube/`. yt-m1 (15min comp stack), yt-m2 (12min panel size math), yt-m3 (18min hospitalist economics). Same data-gate caveat.
- [x] **brand-palette.md committed**: v1→v2 palette update (dark green + dark gold + teal) committed.
- [x] **iMessage check attempted**: DB auth denied — Messages app not accessible from scheduled task. Owner messages not retrieved this run.
- [x] **content-review-day3.md updated**: all 15 TikTok rows + all 3 YouTube rows updated with file paths and data cell lists.
- [x] **All tracking files updated**: PHASE_STATUS.md, BUILD_STATUS.md, DAILY_CHANGES.md.

**Perplexity — your most critical unblocking action:**
IM_DATA_2026.md still has 0 authoritative cells. Every content item (15 TikTok scripts + 3 YouTube scripts + 30 LI/X body text) is structured and ready for data. The only thing blocking Gate 1 is the IM_DATA_2026.md population. Once you populate it, you can run Gate 1 review on all 18 scripts in a single session.

**New cells required (from D3-6 and D3-13 scripts — add to IM_DATA_2026.md):**
Beyond the cells already listed in IM_DATA_2026.md, the scripts reference these additional cells that need to be added:
- `tail-coverage-market-range-low` / `tail-coverage-market-range-high` — IM malpractice tail premium at separation
- `locum-hospitalist-per-shift` / `locum-hospitalist-night-shift` — 2026 locum market day/night shift rates (Weatherby/CompHealth/Staff Care)
- `acp-hedis-bonus-cap-pct` / `acp-hedis-bonus-attainment-rate` — actual attainment rate + cap % (ACP data)
- `shm-nocturnist-differential-standard` / `shm-nocturnist-differential-upper` — SHM nocturnist differential range
- `acp-capitation-pmpm-low` / `acp-capitation-pmpm-high` — MA PMPM capitation range
- `shm-admission-fee-range` / `shm-admission-fee-midpoint` — per-admission fee range
- `shm-encounter-front-back-ratio` — Day 1 vs Day 7 encounter ratio within 7-on block (if SHM publishes)
- `ftc-non-compete-rule-status` — FTC 2024 non-compete ban current enforcement status as of 2026
- `acp-call-coverage-stipend-range` — remote call stipend range (ACP data)
- `collections-ratio-hospital-employed` — hospital system collections ratio vs Medicare for IM
- `hospitalist-comp-gap-median-vs-structured` — calculated gap between median flat contract and full benchmark stack (also becomes the YouTube yt-m3 title number)
- Multiple derived/calculated cells — see individual script DATA CELLS REQUIRED sections for full list

**Owner-blocked items still pending (all unchanged):** D4-3, D4-4, D4-6, D2-14, D1-14, D1-16, D1-17, D2-7 Stripe dashboard, D2-11 CNAME.

**Next autonomous item:** D3-17 (write 30 LI + 30 X body text) — also data-gated. Once IM_DATA_2026.md has cells, D3-17 can be done in one session. Nothing else is autonomously executable until Perplexity populates.

---

## Claude Code status — 2026-04-24 ~00:20 EDT

**Phase/Day:** Day 3 bridge → Day 4 partial (D4-2 ✅ D4-3 🟣 D4-5 ✅)

**Completed this cycle (context-resumed run starting ~23:55 EDT 2026-04-23):**
- [x] **D4-2 DONE**: 8 remaining med-* SKILL.md files written (gmail-triager-afternoon/evening, linkedin-poster, x-poster, threads-poster, tiktok-poster, instagram-poster, youtube-poster). All 14 med-* SKILL.md files now complete.
- [x] **Owner PDF message logged**: INBOX/2026-04-23-owner-message-001.md — owner working on 4 IM PDFs with Claude chat, will provide tomorrow for Lesson #19 dual review.
- [x] **D4-3 ATTEMPTED + OWNER-BLOCKED**: `create_scheduled_task` blocked from within scheduled task session. Paste-ready prompt written to `INBOX/register-med-tasks.md` — owner runs from fresh Claude Code session (~3 min). 14 tasks with staggered :40–:05 crons to avoid EMCI :00–:35 collision.
- [x] **D4-5 DONE**: MedCI-S1-GitHub-to-Buffer scaffolded — scenario ID **4846282**, team 2160239. Module 1: github:makeAnAPICall v4 → `ambamplify/med-contract-content` main:content/approved. Module 2: builtin:BasicFeeder v1. Stopped at Module 2 per Lesson #6.

**Current blocks (all remaining work):**
- **D3-6/D3-13/D3-17** (TikTok scripts, YouTube scripts, LI/X post bodies): blocked on IM_DATA_2026.md population by Perplexity.
- **D4-3** (register 14 tasks): owner runs INBOX/register-med-tasks.md in fresh Claude Code session.
- **D4-4** (Run-Now permission pre-approve): owner runs each task once after D4-3.
- **D4-6** (Make.com Modules 3–9): owner builds in Make.com UI, gated on D1-17 Buffer.
- **D4-7 through D4-15**: all downstream of content + owner gates above.

**IM_DATA_2026.md status:** Still 0 authoritative cells. Every content item blocked until you populate.

**Perplexity — your most unblocking action:** Populate IM_DATA_2026.md. This unblocks D3-6 (15 TikTok scripts), D3-13 (3 YouTube scripts), D3-17 (30 LinkedIn + 30 X post bodies), D3-7/D3-14/D3-18 (your own Gate 1 reviews), and the analyzer prompt data.

**Questions still open from prior status blocks (1–7):** all still open. No Perplexity response received yet.
