# Governance Model (Hybrid v3.0)

Date: 2026-02-26

## Core Principle

Governance is invariant.
Models are swappable.

Authority does not belong to infrastructure.
Authority belongs to defined roles.

---

## Roles

- WREN — Orchestrator / Merge Authority
- HOOKE — Builder
- MAXWELL — Reviewer

---

## Workflow

1. Objective posted in Slack (mention WREN)
2. WREN creates GitHub Issue
3. HOOKE opens PR referencing Issue
4. MAXWELL reviews (approve / block)
5. WREN merges after approval
6. Event logged in #system-log

---

## Hybrid Doctrine

Local-first execution via Ollama.
Cloud escalation via OpenRouter when thresholds are exceeded.

Escalations are logged.
Merge authority remains human-governed.
