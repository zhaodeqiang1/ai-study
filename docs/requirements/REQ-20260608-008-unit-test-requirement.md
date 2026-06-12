# REQ-20260608-008: 强化代码开发单元测试要求

## 状态

Verified

## 背景

用户询问“开发代码必须有测试环节比如单元测试有说明么”。当前 Harness 已有测试验证技能和审查门，但对“代码开发必须优先考虑单元测试”的约束还不够硬，容易出现只执行编译或构建、不沉淀单元测试和回归测试策略的问题。

## 目标

- 明确非平凡代码开发必须优先新增或更新单元测试。
- 明确 Bug 修复必须优先新增回归测试。
- 明确无法补充单元测试时必须说明原因、替代验证、剩余风险和后续补测建议。
- 将单元测试要求接入需求、实现、审查门、AI 开发记录和 HTML 指南。

## 范围

包含：

- `AGENTS.md`
- `harness-engineering/contracts/testing-contract.md`
- `harness-engineering/contracts/README.md`
- `harness-engineering/checklists/unit-test-checklist.md`
- `harness-engineering/checklists/code-review-gate-checklist.md`
- `harness-engineering/checklists/production-readiness.md`
- `harness-engineering/workflows/feature-workflow.md`
- `harness-engineering/workflows/debug-workflow.md`
- `harness-engineering/workflows/review-workflow.md`
- `harness-engineering/skills/testing-verification.md`
- `harness-engineering/skills/code-review.md`
- `.agents/skills/testing-verification/SKILL.md`
- `harness-engineering/loaders/progressive-loading.md`
- `harness-engineering/loaders/skill-loading-index.md`
- `harness-engineering/context/project-map.md`
- `docs/harness-engineering-guide.html`
- 需求索引、AI 开发记录索引和变更日志。

不包含：

- 给业务模块直接新增测试依赖。
- 给现有业务代码补充测试用例。
- 修改 Maven 父级构建配置。

## 验收标准

- 存在独立测试契约文件。
- 存在单元测试检查清单。
- `AGENTS.md` 明确非平凡代码开发必须优先新增或更新单元测试。
- 功能开发、Bug 修复和审查流程都能走到测试要求。
- AI 开发记录契约要求记录单元测试结果或无法补测说明。
- HTML 指南说明单元测试治理规则。

## 安全和生产要求

- 权限：不涉及运行时权限变更。
- 输入校验：测试要求应覆盖参数为空、非法输入和权限不足等路径。
- 输出安全：不得在测试数据中写入真实密钥或生产敏感数据。
- 配置：当前不新增测试依赖，后续首次落地单元测试前需确认测试框架和依赖策略。
- 日志：更新 Harness 变更日志。
- 回滚：删除测试契约和检查清单，并回退相关文档修改。
- 验证：检查关键文件是否包含单元测试要求；如涉及技能文件，执行 skill validator。

## 关联设计

- `harness-engineering/contracts/testing-contract.md`
- `harness-engineering/checklists/unit-test-checklist.md`
- `harness-engineering/skills/testing-verification.md`
- `.agents/skills/testing-verification/SKILL.md`

## 关联决策

- `harness-engineering/decisions/ADR-001-root-harness-engineering.md`

## 关联 AI 开发记录

- `harness-engineering/records/2026-06-08-008-unit-test-requirement.md`

## 状态流转记录

| 日期 | 状态 | 说明 |
| --- | --- | --- |
| 2026-06-08 | Draft | 根据用户反馈创建单元测试强约束需求 |
| 2026-06-08 | Implemented | 已新增测试契约、单元测试检查清单并接入工作流 |
| 2026-06-08 | Verified | 已执行关键内容检查和 skill validator |

