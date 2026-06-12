# 代码审查门契约

非平凡代码实现后，必须满足本契约才能进入验证。

## 输入

- 关联需求。
- 本次修改文件。
- 本次变更计划。
- 对应技能文件。
- 对应约束文件。

## 必读

- `harness-engineering/workflows/review-workflow.md`
- `harness-engineering/skills/code-review.md`
- `harness-engineering/checklists/code-review-gate-checklist.md`

## 输出

审查门必须输出一个结论：

- `Pass`：可以进入验证。
- `NeedsFix`：必须先修复，再重新审查。
- `Blocked`：需要用户确认或外部条件。

## 必查项

- 是否满足需求验收标准。
- 是否只修改允许范围。
- 是否有权限、安全、数据、事务、并发风险。
- 是否有 SQL 回滚和验证。
- 是否有可执行验证命令。
- 是否有未记录风险。

## 记录

审查结果必须写入 AI 开发记录。

