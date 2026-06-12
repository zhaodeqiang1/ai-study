# REQ-20260608-006: 增加契约和评测集机制

## 状态

Verified

## 背景

用户询问当前 Harness Engineering 是否有评测集和契约，以及是否需要。当前 Harness 已有约束、需求、记录、审查门和反馈循环，但缺少明确的“合格标准”和“评测案例”。这会导致规则虽然存在，但缺少可判定的交付契约和持续评测机制。

## 目标

- 增加契约目录，定义需求、AI 变更、审查门、SQL 迁移、AI 功能的合格标准。
- 增加评测集目录，定义评测索引、数据集、用例和评分标准。
- 将契约和评测接入 `AGENTS.md`、feature workflow、review workflow、progressive loading 和 HTML 说明文档。

## 范围

包含：

- `harness-engineering/contracts`
- `harness-engineering/evaluations`
- `harness-engineering/checklists/evaluation-checklist.md`
- 入口、workflow、loader、project map、HTML 文档更新。
- 需求索引、AI 开发记录索引和变更日志更新。

不包含：

- 实现真实 AI 业务评测运行器。
- 执行模型评测。
- 修改业务运行代码。

## 验收标准

- 存在契约目录和契约文件。
- 存在评测目录、评测索引、数据集、用例和评分标准。
- `AGENTS.md` 明确要求非平凡功能声明适用契约。
- `feature-workflow.md` 明确契约和评测步骤。
- HTML 文档说明契约和评测集的作用。

## 安全和生产要求

- 权限：不涉及运行时权限。
- 输入校验：不涉及运行时输入。
- 输出安全：不得包含真实密钥。
- 配置：不涉及。
- 日志：更新 Harness 变更日志。
- 回滚：删除新增契约和评测目录，并回退相关文档修改。
- 验证：检查关键文件和关键词。

## 关联设计

- `harness-engineering/contracts/README.md`
- `harness-engineering/evaluations/README.md`
- `docs/harness-engineering-guide.html`

## 关联决策

- `harness-engineering/decisions/ADR-001-root-harness-engineering.md`

## 关联 AI 开发记录

- `harness-engineering/records/2026-06-08-006-contracts-evaluations.md`

## 状态流转记录

| 日期 | 状态 | 说明 |
| --- | --- | --- |
| 2026-06-08 | Draft | 根据用户问题创建契约和评测集需求 |
| 2026-06-08 | Implemented | 已新增契约、评测集和相关流程接入 |
| 2026-06-08 | Verified | 已检查关键文件和关键词 |

