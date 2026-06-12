# 2026-06-09-002: 企业知识库问答架构设计

## 关联需求

- `docs/requirements/REQ-20260609-002-enterprise-knowledge-base-qa.md`

## 背景

用户确认首个开发目标是企业知识库问答，并说明当前环境包含 MySQL、Nacos、Redis、PostgreSQL 向量数据库、本地 DeepSeek R1 7B 大模型和 bge-m3 向量模型。根据 Harness 要求，本次先进行需求设计、影响范围评估和架构设计，不直接实现业务代码。

## 本次改动

- 新增企业知识库问答需求文档。
- 新增企业知识库问答架构设计文档。
- 更新需求索引。
- 更新 AI 开发记录索引。
- 更新 Harness 变更日志。

## 关键决策

- 首版以 `ruoyi-modules/ruoyi-harness` 作为推荐业务模块，避免修改认证、网关、公共模块和父级构建配置。
- MySQL 保存业务元数据、权限、状态、会话和模型调用日志。
- PostgreSQL + pgvector 保存文档切片向量。
- Redis 只保存任务进度、短期缓存和限流状态，不保存长期追溯数据。
- DeepSeek R1 7B 和 bge-m3 建议通过 OpenAI-compatible API 暴露，再由 Spring AI Alibaba 统一适配。
- 问答必须返回引用来源，并记录 Token、耗时、模型名和失败原因。

## 修改文件

- `docs/architecture/enterprise-knowledge-base-qa-architecture.md`
- `docs/architecture/README.md`
- `docs/requirements/REQ-20260609-002-enterprise-knowledge-base-qa.md`
- `docs/requirements/INDEX.md`
- `harness-engineering/context/project-map.md`
- `harness-engineering/records/2026-06-09-002-enterprise-knowledge-base-qa-architecture.md`
- `harness-engineering/records/INDEX.md`
- `harness-engineering/changes/CHANGELOG.md`

## 验证

- 检查需求索引包含 `REQ-20260609-002`。
- 检查 AI 开发记录索引包含 `2026-06-09-002`。
- 检查架构文档包含 MySQL、Nacos、Redis、PostgreSQL、DeepSeek R1 7B、bge-m3 和 Spring AI Alibaba。
- 检查项目地图包含 `docs/architecture` 的目录职责。
- 检查需求文档包含影响范围评估和后续流程衔接。
- 未执行 Maven/NPM 业务测试或构建，因为本次只新增架构和需求文档，不修改业务代码。

## 审查门结论

- 结论：`Pass`。
- 说明：本次变更是需求和架构设计，不涉及业务代码、SQL、权限配置或运行时部署；已包含影响范围、风险、验证要求和后续流程衔接。

## 风险

- 本地模型服务暴露协议、bge-m3 向量维度和 PostgreSQL pgvector 状态尚需实际确认。
- 后续实现可能需要新增 Maven 模块和依赖，届时必须单独审查父级构建配置修改风险。
- RAG 回答质量需要评测集验证，不能只用人工试问判断。

## 后续事项

- 确认本地模型服务 API 协议。
- 确认 PostgreSQL pgvector 可用性。
- 进入 SQL/migration 设计，先定义 MySQL 元数据表和 PostgreSQL 向量表。
- 进入后端模块骨架设计和最小闭环实现。
