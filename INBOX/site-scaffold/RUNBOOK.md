# Day 2 Site-Scaffold Runbook — MedContractIntel

**Drafted:** 2026-04-22 20:32 EDT (Day 0 autonomous push)
**Executes:** Day 2 Thursday 2026-04-24 morning by Claude Code thread session
**Source site:** `/Users/ambamplify/Desktop/em-contract-site/` (EMCI, fully working, Railway-deployed)
**Target repo:** `git@github.com:ambamplify/med-contract-site.git` (empty shell, created Day 1 D1-12)
**Target local:** `/Users/ambamplify/MedContractIntel/med-contract-site/`

---

## 0. Pre-flight gates (runner verifies BEFORE any `cp -R`)

- [ ] `med-contract-site` GitHub repo exists and is accessible via HTTPS keychain path.
- [ ] No local folder at `/Users/ambamplify/MedContractIntel/med-contract-site/` yet (fresh scaffold). If exists, halt — Day 0 push didn't pre-populate this on purpose.
- [ ] Railway MCP connected OR owner has logged into Railway dashboard and we can drive via `claude-in-chrome`.
- [ ] MedCI Stripe test-mode account scope available (spec: `INBOX/stripe/products-prices-spec.json`).
- [ ] Anthropic API key for MedCI project is issued OR we reuse the existing personal key with a `MEDCI-` prefix in metadata (owner decision — flag if unclear).

**If any gate fails:** write diagnosis to `ESCALATED/day2-site-blocker-YYYY-MM-DD.md` and halt.

---

## 1. Fork strategy decision

**Decision: Clone-and-rebrand, NOT GitHub fork.**
- GitHub fork carries history + upstream tracking we don't want.
- `git clone` the EMCI repo to a fresh folder, delete `.git`, init new `.git`, point at `ambamplify/med-contract-site` remote. Clean slate, independent lineage.

