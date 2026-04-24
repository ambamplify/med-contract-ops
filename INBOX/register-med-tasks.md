# D4-3: Register 14 MedCI Scheduled Tasks
**Created:** 2026-04-24 by ops-controller
**Action:** Owner pastes the prompt below into a fresh Claude Code session (NOT inside a scheduled task). ~3 minutes.

---

## Why this requires a fresh session

`mcp__scheduled-tasks__create_scheduled_task` is blocked from within scheduled task sessions (same as D0-3b for med-ops-controller). All 14 SKILL.md files are written and ready at `~/.claude/scheduled-tasks/med-*/SKILL.md`. Registration just needs to happen from an interactive session.

---

## Paste this into a fresh Claude Code session

```
Register 14 MedCI scheduled tasks via mcp__scheduled-tasks__create_scheduled_task. All SKILL.md files are already written at ~/.claude/scheduled-tasks/med-*/SKILL.md. Use the taskId, description, and cronExpression below. For the prompt field of each task, use: "Read /Users/ambamplify/.claude/scheduled-tasks/{taskId}/SKILL.md and execute every step in order."

Tasks to register (all LOCAL time, staggered from EMCI tasks which run at :00–:35):

1. taskId: med-daily-digest
   description: MedCI Daily Digest — morning briefing on Stripe activity, social queue health, INBOX items, open threads
   cronExpression: 42 7 * * *
   
2. taskId: med-stripe-daily-monitor
   description: MedCI Stripe Daily Monitor — pulls 24h Stripe activity, detects anomalies, escalates disputes/chargebacks/refunds
   cronExpression: 40 9 * * *

3. taskId: med-social-listener
   description: MedCI Social Listener — scans Reddit/forums for IM/hospitalist contract conversations, surfaces reply/post opportunities to INBOX
   cronExpression: 40 11 * * *

4. taskId: med-gmail-triager-morning
   description: MedCI Gmail Triager (Morning) — triage service@medcontractintel.com + admin@medcontractintel.com inboxes, surface customer issues, escalate urgent
   cronExpression: 40 8 * * *

5. taskId: med-gmail-triager-afternoon
   description: MedCI Gmail Triager (Afternoon) — triage @medcontractintel.com inboxes, respond to support issues, flag refund requests
   cronExpression: 40 13 * * *

6. taskId: med-gmail-triager-evening
   description: MedCI Gmail Triager (Evening) — final inbox sweep, close out day, queue follow-ups for tomorrow
   cronExpression: 40 18 * * *

7. taskId: med-weekly-reporter
   description: MedCI Weekly Reporter — Sunday 6:30pm weekly business summary, revenue, content performance, pipeline
   cronExpression: 10 19 * * 0

8. taskId: med-content-ideator
   description: MedCI Content Ideator — Monday 8:30am generates weekly IM/hospitalist content ideas across all platforms
   cronExpression: 10 9 * * 1

9. taskId: med-linkedin-poster
   description: MedCI LinkedIn Poster — daily 7:40am, auto-schedules new approved LinkedIn content to Buffer
   cronExpression: 40 7 * * *

10. taskId: med-x-poster
    description: MedCI X Poster — daily 7:45am, auto-schedules new approved X/Twitter content to Buffer
    cronExpression: 45 7 * * *

11. taskId: med-instagram-poster
    description: MedCI Instagram Poster — daily 7:50am, auto-schedules new approved Instagram content (feed + Reels) to Buffer
    cronExpression: 50 7 * * *

12. taskId: med-threads-poster
    description: MedCI Threads Poster — daily 7:55am, auto-schedules new approved Threads content to Buffer
    cronExpression: 55 7 * * *

13. taskId: med-tiktok-poster
    description: MedCI TikTok Poster — daily 8:00am, auto-schedules new approved TikTok videos to Buffer with Direct Publishing
    cronExpression: 0 8 * * *

14. taskId: med-youtube-poster
    description: MedCI YouTube Poster — daily 8:05am, uploads new approved YouTube videos via YouTube Data API v3 OAuth
    cronExpression: 5 8 * * *

After registering all 14, verify with mcp__scheduled-tasks__list_scheduled_tasks that all show nextRunAt timestamps. Then update /Users/ambamplify/MedContractIntel/med-contract-ops/PHASE_STATUS.md: mark D4-3 checkbox [x] and update the table row to "done YYYY-MM-DD". Commit and push.
```

---

## Notes

- Cron times are LOCAL (EDT). All MedCI tasks run at :40–:05 offset to avoid collision with EMCI tasks which run at :00–:35.
- Buffer channel IDs in poster SKILL.md files are PLACEHOLDERS (MEDCI_BUFFER_ORG_ID etc.) — update when owner connects Buffer org (D1-17).
- med-tiktok-poster uses `schedulingType: "direct"` (TikTok Business Direct Publishing per Lesson #17).
- med-gmail-triager tasks require MedCI Gmail MCP connection (owner D1-6/D1-7) before they can process email.
- After D4-3, owner must do D4-4: Run-Now on each task to pre-approve Chrome MCP + Bash permissions (Lesson #18). Without this, first cron fires will stall on permission prompt.
