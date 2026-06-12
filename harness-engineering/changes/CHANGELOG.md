# 变更日志

本文件记录 AI 辅助开发相关变更。

## 2026-06-08

- 初始化根路径 `AGENTS.md`，作为 Codex 默认入口。
- 初始化 `harness-engineering` 目录。
- 新增渐进式加载规则。
- 新增项目模块地图。
- 新增编码边界、Token 预算、安全约束、生产约束。
- 新增 RuoYi、Spring AI Alibaba、Vue、数据库、测试、代码审查技能。
- 新增功能开发、调试、审查、重构工作流。
- 新增任务模板、变更记录模板、ADR 模板。
- 新增 `CLAUDE.md` 兼容入口。
- 新增 `.claude/commands` 命令模板，方便 Claude Code 按 Harness 规则执行任务。

## 2026-06-08 入口调整

- 移除自定义入口文件。
- 统一使用 Codex 默认入口 `AGENTS.md`。
- 更新所有 Harness 文档、提示词和命令模板中的入口引用。

## 2026-06-08 入口和项目地图增强

- 在 `AGENTS.md` 增加绝对禁止事项，明确 Git、删除文件、全仓库扫描、密钥、权限、安全和验证红线。
- 扩展 `harness-engineering/context/project-map.md`，补充根目录文件、后端模块、前端源码、SQL 和 Harness 目录的职责说明。

## 2026-06-08 反熵增治理和反馈循环

- 新增 `docs/requirements` 需求体系，包含需求编号、需求索引、状态流转和验收标准模板。
- 新增 `harness-engineering/records` AI 开发记录体系，要求每次非平凡 AI 开发都有独立记录。
- 新增 `harness-engineering/governance` 反熵增治理、反馈循环和审计清单。
- 强化 SQL/migration 规则，要求正向 SQL、回滚 SQL 或回滚方案、数据影响、部署顺序、验证 SQL、不可逆说明。
- 强化测试验证技能，补充 Maven 和前端构建命令，并要求记录无法验证原因。
- 更新 `AGENTS.md`、工作流、命令模板和项目地图，把需求、记录、反馈循环接入默认流程。

## 2026-06-08 Harness HTML 说明文档

- 新增 `docs/harness-engineering-guide.html`，说明 Harness Engineering 目录和文件职责。
- 在 HTML 文档中加入 Harness 结构图和 AI 开发流程图。
- 新增需求记录 `REQ-20260608-002`。
- 新增 AI 开发记录 `2026-06-08-002`。

## 2026-06-08 追加 AI 开发详细分支流程图

- 在 `docs/harness-engineering-guide.html` 中追加 “AI 开发详细分支流程图”。
- 新增分支文件走向表，明确每个分支必须读取、按需读取和必须更新的文件。
- 新增需求记录 `REQ-20260608-003`。
- 新增 AI 开发记录 `2026-06-08-003`。

## 2026-06-08 补充 Harness 设计原因说明

- 在 `docs/harness-engineering-guide.html` 中新增 “为什么这样设计” 章节。
- 新增问题和设计映射表，说明原始问题、设计方案、解决效果和代价。
- 新增核心设计取舍表，说明入口、需求、记录、技能加载和 SQL 约束的设计原因。
- 新增需求记录 `REQ-20260608-004`。
- 新增 AI 开发记录 `2026-06-08-004`。

## 2026-06-08 补充实现后代码审查门

- 将代码审查从独立旁路分支补充为非平凡代码实现后的主线门禁。
- 在 `docs/harness-engineering-guide.html` 主流程图中增加 “审查门”，并在详细分支图中增加 “实现后审查门”。
- 新增 `harness-engineering/checklists/code-review-gate-checklist.md`。
- 更新 `AGENTS.md`、`feature-workflow.md`、`review-workflow.md`、`production-readiness.md` 和 `feedback-loop.md`。
- 更新实现功能命令模板，要求实现后进入审查门，通过后再验证。
- 新增需求记录 `REQ-20260608-005`。
- 新增 AI 开发记录 `2026-06-08-005`。

## 2026-06-08 增加契约和评测集机制

- 新增 `harness-engineering/contracts`，包含需求、AI 变更、审查门、SQL 迁移和 AI 功能契约。
- 新增 `harness-engineering/evaluations`，包含评测索引、治理质量评测数据集、评分标准和评测案例。
- 新增 `harness-engineering/checklists/evaluation-checklist.md`。
- 更新 `AGENTS.md`、feature workflow、review workflow、progressive loading、skill loading index、project map 和 production checklist。
- 更新 `docs/harness-engineering-guide.html`，说明契约和评测集的作用。
- 新增需求记录 `REQ-20260608-006`。
- 新增 AI 开发记录 `2026-06-08-006`。

## 2026-06-08 调整技能到 Codex 原生发现位置

