# 契约说明

契约用于定义 AI 开发产物必须满足的结构、边界和交付条件。

如果说 `constraints` 是“不能做什么”，那么 `contracts` 是“做到什么才算合格”。

## 契约类型

- `requirement-contract.md`：需求记录契约。
- `ai-change-contract.md`：AI 开发变更契约。
- `review-gate-contract.md`：代码审查门契约。
- `testing-contract.md`：非平凡代码开发的单元测试、回归测试和无法补测说明契约。
- `sql-migration-contract.md`：SQL 迁移契约。
- `ai-feature-contract.md`：Spring AI / RAG / 模型调用类功能契约。

## 使用规则

- 非平凡功能必须满足需求契约和 AI 变更契约。
- 非平凡代码实现必须满足审查门契约。
- 非平凡代码开发必须满足测试契约；无法补单元测试时必须记录原因、替代验证、剩余风险和后续补测建议。
- SQL/migration 必须满足 SQL 迁移契约。
- Spring AI Alibaba 相关功能必须满足 AI 功能契约。

契约检查结果应写入对应 AI 开发记录。
