# Slack Orchestration Guide (Hybrid v3.1)

Slack is the primary human interface for directing the Lab.

GitHub remains the governance and audit layer.

---

## Channels

- #wren — operational command channel
- #systemlog — append-only runtime and escalation log

No additional channels are required for core operation.

---

## #wren — Operational Surface

This is the only command channel.

Usage:

@WREN create Issue for TODAYLIST auth spike

Rules:

- Human posts objectives
- WREN responds
- No work occurs without a GitHub Issue
- Status updates may be posted here
- No casual discussion

This channel is signal-only.

---

## #systemlog — Audit Stream

This channel is append-only.

It records:

- Issue creation
- PR creation
- Review block / approval
- Merge events
- Model escalation events

No discussion.
No replies.
No commentary.

Format example:

OK — Escalated to cloud model — Issue #42 — reason: complex refactor

---

## Escalation Visibility

When escalation occurs (local → cloud), a log entry must include:

- Issue number
- Reason for escalation
- Outcome (ok / blocked)

All escalations must be visible.

---

## Discipline Model

- No work without Issue
- No merge without MAXWELL approval
- WREN merges only after approval
- All merges logged in #systemlog

Slack is orchestration.
GitHub is authority.
Logs are permanent.
