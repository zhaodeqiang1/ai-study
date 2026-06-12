---
name: testing-verification
description: Use when deciding, running, or documenting backend tests, Maven verification, frontend builds, SQL checks, failed validation, unavailable dependencies, or verification evidence for AI changes.
---

# Testing Verification

Use this repo skill for verification planning and execution.

Before verifying, read:

- `AGENTS.md`
- `harness-engineering/skills/testing-verification.md`
- `harness-engineering/contracts/ai-change-contract.md`
- `harness-engineering/contracts/testing-contract.md`
- `harness-engineering/checklists/unit-test-checklist.md`

If the change is AI, SQL, review-gate, or Harness-governance related, also read:

- `harness-engineering/evaluations/README.md`
- `harness-engineering/checklists/evaluation-checklist.md`

Only claim a test, build, or check passed if the command was actually run.

For non-trivial code changes, add or update unit tests first. If that is not possible, record the reason, substitute verification, residual risk, and follow-up test recommendation.

If verification cannot run, record the reason and remaining risk in the AI development record.
