# MedCI Social State

**Last updated:** 2026-04-22 23:15 EDT
**Owner:** Claude Code (autonomous writes) — Perplexity reads

---

## Accounts

| Platform | Handle | Status |
|---|---|---|
| TikTok | @medcontractintel | 🟣 owner-gated (D1-14) — MUST be Business account from day one (Lesson #17); enables Direct Publishing via Buffer |
| Instagram | @medcontractintel | 🟣 owner-gated — Business account required for Buffer scheduling; create simultaneously with TikTok |
| LinkedIn Company Page | MedContractIntel | 🟣 owner-gated |
| X (Twitter) | @medcontractintel | 🟣 owner-gated |
| Threads | @medcontractintel | 🟣 owner-gated (inherits from IG) |
| YouTube | @medcontractintel Brand Account under ambamplify@gmail.com | 🟣 owner-gated (D3-2:30 PM) |
| Reddit (personal, value-add only) | same as owner's EMCI Reddit pattern | 🟣 owner — no brand mention first 30 days |
| Reddit brand `/u/MedContractIntel` | 🟣 owner-gated (D1-22) | 0 posts for first 30 days — karma-building only via upvotes/comments |
| Substack | medcontractintel.substack.com | 🟣 owner-gated — weekly long-form |

## Buffer queue (populated Day 4+)

### TikTok
- 🔴 0 scheduled — queue fills Day 4 afternoon after Day 3 content production

### IG (feed + Reels)
- 🔴 0 scheduled
- Static feed posts will use Buffer `automatic` mode with catbox image URLs (proven on EMCI)
- Reels will use Buffer `notification` mode until/unless custom R2 domain `media.medcontractintel.com` is bound (proven on EMCI — `em-contract-ops/playbooks/instagram-posting.md`)

### LinkedIn / X / Threads
- 🔴 0 scheduled — Day 3 content production → Day 4 Buffer scheduling

### YouTube
- 🔴 0 scheduled — Day 4 manual upload test for YT #1 via `upload_youtube.py` script

## Content production pipeline

| Stage | Status |
|---|---|
| 15 TikTok scripts (IM-specific hooks) | 🔴 Day 3 morning |
| Perplexity Gate 1 review (Lesson #19) | 🔴 Day 3 9:45 AM |
| Claude-chat-opus Gate 2 review | 🔴 Day 3 10:15 AM (owner runs) |
| 15 TikTok videos via ElevenLabs + FFmpeg | 🔴 Day 3 10:40 AM (Claude Code production) |
| R2 upload + content YAML update | 🔴 Day 3 2:00 PM |
| 3 YouTube long-form scripts | 🔴 Day 3 4:00 PM |
| 3 YouTube videos via Remotion | 🔴 Day 3 5:30 PM |
| 30 LinkedIn + 30 X + 15 Threads posts | 🔴 Day 3 7:00 PM |

## Lesson #19 review ledger

- File: `state/content-review-day3.md` (pre-populated 2026-04-22 evening)
- Tracked: 27 artifacts (15 TikTok + 3 YouTube + 1 text-lane placeholder + 8 site-copy rows)
- Pass criteria: BOTH Perplexity PASS + Claude-chat-opus PASS before YAML `approved: true`
- Launch Gate 18 denominator set

## IG Reels asset hosting

- Bucket: `medci-social-media` (created 2026-04-22 23:32 UTC)
- Dev URL: `pub-<hash>.r2.dev/...` — once public access attached
- Custom domain (future): `media.medcontractintel.com` — unlocks Direct Publishing for Reels (Meta rejects `pub-*.r2.dev` for video containers). Lower priority than getting MVP to launch first.

## Content calendar

- Template: `med-contract-content/` repo (pre-seeded 15 TikTok rows + 3 YouTube rows with hooks + dates + `data_cells` refs)
- LinkedIn / X / Threads / IG / Substack: 🔴 empty — Day 3 7:00 PM populates text lanes

## Open questions for Perplexity

1. **Cross-promote EMCI content?** EMCI has 15 TikTok scripts on contract lessons. They're generic enough to run on MedCI too with minor re-hooks (replace "physician" with "internist/hospitalist" where applicable, swap data cells to IM_DATA_2026 figures). Worth the re-hook cost to double Day 1 content inventory, or keep MedCI content 100% original?
2. **IG Reels first-post cadence:** EMCI currently has Reel 01 live + 7 scheduled at 11:00 UTC daily (notification mode). For MedCI, should Day 5 launch day include a first IG Reel, or does Reels launch push to Day 6+ once owner approves from notification?
