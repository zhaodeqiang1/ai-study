# 2026-06-09-003: 企业知识库问答环境确认

## 关联需求

- `docs/requirements/REQ-20260609-002-enterprise-knowledge-base-qa.md`

## 背景

用户补充确认：DeepSeek R1 7B 和 bge-m3 均由 Ollama 部署，PostgreSQL 已启用 pgvector。该信息会影响模型接入方式、Nacos 配置项、向量表设计和后续环境验证步骤。

## 本次改动

- 更新企业知识库问答架构设计文档。
- 更新企业知识库问答需求文档。
- 更新需求索引。
- 更新 AI 开发记录索引。
- 更新 Harness 变更日志。

## 关键决策

- 模型接入统一按 Ollama 设计。
- Nacos 配置使用 `provider: ollama` 和 `HARNESS_OLLAMA_BASE_URL`。
- PostgreSQL 向量库按已启用 pgvector 处理。
- bge-m3 向量维度仍需通过实际 embedding 响应确认后再写入 SQL，避免 pgvector 字段维度错误。

## 修改文件

- `docs/architecture/enterprise-knowledge-base-qa-architecture.md`
- `docs/requirements/REQ-20260609-002-enterprise-knowledge-base-qa.md`
- `docs/requirements/INDEX.md`
- `harness-engineering/records/2026-06-09-003-enterprise-knowledge-base-environment-confirmation.md`
- `harness-engineering/records/INDEX.md`
- `harness-engineering/changes/CHANGELOG.md`

## 验证

- 检查架构文档包含 Ollama、DeepSeek R1 7B、bge-m3 和 PostgreSQL 已启用 pgvector。
- 检查需求文档移除“是否由 Ollama 部署”和“PostgreSQL 是否启用 pgvector”的待确认项。
- 检查需求索引、AI 开发记录索引和变更日志包含本次记录。
- 未执行 Maven/NPM 业务测试或构建，因为本次只修改需求和架构文档，不修改业务代码。

## 审查门结论

- 结论：`Pass`。
- 说明：本次变更只收敛环境确认信息，不涉及业务代码、SQL、权限配置或运行时部署。

## 风险

- 仍需通过实际 Ollama 调用确认模型标签和 bge-m3 embedding 维度。
- 后续 SQL 迁移前必须先固定向量维度，否则 pgvector 表结构可能返工。

## 后续事项

- 运行或确认 `ollama list` 中 DeepSeek R1 7B 和 bge-m3 的实际模型标签。
- 通过一次 bge-m3 embedding 调用确认向量维度。
- 进入 SQL/migration 设计。