**Files that must NOT be carried over from EMCI:**
- `em-contract.db`, `em-contract.db-shm`, `em-contract.db-wal` (SQLite DB files with EMCI analyses).
- `.env` (EMCI API keys, Stripe secrets).
- `dist/` (old EMCI build artifacts).
- `node_modules/` (fresh install for MedCI).
- `.claude/` (EMCI local Claude settings — we use parent folder's).
- Any `emails-2-7-clean.md`, `CLAUDE_TASKS.md`, or one-off ops files — leave in EMCI only.

---

## 2. Execute — scaffold script

```bash
#!/usr/bin/env bash
set -euo pipefail

SRC=/Users/ambamplify/Desktop/em-contract-site
DST=/Users/ambamplify/MedContractIntel/med-contract-site

if [ -d "$DST" ]; then
  echo "FAIL: $DST already exists. Runner expected fresh directory."
  exit 1
fi

# Clone structure (everything except excludes).
# Use rsync so we can exclude precisely.
rsync -a \
  --exclude '.git/' \
  --exclude 'node_modules/' \
  --exclude 'dist/' \
  --exclude '.env' \
  --exclude 'em-contract.db' \
  --exclude 'em-contract.db-shm' \
  --exclude 'em-contract.db-wal' \
  --exclude 'emails-2-7-clean.md' \
  --exclude 'CLAUDE_TASKS.md' \
  --exclude '.claude/' \
  --exclude '.DS_Store' \
  "$SRC/" "$DST/"

cd "$DST"

# Fresh git repo wired to MedCI remote
git init -b main
git config credential.helper osxkeychain
git remote add origin https://github.com/ambamplify/med-contract-site.git

# Sanity check — no EMCI DB shouldered in
test ! -f em-contract.db || { echo "FAIL: EMCI DB copied"; exit 2; }
test ! -f .env           || { echo "FAIL: EMCI .env copied"; exit 3; }

echo "Scaffold complete: $DST"
```

---

## 3. Find-replace rebrand (deterministic)

Run in order. All `sed` invocations are `-i ''` (macOS in-place). Skip binary files.

```bash
cd /Users/ambamplify/MedContractIntel/med-contract-site

# Text replacements, most-specific first
find . -type f \( \
  -name "*.ts" -o -name "*.tsx" -o -name "*.js" -o -name "*.jsx" -o \
  -name "*.html" -o -name "*.json" -o -name "*.md" -o -name "*.css" -o \
  -name "*.toml" -o -name "*.py" -o -name ".gitignore" -o -name "*.yaml" \
  \) \
  -not -path "./node_modules/*" \
  -not -path "./.git/*" \
  -exec sed -i '' \
    -e 's/EM Contract Intel™/MedContractIntel™/g' \
    -e 's/EM Contract Intel/MedContractIntel/g' \
    -e 's/emcontractintel\.com/medcontractintel.com/g' \
    -e 's/em-contract-intel/medcontractintel/g' \
    -e 's/em-contract-site/med-contract-site/g' \
    -e 's/em-contract\.db/med-contract.db/g' \
    -e 's/EMERGENCY MEDICINE/INTERNAL MEDICINE \& HOSPITALIST/g' \
    -e 's/Emergency Medicine physician/Internal Medicine or Hospitalist physician/g' \
    -e 's/emergency medicine physicians/internal medicine \& hospitalist physicians/g' \
    -e 's/Emergency Medicine/Internal Medicine \& Hospitalist/g' \
    -e 's/emergency medicine/internal medicine and hospitalist/g' \
    {} \;

# Specialty-specific copy that needs manual review (NOT a mechanical swap)
# analysis-prompt.ts has EM-specific clause analysis logic.
# This file is REWRITTEN manually, not sed'd. See section 4.
echo "analysis-prompt.ts requires manual rewrite — see Section 4"
```

**Expected count check (run after):**
```bash
# Should be 0
grep -rE "emcontractintel|EM Contract Intel" /Users/ambamplify/MedContractIntel/med-contract-site/ \
  --include='*.ts' --include='*.tsx' --include='*.html' --include='*.json' --include='*.md' \
  | wc -l
```

If not 0, inspect the hits. Likely remainders: commented `//` references, backup files, or regex-escaped strings.

---

## 4. Files that need MANUAL rewrite (not mechanical sed)

| File | Why | Action |
|---|---|---|
| `server/analysis-prompt.ts` | Entire clause-analysis prompt is tuned for EM contracts (shift models, ED-specific terms, ACEP benchmarks). | Rewrite for IM/Hospitalist: swap ACEP→MGMA/SHM/AMGA/AAMC/Doximity; add nocturnist differential, census/panel-size commitments, admit cap, observation billing, tail coverage variants; remove ED-specific boilerplate. Pull from `MEDCONTRACTINTEL_BLUEPRINT.md` §8.3. |
| `server/letter-docx.ts` | Counter-proposal letter template cites EM benchmarks + specialty-specific clauses. | Rewrite counter-proposal clauses for IM/hospitalist context. Same blueprint section. |
| `server/email-service.ts` | Welcome email + 2-week follow-up copy references "your ED contract" in places. | Find-replace + a pass-through for "ED"→"hospitalist/IM" language the sed didn't catch. |
| `public/index.html` | Hero copy, value-prop bullets, product grid copy — all EM. | Rewrite hero + product grid from blueprint §11 homepage section. Nav labels stay identical. |
| `public/pages/analyzer.html` | Analyzer description + FAQ. | Rewrite to IM/hospitalist framing. |
| `public/pages/about.html` (if exists) | Founder bio + operator narrative — mostly stays but mentions "emergency physician" explicitly. | Swap to internal-medicine framing; owner approves founder-bio copy Day 2 afternoon. |
| `client/src/**` React components | EM-specific labels in the analyzer form (employer-type options include EM-specific items like "CMG, hospital-employed ED"). | Update employer-type enum values to IM/hospitalist options: `hospital-employed`, `private-group`, `academic`, `locums`, `CMG`, `critical-access`, `teaching-service`. |
| `shared/schema.ts` | Drizzle schema. Mostly reusable but table-name `em_analyses` etc. needs rename. | Rename `em_*` tables to `med_*`. Fresh DB anyway — no migration. |
| `drizzle.config.ts` | Points at `em-contract.db`. | After sed pass, confirm points at `med-contract.db`. |
| `railway.json` / `railway.toml` | Service name probably `em-contract-intel`. | After sed pass, confirm service name is `medcontractintel` or similar. |

**Lesson #19 applies to site copy that's user-facing marketing content.** Hero bullets, product-grid descriptions, analyzer FAQ, and about-page founder bio all need Perplexity + Claude-chat-opus dual review before they can advance from `draft` to `approved` in `state/content-review-day3.md`. Schedule those reviews into the Day 3 / Day 4 content-review slots.

---

## 5. Fresh artifacts (MedCI-only, don't exist in EMCI)

- `med-contract.db` — create fresh. Drizzle will auto-initialize from the updated `shared/schema.ts` on first `npm run db:push`.
- `.env` — populate from MedCI-specific values:
  - `ANTHROPIC_API_KEY`: MedCI scope (or shared personal key with MEDCI metadata — owner confirms)
  - `EMAIL_PROVIDER=resend`, `EMAIL_API_KEY=<from Resend MedCI>`, `EMAIL_FROM=noreply@medcontractintel.com`
  - `STRIPE_SECRET_KEY` (test mode Day 2, live mode Day 4 afternoon)
  - `STRIPE_WEBHOOK_SECRET` (populated after webhook endpoint is created Day 2)
  - `DATABASE_URL=file:./med-contract.db` (SQLite for launch; Postgres migration post-launch)
  - `SENTRY_DSN` (from owner ESCALATED #9)
- `.env.example` — commit-safe template listing all keys without values.
- Fresh favicon + brand icons — sourced from Day 1 brand asset drop (owner-driven).
- `public/robots.txt` — update `Sitemap:` line.
- `public/sitemap.xml` — regenerate with MedCI URLs.
- Drop-in legal pages from `/Users/ambamplify/MedContractIntel/med-contract-ops/INBOX/legal-pages/` per that dir's README.

---

## 6. First deploy — Railway

```
1. Connect `med-contract-site` GitHub repo to Railway as new project.
2. Copy env vars from EMCI Railway project, rewriting each per Section 5.
3. Set custom domain: medcontractintel.com (triggers Cloudflare DNS pointer — A/AAAA records go to Railway IPv4/IPv6).
4. After first successful build: copy Railway's issued IP into Cloudflare DNS (PHASE_STATUS D1-5 step still pending for A/AAAA — finish here).
5. Verify: curl -I https://medcontractintel.com/ returns 200 and body contains "MedContractIntel".
```

---

## 7. First commit + push

```bash
cd /Users/ambamplify/MedContractIntel/med-contract-site

git add -A
git commit -m "$(cat <<'EOF'
Initial MedContractIntel site scaffold — forked from EMCI

Clone of em-contract-site rebranded for Internal Medicine &
Hospitalist contracts per MEDCONTRACTINTEL_BLUEPRINT.md §8.

- Deterministic sed find-replace for brand tokens
- Manual rewrite of analysis-prompt.ts, letter-docx.ts,
  email-service.ts, public/index.html, analyzer.html,
  shared/schema.ts (per RUNBOOK Section 4)
- Legal pages dropped in from med-contract-ops/INBOX/legal-pages/
- Fresh .env, .env.example, med-contract.db
- Railway project wired up, medcontractintel.com pointing

Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>
EOF
)"

git push -u origin main
```

---

## 8. Post-deploy acceptance tests (Day 2 EOD)

- [ ] `https://medcontractintel.com/` returns 200, body has "MedContractIntel" in title.
- [ ] `https://medcontractintel.com/analyzer` loads analyzer form.
- [ ] `https://medcontractintel.com/pages/privacy.html` loads.
- [ ] `https://medcontractintel.com/pages/terms.html` loads.
- [ ] `https://medcontractintel.com/pages/disclaimer.html` loads.
- [ ] `https://medcontractintel.com/pages/dmca.html` loads.
- [ ] `https://medcontractintel.com/refund` (redirect to index.html) loads.
- [ ] `grep -rE "emcontractintel|EM Contract Intel" /Users/ambamplify/MedContractIntel/med-contract-site/ --include='*.ts' --include='*.tsx' --include='*.html'` returns 0 hits.
- [ ] Stripe test-mode checkout (Payment Link for `analyzer` slug) returns to `/thank-you` and webhook fires.
- [ ] One smoke-test analysis submission round-trips without error in the new SQLite DB.

---

## 9. Open decisions flagged for Day 2 owner check (non-blocking)

- **Anthropic API key scoping**: new MedCI-only key vs. shared personal key with metadata. Default: shared personal, add `metadata.business=medci` to every Messages API call.
- **Founder bio on About**: which narrative? Day 2 afternoon copy write.
- **Brand icon / favicon**: source from Day 1 brand asset drop. If owner hasn't dropped assets by Day 2 morning, ship with plain text wordmark + a 1-letter "M" favicon placeholder; swap later.
- **SQLite vs. Postgres**: launch on SQLite (matches EMCI, good enough for 5-day build window). Post-launch migration to Postgres is a separate project.

---

**Drafted by:** Claude Code (thread)
**Review status:** `draft` — Day 2 runner confirms each step is still-correct before executing (blueprint may have drifted).
