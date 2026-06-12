---
name: code-review
description: Use when reviewing code, running the post-implementation review gate, inspecting diffs, checking production risk, security, permissions, transactions, SQL rollback, tests, or Harness rule compliance.
---

# Code Review

Use this repo skill for standalone reviews and post-implementation review gates.

Before reviewing, read:

- `AGENTS.md`
- `harness-engineering/workflows/review-workflow.md`
- `harness-engineering/skills/code-review.md`
- `harness-engineering/checklists/code-review-gate-checklist.md`
- `harness-engineering/contracts/review-gate-contract.md`

For SQL or AI changes, also read the matching contract:

- `harness-engineering/contracts/sql-migration-contract.md`
- `harness-engineering/contracts/ai-feature-contract.md`

Review conclusions must be one of:

- `Pass`
- `NeedsFix`
- `Blocked`

Write the review result into the AI development record for non-trivial implementation work.

