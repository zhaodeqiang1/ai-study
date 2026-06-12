# 渐进式加载

渐进式加载的目标是：让 AI 每次只读取完成任务所需的最小上下文。

## 第 0 层：入口

必须读取：

- `AGENTS.md`
- `harness-engineering/loaders/harness-execution-routing.md`

## 第 1 层：通用约束

默认读取：

- `harness-engineering/context/project-map.md`
- `harness-engineering/context/project-technology-baseline.md`
- `harness-engineering/constraints/coding-boundaries.md`
- `harness-engineering/constraints/token-budget.md`

## 第 2 层：任务类型

先按 `harness-engineering/loaders/harness-execution-routing.md` 的触发阈值表判断任务类型，再按任务读取一个工作流：

- 需求设计：`harness-engineering/skills/requirements-design.md`
- 新功能：`harness-engineering/workflows/feature-workflow.md`
- Bug 修复：`harness-engineering/workflows/debug-workflow.md`
- 代码审查：`harness-engineering/workflows/review-workflow.md`
- 重构：`harness-engineering/workflows/refactor-workflow.md`
- 用户反馈或治理缺口：`harness-engineering/governance/feedback-loop.md`

## 第 3 层：技术技能

只读取相关技能：

- 需求设计：`harness-engineering/skills/requirements-design.md`
- RuoYi 后端：`harness-engineering/skills/ruoyi-cloud-backend.md`
- Spring AI Alibaba：`harness-engineering/skills/spring-ai-alibaba.md`
- Vue 前端：`harness-engineering/skills/ruoyi-vue-frontend.md`
- 数据库：`harness-engineering/skills/database-mybatis.md`
- 测试验证：`harness-engineering/skills/testing-verification.md`

## 第 3.5 层：治理上下文

只在任务涉及需求、记录、反馈、审计或生产治理时读取：

- `docs/requirements/README.md`
- `harness-engineering/records/README.md`
- `harness-engineering/governance/anti-entropy-governance.md`
- `harness-engineering/governance/feedback-loop.md`
- `harness-engineering/governance/entropy-audit-checklist.md`
- `harness-engineering/contracts/README.md`
- `harness-engineering/evaluations/README.md`

如果任务涉及需求设计或需求补充，还必须按需读取：

- `harness-engineering/skills/requirements-design.md`
- `harness-engineering/contracts/requirement-contract.md`
- `harness-engineering/checklists/impact-scope-checklist.md`

如果任务涉及非平凡代码开发，还必须按需读取：

- `harness-engineering/contracts/testing-contract.md`
- `harness-engineering/checklists/unit-test-checklist.md`

## 第 4 层：代码局部上下文

只读取和任务直接相关的代码：

- 用户明确指定的文件。
- 目标模块下的相邻同类实现。
- 目标模块的 `pom.xml` 或前端配置文件。
- 目标功能对应的 SQL、Mapper、Controller、Service、Vue 页面。

## 禁止行为

- 默认扫描整个仓库。
- 默认读取所有 `pom.xml`。
- 默认读取所有 SQL 文件。
- 为了理解风格而打开大量无关文件。
- 在没有计划的情况下直接修改全局配置。
- 绕过 `harness-engineering/loaders/harness-execution-routing.md` 自行判断触发阈值。

## 何时停止继续读取

当 AI 能回答以下问题时，应停止读取更多上下文：

- 这次改动归属哪个模块？
- 是否已有需求文档，需求文档是否在 `docs/requirements`？
- 影响范围是否评估完整？
- 需要编辑哪些文件？
- 应该参考哪个已有实现？
- 需要哪些权限、安全、配置和日志？
- 如何验证？
- 是否需要新增或更新单元测试？
- 是否需要需求编号和独立 AI 开发记录？
- 适用哪些契约？
- 是否需要评测集？
