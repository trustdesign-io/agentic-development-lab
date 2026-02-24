# Project Creation Process

## Intent

Defines the canonical process for instantiating a new project within the Agentic Development Lab.

Project creation is a governance action.

It provisions structure, not implementation.

---

## 1. Authority Model

- Human defines strategic intent.
- WREN provisions infrastructure.
- HOOKE does not create repositories.
- MAXWELL does not create repositories.

Project creation is orchestrated, not improvised.

---

## 2. Preconditions

Before provisioning:

- `project-starter` repository exists
- `project-starter` is marked as a GitHub Template repository
- GitHub token used by WREN has:
  - `repo` scope
  - Organisation repo creation permissions

---

## 3. Triggering Project Creation

Project creation must be explicitly requested.

Example Slack command:

    @WREN create a new project from project-starter called {PROJECT_NAME}

WREN must:

1. Restate the request in one line.
2. Confirm repository visibility (public/private).
3. Confirm organisation (if ambiguous).
4. Proceed only after clarity.

---

## 4. Provisioning Steps (Automated)

WREN performs:

1. Create new repository from template via GitHub API.
2. Apply branch protection rules.
3. Create initial Issue:
   - "Complete SPEC.md (MVP definition)"
4. Optionally create a Project board.
5. Log provisioning event in Slack.

WREN does not:

- Modify SPEC content.
- Add implementation code.
- Expand scope beyond template.

---

## 5. First-Day Ritual (Human Required)

After provisioning:

Human must complete:

- Problem
- User
- MVP Scope
- Non-Goals
- Acceptance Criteria

No implementation begins before SPEC + Definition of Done are written.

---

## 6. Transition to Operational Mode

Once SPEC is completed:

    @WREN convert SPEC.md into a sequenced Issue list (small, scoped).

Workflow proceeds under the standard governance model:

Human → WREN → HOOKE → MAXWELL → WREN

---

## 7. Safety Rules

- No project is created implicitly.
- No repositories are created without explicit Slack mention.
- Destructive repo actions require explicit confirmation.
- Repository naming must be deliberate and stable.

---

## 8. Versioning

Changes to this process require:

- GitHub Issue
- Pull Request
- MAXWELL approval
- Merge by WREN

Provisioning policy is part of Lab governance and must not drift.
