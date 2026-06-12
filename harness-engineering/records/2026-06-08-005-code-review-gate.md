# 2026-06-08-005: 补充实现后代码审查门

## 关联需求

- `docs/requirements/REQ-20260608-005-code-review-gate.md`

## 背景

用户指出：流程图虽然有代码审查分支，但没有说明需求新增代码实现后如何走到审查。合理的生产流程应该是实现后先审查，通过后再验证。

## 本次改动

- 在 HTML 主流程图中将流程调整为：实现变更 -> 审查门 -> 验证 -> 独立记录。
- 在 HTML 详细分支流程图中增加 “实现后审查门”。
- 更新分支文件走向表，说明审查门必须读取、按需读取和必须更新的文件。
- 新增 `harness-engineering/checklists/code-review-gate-checklist.md`。
- 更新 `AGENTS.md`、`feature-workflow.md`、`review-workflow.md`、`production-readiness.md` 和 `feedback-loop.md`。
- 更新实现功能命令模板，要求实现后进入审查门，通过后再验证。
- 更新需求索引、记录索引和变更日志。

## 关键决策

- 代码审查既保留为独立任务分支，也作为新功能、Bug 修复、SQL、AI 能力和前端变更后的主线门禁。
- 审查门必须输出 `Pass`、`NeedsFix` 或 `Blocked`。
- `NeedsFix` 必须回到实现修复，再重新审查。

## 修改文件

- `docs/harness-engineering-guide.html`
- `AGENTS.md`
- `harness-engineering/workflows/feature-workflow.md`
- `harness-engineering/workflows/review-workflow.md`
- `harness-engineering/checklists/code-review-gate-checklist.md`
- `harness-engineering/checklists/production-readiness.md`
- `harness-engineering/governance/feedback-loop.md`
- `harness-engineering/commands/implement-feature.md`
- `.claude/commands/implement-feature.md`
- `docs/requirements/REQ-20260608-005-code-review-gate.md`
- `docs/requirements/INDEX.md`
- `harness-engineering/records/2026-06-08-005-code-review-gate.md`
- `harness-engineering/records/INDEX.md`
- `harness-engineering/changes/CHANGELOG.md`

## 验证

- 检查 HTML 是否包含 “审查门” 和 “实现后审查门”。
- 检查 `feature-workflow.md` 是否包含审查门步骤。
- 检查 `review-workflow.md` 是否包含审查结论。
- 检查 `AGENTS.md` 是否包含非平凡代码实现后必须进入审查门。
- 检查索引是否包含 `REQ-20260608-005` 和 `2026-06-08-005`。

## 风险

- 本次只修改文档和 Harness 规则，不影响运行时代码。
- 后续执行真实代码任务时，需要 AI 按审查门规则实际执行自检或请求审查。

## 后续事项

- 后续可以进一步把审查门拆成后端审查、前端审查、SQL 审查、AI 安全审查四个子清单。
