# Day 1 Owner Actions — Wednesday 2026-04-23

**Compiled evening of 2026-04-22 by Claude Code (thread session). Owner unavailable tomorrow morning — autonomous med-ops-controller runs at 00:11, 04:11, 08:07 (digest), 12:11, 16:11, 20:11 EDT will execute all 🟢 Claude Code items. This file lists the 🟣 Owner-only items waiting for your return.**

Work through these in order. Each item has: (a) what to do, (b) where to do it, (c) what to verify, (d) where to log completion.

---

## CRITICAL PATH (launch-gate blockers)

### 1. Google Workspace — add medcontractintel.com as secondary domain + create 8 aliases

**Where:** https://admin.google.com → Account → Domains → Manage domains → Add a domain → "Secondary domain"

**Steps:**
1. Add `medcontractintel.com`
2. Verify ownership (Cloudflare DNS TXT — I'll have prepared this if Cloudflare zone is live; if not, verify via file upload fallback)
3. Once verified, go to Directory → Users → (pick your primary user) → User information → Email aliases
4. Add 8 aliases on `@medcontractintel.com`:
   - service@
   - admin@
   - billing@
   - support@
   - hello@
   - legal@
   - noreply@
   - dmca@

**Verify:** Send test email from external to each alias; confirm landing in Gmail inbox.

**Log:** Reply `1Y` to 8:07 digest, or append line to `logs/DAILY_CHANGES.md`.

---

### 2. NJ DBA filing — MedContractIntel

**Where:** NJ Division of Revenue https://www.njportal.com/DOR/BusinessRegistration/ (or your usual filing channel)

**Note:** You said on Day 0 you'd handle this personally — no Claude Code dependency. Not a launch-gate blocker, but confirms trade name registration.

**Log:** Reply `2Y` when filed (or `2 SKIP` if deferring post-launch).

---

### 3. Create 4 new 1Password vaults

**Where:** 1Password desktop app or https://ambamplify.1password.com

**Vaults to create:**
- `MedCI — Secrets` (API keys, service tokens)
- `MedCI — Infra` (Cloudflare, Railway, GitHub tokens)
- `MedCI — Stripe` (Stripe restricted keys, webhook secrets)
- `MedCI — Social` (TikTok, Reddit, LinkedIn, X, IG credentials)

**Log:** Reply `3Y` when all 4 exist.

---

### 4. Create Perplexity 1P service account + token → Perplexity MedCI Space memory

**Where:** https://start.1password.com → Integrations → 1Password Connect / Service Accounts → Create Service Account

**Steps:**
1. Name: `Perplexity MedCI Service Account`
2. Grant read-only access to the 4 MedCI vaults (from step 3)
3. Copy the service account token
4. Open Perplexity MedCI Space → Memory → paste the token
5. Also paste into `MedCI — Secrets` vault under name `Perplexity 1P Service Account Token`

**Verify:** Ask Perplexity MedCI Space to retrieve any secret from a MedCI vault.

**Log:** Reply `4Y` when token delivered to both locations.

---

### 5. Google Drive folder tree (per blueprint §5.5)

**Where:** https://drive.google.com (signed in as ambamplify@gmail.com)

**Tree to create at Drive root:**
```
MedContractIntel/
├── 00_Operations/
│   ├── Blueprint/
│   ├── Weekly_Reviews/
│   └── Launch/
├── 01_Content/
│   ├── Scripts/
│   ├── Video_Raw/
│   ├── Video_Approved/
│   └── Social_Drafts/
├── 02_Data/
│   ├── IM_DATA_2026/
│   ├── Research_Sources/
│   └── Scrapes/
├── 03_Customers/
│   ├── Testimonials/
│   ├── Support_Tickets/
│   └── Refund_Log/
├── 04_Legal/
│   ├── DBA/
│   ├── Trademark/
│   └── Contracts_Signed/
└── 05_Finance/
    ├── Stripe_Exports/
    ├── Tax/
    └── Receipts/
```

**Log:** Reply `5Y` when tree complete.

---

### 6. TikTok Business account registration (Lesson #17)

**Where:** TikTok app or https://www.tiktok.com/signup

**Steps:**
1. Create new handle `@medcontractintel` as **Business account** from the start (NOT Personal → Business later — that breaks Buffer Direct Publishing)
2. Also: convert existing `@emcontractintel` to Business if not already (per Lesson #17)
3. When onboarding asks for category: pick "Education" or "Business Services"

**Why now:** Buffer Direct Publishing for TikTok requires Business tier. If we register as Personal, launch Day 5 social posting breaks.

**Log:** Reply `6Y` when Business accounts confirmed.

---

### 7. Kit account — new signup on admin@medcontractintel.com

**Where:** https://app.kit.com/users/signup

**Steps:**
1. Sign up with `admin@medcontractintel.com` (will exist after step 1 above)
2. Disable double opt-in: Settings → Email preferences → uncheck double opt-in
3. Skip onboarding flows — I'll automate list + sequence creation Day 2

**Log:** Reply `7Y` when account exists + double opt-in off.

---

### 8. Buffer — create MedCI organization + OAuth all 5 socials

**Where:** https://buffer.com → Settings → Create new organization

**Steps:**
1. Name the org "MedContractIntel"
2. Connect channels: TikTok Business, Instagram, X, LinkedIn, Threads
3. Confirm Direct Publishing is available on all (especially TikTok — requires Business from step 6)

**Log:** Reply `8Y` with channel count connected.

---

### 9. Sentry — new project medcontractintel-production

**Where:** https://sentry.io → Projects → Create Project

**Steps:**
1. Platform: Node.js (will match MedCI site Day 2)
2. Name: `medcontractintel-production`
3. Team: default or create "MedCI"
4. Copy the DSN
5. Paste DSN into `MedCI — Secrets` vault as `Sentry DSN (medcontractintel-production)`

**Log:** Reply `9Y` when DSN saved.

---

### 10. Reddit — register brand account /u/MedContractIntel

**Where:** https://www.reddit.com/register

**Steps:**
1. Username: `MedContractIntel`
2. Email: `admin@medcontractintel.com` (after step 1)
3. Enable 2FA
4. Store creds in `MedCI — Social` vault

**Note:** This is the BRAND account. Your personal physician account stays separate (Reddit strategy same as EMCI — trust-building phase uses personal voice, not brand).

**Log:** Reply `10Y` when account created + 2FA on.

---

## ALREADY RESOLVED (Day 0 decisions locked — no owner action needed)

- **Pricing** — $197 bundle / $97 analyzer / $67 scripts / $47 wRVU / $37 shift-economics (D0-6 confirmed 2026-04-22 evening)
- **Better Stack** — deferred post-launch (D0-8 decision; D1-23 removed from plan)
- **med-ops-controller scheduled task** — registered + enabled (cron 7 */4 * * *, nextRunAt 2026-04-23T00:11:47Z)

---

## REPLY SHORTHAND

Each 8:07 digest will reference these 10 numbered items. Reply format:
- `1Y` = item 1 done
- `1N` = item 1 skipped/blocked (I'll ask why next digest)
- `1 BLOCKER: <text>` = item 1 stuck, here's why
- `PAUSE` = halt all med-* tasks (kill switch)
- `RESUME` = un-halt

---

## What's being done autonomously while you're away tomorrow

The 00:11, 04:11, 08:07, 12:11, 16:11, 20:11 EDT runs of med-ops-controller will execute (no owner input needed):

- ✅ R2 bucket `medci-social-media` (DONE 2026-04-22 23:32 UTC — pre-flight)
- 🟢 D1-2: Today's hour-by-hour already in PHASE_STATUS.md (populated Day 0)
- 🟢 D1-11: Gmail filters @medcontractintel.com → MCI/* labels (after aliases exist — requires step 1)
- 🟢 D1-12: Create 3 GitHub repos (requires GitHub token in 1P — requires step 3)
- 🟢 D1-13: Git init local med-contract-ops + push to GitHub (requires step 3 + D1-12)
- 🟢 D1-19: Resend domain verification (requires DNS — requires step 1 zone verification)
- 🟢 D1-21: Port legal pages from EMCI (can prep in INBOX; commit requires D1-13)

**Blockers for autonomous work:**
- Cloudflare DNS zone creation needs Cloudflare dashboard action (no MCP tool for zones — only R2/D1/KV/Workers). I'll write a paste-ready script to `INBOX/create-cloudflare-zone.md` for your 2-min click-through OR handle via Claude-in-Chrome when you're back.
- GitHub repo creation needs a PAT in `MedCI — Infra` vault (requires step 3).

---

**File last updated:** 2026-04-22 evening EDT by Claude Code (thread session, pre-Day-1).
