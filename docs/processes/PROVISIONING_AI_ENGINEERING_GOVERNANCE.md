# AI-Assisted Engineering Governance Provisioning

This template includes the minimum enforcement layer for AI-assisted work:

- PR template: `.github/pull_request_template.md`
- CI gates: `.github/workflows/ci.yml`

## Required npm scripts

Projects created from this template must provide:

- `npm test`
- `npm run lint`
- `npm run typecheck`

CI will fail if any are missing or failing.

## Policy reference

The governing policy is maintained in `agentic-development-lab`:

- `ENGINEERING_GOVERNANCE_POLICY.md`

Projects should treat that document as the source of truth for AI-assisted contributions.
