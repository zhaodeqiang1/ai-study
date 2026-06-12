# REQ-20260609-002: 企业知识库问答

## 状态

Reviewed

## 背景

项目首个 AI 开发目标是企业知识库问答。当前已具备 MySQL、Nacos、Redis、PostgreSQL 向量数据库、本地 DeepSeek R1 7B 大模型和 bge-m3 向量模型。DeepSeek R1 7B 和 bge-m3 已确认全部由 Ollama 部署，PostgreSQL 已确认启用 `pgvector`。需要先完成架构设计和环境搭建方案，作为后续实现、审查、SQL 迁移、测试和评测的输入。

## 目标

- 基于 RuoYi Cloud 设计企业知识库问答的首版架构。
- 使用 Spring AI Alibaba 接入由 Ollama 部署的本地大模型和向量模型。
- 使用 MySQL 保存业务元数据、权限、会话和日志。
- 使用已启用 pgvector 的 PostgreSQL 保存文档切片向量。
- 使用 Redis 保存任务进度、短期缓存和限流状态。
- 使用 Nacos 管理 AI、RAG、数据源和任务参数配置。
- 为后续生产化实现预留权限、审计、回滚、测试和评测机制。

## 范围

包含：

- 企业知识库管理。
- 文档上传、解析、切片和向量化。
- PostgreSQL 向量检索。
- Ollama / DeepSeek R1 7B 问答生成。
- Ollama / bge-m3 Embedding。
- RAG Prompt 组装。
- 会话、消息、引用来源和模型调用日志。
- 环境配置架构。
- 后续模块、接口、SQL 和前端页面规划。

## 非目标

- 本阶段不直接实现 Java、Vue 或 SQL 业务代码。
- 本阶段不修改 `ruoyi-auth`、`ruoyi-gateway`、`ruoyi-common` 或根 `pom.xml`。
- 本阶段不接入外部云模型。
- 本阶段不实现复杂工作流、Agent 工具调用或自动化审批。
- 本阶段不把 Redis 作为长期数据存储。

## 业务规则

- 用户只能访问有权限的知识库。
- 问答必须返回引用来源。
- 文档入库必须有状态流转，至少包含待解析、解析中、已完成、失败。
- 文档解析失败必须可查看失败原因，并支持后续重试。
- 模型调用必须记录模型名、耗时、Token、成功状态和失败原因。
- Prompt 模板必须可配置、可版本化。
- 用户问题必须限制长度。
- 文档上传必须限制文件类型、大小和数量。
- 模型输出不能直接触发删库、改权限、发送外部通知等高风险动作。

## 影响范围评估

- 后端：建议新增 `ruoyi-modules/ruoyi-harness`，承载知识库、文档、RAG、模型调用和日志能力；可规划 `ruoyi-api/ruoyi-api-harness` 作为远程 API 契约。
- 前端：建议新增 `ruoyi-ui/src/api/harness` 和 `ruoyi-ui/src/views/harness`，包含知识库、文档、问答、会话和日志页面。
- 数据库：MySQL 需要新增知识库、文档、任务、会话、消息、引用、模型配置和调用日志表；PostgreSQL 已启用 pgvector，后续需要新增向量切片表；后续 SQL 必须包含正向、回滚、验证和不可逆说明。
- 权限和安全：需要新增菜单、按钮权限、知识库访问控制、输入长度限制、上传限制、敏感信息处理和模型输出安全约束。
- 配置和部署：Nacos 需要新增 Ollama base URL、Chat 模型名、Embedding 模型名、RAG 参数、超时、批量大小、向量维度等配置；Ollama 模型服务需要健康检查。
- AI 功能：涉及 Ollama、DeepSeek R1 7B、bge-m3、Prompt、Embedding、RAG 检索、引用来源、Token 统计和 AI 调用审计。
- 测试和验证：后续实现时需要单元测试覆盖切片、Prompt 渲染、召回过滤、权限校验、模型异常；需要 SQL 验证、后端模块测试、前端构建和 AI 问答评测集。
- 发布和回滚：建议按环境配置、SQL、后端服务、前端页面、模型服务健康检查的顺序部署；SQL 必须提供回滚脚本或回滚方案。
- 不改动范围：默认不修改认证服务、网关服务、公共模块、父级构建配置和全局安全配置。

## 验收标准

- 存在企业知识库问答架构设计文档。
- 架构设计明确 MySQL、Redis、Nacos、PostgreSQL/pgvector、Ollama、本地 DeepSeek R1 7B 和 bge-m3 的职责。
- 架构设计明确后端模块、远程 API 模块、前端目录和 SQL 推荐落点。
- 架构设计包含文档入库流程和问答流程。
- 架构设计包含数据表规划、接口规划、权限规划、生产约束和里程碑。
- 需求文档登记到 `docs/requirements/INDEX.md`。
- 本次设计有独立 AI 开发记录。

## 安全和生产要求

- 权限：所有管理接口必须接入 RuoYi 权限体系；知识库需要访问控制。
- 输入校验：限制问题长度、文件类型、文件大小、知识库 ID、分页参数和状态参数。
- 输出安全：回答必须带引用来源；模型输出不得驱动高风险动作。
- 配置：Ollama 地址、模型名、超时、Token、RAG 参数和向量维度必须配置化，不硬编码真实密钥。
- 日志：记录操作日志、会话消息、引用来源、模型调用耗时、Token 和失败原因。
- 回滚：后续 SQL/migration 必须提供正向 SQL、回滚 SQL 或回滚方案、数据影响、部署顺序和验证 SQL。
- 验证：后续实现必须执行单元测试、模块测试、SQL 验证、前端构建和 AI 问答评测。

## 关联设计

- `docs/architecture/enterprise-knowledge-base-qa-architecture.md`

## 关联决策

- `harness-engineering/decisions/ADR-001-root-harness-engineering.md`

## 关联 AI 开发记录

- `harness-engineering/records/2026-06-09-002-enterprise-knowledge-base-qa-architecture.md`
- `harness-engineering/records/2026-06-09-003-enterprise-knowledge-base-environment-confirmation.md`

## 后续流程衔接

- 推荐后续流程：`harness-engineering/workflows/feature-workflow.md`
- 推荐读取技能：
  - `harness-engineering/skills/spring-ai-alibaba.md`
  - `harness-engineering/skills/ruoyi-cloud-backend.md`
  - `harness-engineering/skills/database-mybatis.md`
  - `harness-engineering/skills/ruoyi-vue-frontend.md`
  - `harness-engineering/skills/testing-verification.md`
- 需要先确认的问题：
  - DeepSeek R1 7B 在 Ollama 中的实际模型标签。
  - bge-m3 在 Ollama 中的实际模型标签、Embedding 维度和 API 协议。
  - 首版是否允许新增 `ruoyi-harness` 模块和 `ruoyi-api-harness` 模块。
  - 首版文件上传是否复用 RuoYi 现有文件服务。
- 是否需要评测集：需要。后续 RAG 问答实现后，应建立企业知识库问答评测集，覆盖有答案、无答案、权限不足、召回不足、敏感问题和超长输入。

## 状态流转记录

| 日期 | 状态 | 说明 |
| --- | --- | --- |
| 2026-06-09 | Draft | 根据用户首个 AI 开发目标创建需求 |
| 2026-06-09 | Reviewed | 已完成首版架构设计，等待确认后进入实现 |
| 2026-06-09 | Reviewed | 已确认 DeepSeek R1 7B 和 bge-m3 均由 Ollama 部署，PostgreSQL 已启用 pgvector |