- 新增 `.agents/skills` repo 级 Codex 原生技能目录。
- 为 `ruoyi-cloud-backend`、`spring-ai-alibaba`、`ruoyi-vue-frontend`、`database-mybatis`、`testing-verification`、`code-review` 创建标准 `SKILL.md`。
- 每个 `SKILL.md` 作为薄封装，指向 `harness-engineering/skills` 中的详细规则。
- 补充 `agents/openai.yaml` UI 元数据。
- 更新 `AGENTS.md`、技能 README、项目地图、技能加载索引和 HTML 说明文档。
- 执行 skill validator，6 个技能均通过。
- 新增需求记录 `REQ-20260608-007`。
- 新增 AI 开发记录 `2026-06-08-007`。

## 2026-06-08 强化代码开发单元测试要求

- 新增 `harness-engineering/contracts/testing-contract.md`，明确非平凡代码开发必须优先新增或更新单元测试。
- 新增 `harness-engineering/checklists/unit-test-checklist.md`，说明何时必须考虑单元测试和推荐覆盖分支。
- 更新 `AGENTS.md`、功能开发流程、Bug 修复流程、审查流程、测试验证技能、代码审查技能和生产检查清单。
- 更新 `.agents/skills/testing-verification/SKILL.md`，让 Codex 原生技能入口加载测试契约和单元测试检查清单。
- 更新 `docs/harness-engineering-guide.html`，补充单元测试治理说明。
- 新增需求记录 `REQ-20260608-008`。
- 新增 AI 开发记录 `2026-06-08-008`。

## 2026-06-09 增加需求设计与影响范围评估技能

- 新增 `.agents/skills/requirements-design` Codex 原生需求设计技能入口。
- 新增 `harness-engineering/skills/requirements-design.md`，明确需求设计、需求编号、固定输出位置和后续流程衔接。
- 新增 `harness-engineering/checklists/impact-scope-checklist.md`。
- 强化需求 README、需求模板和需求契约，要求非平凡需求包含影响范围评估。
- 更新 `AGENTS.md`、渐进加载、技能加载索引、项目地图、技能 README、功能开发流程和 HTML 说明文档。
- 新增需求记录 `REQ-20260609-001`。
- 新增 AI 开发记录 `2026-06-09-001`。

## 2026-06-09 企业知识库问答架构设计

- 新增 `docs/requirements/REQ-20260609-002-enterprise-knowledge-base-qa.md`。
- 新增 `docs/architecture/enterprise-knowledge-base-qa-architecture.md`。
- 新增 `docs/architecture/README.md`，说明架构文档目录职责。
- 明确 MySQL、Nacos、Redis、PostgreSQL 向量库、本地 DeepSeek R1 7B 和 bge-m3 在企业知识库问答中的职责。
- 设计文档入库流程、RAG 问答流程、模块边界、数据存储、API、权限、生产约束和里程碑。
- 更新项目地图，补充 `docs/architecture`。
- 更新需求索引和 AI 开发记录索引。
- 新增 AI 开发记录 `2026-06-09-002`。

## 2026-06-09 企业知识库问答环境确认

- 根据用户确认，更新企业知识库问答架构：DeepSeek R1 7B 和 bge-m3 均由 Ollama 部署。
- 更新 PostgreSQL 向量库前提：已启用 pgvector。
- 更新 Nacos 配置建议，模型 provider 调整为 `ollama`。
- 保留 bge-m3 embedding 维度需通过实际响应确认的风险说明。
- 新增 AI 开发记录 `2026-06-09-003`。

## 2026-06-09 项目基础架构与技术栈基线写入入口

- 根据用户纠正，明确 `AGENTS.md` 只记录项目级基础架构与技术栈基线，不记录某个需求的局部架构变更。
- 在 `AGENTS.md` 新增“项目基础架构与技术栈基线”章节。
- 记录 RuoYi Cloud 3.6.8、JDK 17、Spring Boot 4.0.3、Spring Cloud 2025.1.0、Spring Cloud Alibaba 2025.1.0.0 等基础版本。
- 记录 Nacos、Redis、MySQL、Sentinel、Seata、MyBatis、Druid 等基础中间件和能力。
- 记录 Spring AI Alibaba、Ollama、DeepSeek R1 7B、bge-m3、PostgreSQL/pgvector 等 AI 方向基础设施。
- 更新反馈循环，要求后续项目级技术栈确认必须同步入口。
- 新增需求记录 `REQ-20260609-003`。
- 新增 AI 开发记录 `2026-06-09-004`。

## 2026-06-12 Harness 路由权威文档与 AGENTS 瘦身

- 新增 `harness-engineering/loaders/harness-execution-routing.md`，作为四层拆分、触发阈值和分支文件走向的权威 Markdown。
- 新增 `harness-engineering/context/project-technology-baseline.md`，承载项目基础架构与技术栈基线。
- 瘦身 `AGENTS.md`，只保留总入口、红线、默认加载顺序和权威文件指针。
- 更新 `progressive-loading.md`、`skill-loading-index.md`、项目地图、反馈循环和反熵增治理。
- 将 `REQ-20260609-003` 标记为 `Deprecated`，由 `REQ-20260612-001` 替代。
- 新增需求记录 `REQ-20260612-001`。
- 新增 AI 开发记录 `2026-06-12-001`。
