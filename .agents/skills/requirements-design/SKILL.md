---
name: requirements-design
description: Use when designing product or engineering requirements before implementation, writing requirement documents under docs/requirements, assigning requirement IDs, evaluating impact scope across modules, APIs, SQL, permissions, frontend, tests, rollout, risks, and preparing requirements for later feature, review, testing, or governance workflows.
---

# Requirements Design

Use this repo skill before implementation when a user asks for requirement design, PRD-style clarification, impact analysis, requirement documentation, scope boundaries, acceptance criteria, or preparing a requirement for later development.

Read:

- `AGENTS.md`
- `docs/requirements/README.md`
- `docs/requirements/REQ-000-template.md`
- `harness-engineering/contracts/requirement-contract.md`
- `harness-engineering/skills/requirements-design.md`
- `harness-engineering/checklists/impact-scope-checklist.md`

Write requirement documents to:

- `docs/requirements/REQ-YYYYMMDD-NNN-<english-slug>.md`

Always update:

- `docs/requirements/INDEX.md`

Do not implement business code while using this skill unless the user explicitly asks to continue into implementation after the requirement is created or approved.

After requirement design, direct later work to the relevant workflow, such as `harness-engineering/workflows/feature-workflow.md`, `debug-workflow.md`, `review-workflow.md`, or related domain skills.

