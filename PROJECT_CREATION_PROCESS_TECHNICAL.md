# Project Creation Process — Technical Implementation

## Intent

Defines the technical mechanism by which WREN provisions new repositories
from the `project-starter` template.

This document complements PROJECT_CREATION_PROCESS.md.

---

## 1. GitHub Template Requirement

The repository `project-starter` must:

- Exist in the organisation
- Be marked as "Template repository"
- Have stable main branch
- Contain no environment secrets

---

## 2. GitHub API Endpoint

WREN uses:

POST /repos/{template_owner}/{template_repo}/generate

Example:

POST /repos/trustdesign-io/project-starter/generate

Body:

{
"owner": "trustdesign-io",
"name": "{project-name}",
"private": true,
"include_all_branches": false
}

---

## 3. Required GitHub Token Scopes

The token used by WREN must have:

- repo
- admin:repo_hook (if hooks used)
- write:org (if organisation policy requires)

Token must:

- Be stored server-side only
- Never committed to Git
- Be rotated periodically

---

## 4. Post-Creation Configuration

After repository creation, WREN should:

1. Apply branch protection rules:
   - Require PR
   - Require review
   - Restrict direct pushes to main

2. Create initial Issue:
   Title: "Complete SPEC.md (MVP definition)"

3. Optionally:
   - Create a GitHub Project board
   - Add default labels (bug, enhancement, spike, governance)

4. Log event to Slack:

   OK — Repository {name} created from template — <repo_link>

---

## 5. Safety Constraints

WREN must not:

- Overwrite existing repositories
- Delete repositories
- Rename repositories
- Change visibility without explicit confirmation

Destructive repo actions require explicit Slack confirmation.

---

## 6. Failure Handling

If repository creation fails:

WREN must:

- Report the exact API error
- Not retry blindly
- Not create partial infrastructure

Provisioning must be atomic.

---

## 7. Separation of Concerns

PROJECT_CREATION_PROCESS.md defines policy.
This document defines mechanics.

Changes to either require:

- Issue
- PR
- MAXWELL approval
- Merge by WREN
