# REQ-20260608-005: 补充实现后代码审查门

## 状态

Verified

## 背景

用户指出当前流程图中“代码审查”只是一个独立分支，没有体现新需求代码实现后必须进入审查。对于生产可用项目，新功能或非平凡代码实现后应先经过审查门，再进入验证和记录。

## 目标

- 将代码审查从旁路分支补充为实现后的主线门禁。
- 明确审查门读取的文件和输出结论。
- 更新 HTML 流程图、详细分支图和分支文件走向表。
- 更新功能开发 workflow、审查 workflow、反馈循环和生产检查清单。

## 范围

包含：

- `docs/harness-engineering-guide.html`
- `AGENTS.md`
- `harness-engineering/workflows/feature-workflow.md`
- `harness-engineering/workflows/review-workflow.md`
- `harness-engineering/checklists/code-review-gate-checklist.md`
- `harness-engineering/checklists/production-readiness.md`
- `harness-engineering/governance/feedback-loop.md`
- 需求索引、记录索引、变更日志。

不包含：

- 修改业务运行代码。
- 执行真实代码审查工具或构建命令。

## 验收标准

- HTML 主流程图中存在 “审查门”。
- HTML 详细流程图中实现分支先汇入 “实现后审查门”。
- 分支文件走向表说明审查门必须读取和必须更新的内容。
- `feature-workflow.md` 明确实现后进入审查门。
- `review-workflow.md` 明确审查门结论为 `Pass`、`NeedsFix` 或 `Blocked`。
- 入口文件 `AGENTS.md` 明确非平凡代码实现后必须进入审查门。

## 安全和生产要求

- 权限：不涉及运行时权限。
- 输入校验：不涉及运行时输入。
- 输出安全：不得包含真实密钥。
- 配置：不涉及。
- 日志：更新 Harness 变更日志。
- 回滚：回退本次文档修改并删除新增清单、需求和记录。
- 验证：检查关键文件中是否包含审查门规则。

## 关联设计

- `harness-engineering/workflows/review-workflow.md`
- `harness-engineering/checklists/code-review-gate-checklist.md`
- `docs/harness-engineering-guide.html`

## 关联决策

- `harness-engineering/decisions/ADR-001-root-harness-engineering.md`

## 关联 AI 开发记录

- `harness-engineering/records/2026-06-08-005-code-review-gate.md`

## 状态流转记录

| 日期 | 状态 | 说明 |
| --- | --- | --- |
| 2026-06-08 | Draft | 根据用户反馈创建审查门需求 |
| 2026-06-08 | Implemented | 已补充审查门规则和流程图 |
| 2026-06-08 | Verified | 已检查关键文件和索引记录 |

