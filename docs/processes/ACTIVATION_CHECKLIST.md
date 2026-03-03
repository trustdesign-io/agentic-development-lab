# Activation Checklist

## Agentic Development Lab — OpenClaw Runtime Bring-Up (Hybrid v3.1)

Date: 2026-02-26

---

## 1. Pre-Install (Accounts & Access)

- GitHub organisation configured
  - Branch protection enabled
  - PR required for merge
  - WREN merge authority only
- Agent accounts created (WREN / HOOKE / MAXWELL)
- Slack workspace created
- Slack channels created:
  - #wren
  - #systemlog
- Slack App configured (Socket Mode enabled)
- OpenRouter account created + API key generated

---

## 2. Runtime Setup (Mac mini 32GB — Hybrid)

### Local Lane (Primary)

- Install Homebrew
- Install Ollama
- Pull tool-capable local model(s)
- Install OpenClaw runtime
- Configure runtime to use local model via Ollama
- Test local completion

Local lane must be stable before cloud lane is enabled.

---

### Cloud Lane (Escalation)

- Add OpenRouter API key to `.env`
- Restrict file permissions (`chmod 600 .env`)
- Configure escalation provider
- Test cloud completion
- Trigger one intentional escalation

Escalations must generate a log entry in #systemlog.

---

## 3. Secrets & Permissions

- Store Slack + GitHub + OpenRouter tokens in `.env`
- Confirm no secrets committed to Git
- Rotate tokens if roles change
- Confirm branch protections active

---

## 4. Hybrid Connectivity Test

- Verify Slack mention triggers WREN in #wren
- Verify Issue creation (local model)
- Verify PR creation (local model)
- Trigger one intentional cloud escalation
- Confirm escalation logged in #systemlog

---

## 5. Governance Validation

Simulate full workflow:

1. WREN creates Issue
2. HOOKE opens PR referencing Issue
3. MAXWELL blocks once
4. HOOKE revises
5. MAXWELL approves
6. WREN merges
7. Merge event logged in #systemlog

Governance must be invariant regardless of model lane.

---

## 6. Go / No-Go Criteria

Go when:

- Local lane stable
- Escalation works
- Merge policy enforced
- Logs consistent
- Slack topology clean (#wren / #systemlog only)

No-Go when:

- Uncontrolled merges
- Escalation undocumented
- Tool-calling unstable without fallback
- Slack channel noise dilutes signal

---

The lab is operational only when governance, logging, and escalation are verifiably stable.
