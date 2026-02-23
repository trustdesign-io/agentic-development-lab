# Agentic Development Lab

## Governance Model

Version: 1.0

---

## 1. Workflow Overview

The Lab operates through structured pull request governance.

### Flow:

1. Strategic objective defined by Human.
2. WREN converts objective into Issues.
3. HOOKE implements.
4. HOOKE opens Pull Request.
5. MAXWELL reviews.
6. If approved:
   - CI passes
   - No human halt flag
7. WREN merges.
8. Merge logged to Slack.

---

## 2. Role Separation

HOOKE:

- May implement.
- May open PRs.
- May not merge.
- May not formally review.

MAXWELL:

- May review.
- May approve or block.
- May not merge.
- May not implement full features.

WREN:

- May orchestrate.
- May enforce review.
- May merge after approval.
- May not implement production features.

Human:

- May override.
- May halt merge.
- May refactor directly (transparently).
- Retains final authority.

---

## 3. Override Policy

If the Human disagrees with MAXWELL:

- Override must be explicit.
- Rationale must be documented in the PR.
- Silent intervention is prohibited.

---

## 4. Production Failure Protocol

If a defect reaches production:

- Responsibility lies with the Human.
- Post-mortem documented.
- Governance model refined if required.

Agents are not blamed.
System discipline is improved.

---

## 5. Version 1 Constraints

- One Builder (HOOKE).
- One Reviewer (MAXWELL).
- WREN merges only after approval.
- No parallel builders.
- No autonomous environment modification.
- No financial autonomy.

Scale is reserved for future versions.
