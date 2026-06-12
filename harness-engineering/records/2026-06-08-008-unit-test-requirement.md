# 2026-06-08-008: 强化代码开发单元测试要求

## 关联需求

- `docs/requirements/REQ-20260608-008-unit-test-requirement.md`

## 背景

用户指出需要确认代码开发是否必须有测试环节，例如单元测试。此前 Harness 已有测试验证技能，但没有把“单元测试优先”沉淀成独立契约和检查清单，也没有在所有开发流程中形成硬约束。

## 本次改动

- 新增 `harness-engineering/contracts/testing-contract.md`。
- 新增 `harness-engineering/checklists/unit-test-checklist.md`。
- 更新 `AGENTS.md`，明确非平凡代码开发必须优先新增或更新单元测试。
- 更新功能开发、Bug 修复、审查门、生产检查清单和 AI 变更契约。
- 更新测试验证技能和代码审查技能。
- 更新 `.agents/skills/testing-verification/SKILL.md`，让 Codex 原生技能入口也能加载测试契约。
- 更新项目地图、渐进加载、技能加载索引和 HTML 说明文档。
- 更新需求索引、AI 开发记录索引和变更日志。

## 关键决策

- 使用独立测试契约承载“必须做到什么”，避免只把测试要求散落在验证说明里。
- 使用单元测试检查清单承载“什么时候必须考虑测试”和“测哪些分支”。
- 当前项目未发现稳定的 `src/test` 目录和测试依赖，因此本次不直接修改 Maven 依赖，避免触碰父级构建配置。
- 若后续代码变更无法新增单元测试，必须记录原因、替代验证、剩余风险和后续补测建议，不能只写“无需测试”。

## 修改文件

- `AGENTS.md`
- `.agents/skills/testing-verification/SKILL.md`
- `docs/harness-engineering-guide.html`
- `docs/requirements/REQ-20260608-008-unit-test-requirement.md`
- `docs/requirements/INDEX.md`
- `harness-engineering/contracts/testing-contract.md`
- `harness-engineering/contracts/README.md`
- `harness-engineering/contracts/ai-change-contract.md`
- `harness-engineering/checklists/unit-test-checklist.md`
- `harness-engineering/checklists/code-review-gate-checklist.md`
- `harness-engineering/checklists/production-readiness.md`
- `harness-engineering/context/project-map.md`
- `harness-engineering/loaders/progressive-loading.md`
- `harness-engineering/loaders/skill-loading-index.md`
- `harness-engineering/skills/testing-verification.md`
- `harness-engineering/skills/code-review.md`
- `harness-engineering/workflows/feature-workflow.md`
- `harness-engineering/workflows/debug-workflow.md`
- `harness-engineering/workflows/review-workflow.md`
- `harness-engineering/records/2026-06-08-008-unit-test-requirement.md`
- `harness-engineering/records/INDEX.md`
- `harness-engineering/changes/CHANGELOG.md`

## 验证

- 检查 `AGENTS.md`、功能开发流程、测试验证技能、测试契约、单元测试检查清单和 HTML 指南中均包含单元测试要求。
- 检查需求索引、AI 开发记录索引和变更日志包含本次需求编号和记录编号。
- 执行 Codex skill validator，确认 `.agents/skills/testing-verification` 仍符合技能结构。
- 未执行 Maven/NPM 业务测试或构建，因为本次只修改 Harness 文档、契约、检查清单和技能入口，不修改业务代码。

## 审查门结论

- 结论：`Pass`。
- 说明：本次变更已补齐需求记录、AI 开发记录、契约、检查清单、流程、索引和 HTML 指南；不涉及 SQL、权限、生产配置或业务运行时代码。

## 风险

- 当前项目尚未建立测试目录和测试依赖，首次为业务代码补充单元测试时需要确认是否允许新增测试依赖。
- 文档已经形成硬约束，但现有业务代码并不会自动获得测试覆盖，需要后续按模块逐步补齐。

## 后续事项

- 后续首次开发业务代码时，优先在目标模块建立 `src/test/java` 并确认 JUnit、Mockito 或 Spring Boot Test 依赖策略。
- 可为 Spring AI Alibaba 的 Prompt 渲染、模型参数组装、工具调用白名单等逻辑优先补充单元测试样例。
