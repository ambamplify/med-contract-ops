# INBOX/ — Directive Queue

**This directory is owner + Claude Code only. Perplexity has read-only access to the MCI repo and does not write here.**

## Workflow

1. **Owner** (or Claude Code via owner instruction) writes a directive file: `INBOX/{YYYY-MM-DD}-{topic}.md`
2. Claude Code's `med-ops-controller` scheduled task polls INBOX/ on each routine run
3. Items move INBOX → QUEUE → IN_PROGRESS → DONE as Claude Code triages

## Perplexity's role

Perplexity (MCI Space) reads state files (`PHASE_STATUS.md`, `BUILD_STATUS.md`, `COMPUTER_RESPONSE.md`, `CROSS_PROJECT_EMCI_CONTEXT.md`, content-review ledger, etc.) and:
- Performs Gate 1 fact-check reviews on every content artifact (Lesson #19, Launch Gate 18) — recorded in `state/content-review-day3.md`
- Drafts strategic recommendations in chat
- Drafts data corrections against `IM_DATA_2026.md` source links

Owner reviews. Owner instructs Claude Code to apply. Claude Code writes to INBOX/ on owner's behalf if a queued directive is needed, otherwise applies directly and updates state files + logs/DAILY_CHANGES.md.

Perplexity does NOT push to this repo. Read-only PAT or anonymous-public clone only.

## File format

Minimum fields:
- Source (Perplexity-recommended via owner / direct owner / Gate 1 fail / monitor / other)
- Priority (urgent / normal / low)
- Action requested (1 sentence)
- Context (what changed, why this is needed now)
- Acceptance criteria (how Claude Code knows it's done)
