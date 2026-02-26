# Project Creation Process — Technical (Hybrid v3.0)

Date: 2026-02-26

## Environment Setup

### Local Lane
- Install Ollama
- Pull tool-capable model
- Configure OpenClaw to use local model

### Cloud Lane
- Add OpenRouter API key to `.env`
- Restrict permissions
- Test completion call
- Test tool-call
- Validate escalation path

---

## Escalation Test

Intentionally trigger a cloud escalation and confirm:

- Log entry created
- Issue reference present
- Reason documented

---

## Security

- No secrets committed
- Tokens rotated if roles change
