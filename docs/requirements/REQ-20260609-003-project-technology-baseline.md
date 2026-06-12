# REQ-20260609-003: 项目基础架构与技术栈基线写入入口

## 状态

Deprecated

## 背景

用户纠正：主入口 `AGENTS.md` 应记录整体项目使用了哪些架构和技术，例如项目基础描述、JDK 版本等；不应记录某个需求导致的局部架构变更。后续进一步明确：`AGENTS.md` 仍不宜继续塞细节，应只保留总入口和红线。因此本需求已被 `REQ-20260612-001` 替代，项目技术栈基线迁移到 `harness-engineering/context/project-technology-baseline.md`。

## 目标

- 在 `AGENTS.md` 中新增项目基础架构与技术栈基线。
- 记录项目级长期稳定事实，例如 RuoYi Cloud、JDK、Spring Boot、Spring Cloud、Spring Cloud Alibaba、Nacos、Redis、MySQL 等。
- 记录 AI 方向的项目级基础设施，如 Spring AI Alibaba、Ollama、本地模型和 pgvector。
- 明确禁止为了局部需求擅自升级版本或引入新的重型依赖。
- 更新反馈循环，确保后续项目级技术栈确认会同步到入口。

## 范围

包含：

- `AGENTS.md`
- `harness-engineering/governance/feedback-loop.md`
- `docs/requirements/REQ-20260609-003-project-technology-baseline.md`
- `docs/requirements/INDEX.md`
- `harness-engineering/records/2026-06-09-004-project-technology-baseline.md`
- `harness-engineering/records/INDEX.md`
- `harness-engineering/changes/CHANGELOG.md`

## 非目标

- 不记录某个需求的局部架构变更细节。
- 不修改业务代码。
- 不新增依赖。
- 不修改 Maven、NPM、SQL 或运行时配置。

## 业务规则

- `AGENTS.md` 只记录项目级长期稳定的基础架构、技术栈和版本边界。
- 需求级架构变更记录在对应需求文档和架构文档中。
- 变更项目技术栈基线前必须形成需求编号，并说明原因、影响范围、替代方案、回滚方案和验证方式。
- 新增重型依赖、升级框架版本、替换基础中间件或更换 AI 框架方向前，必须检查 `AGENTS.md`。

## 影响范围评估

- 后端：不涉及运行时代码；后续后端实现会受技术栈基线约束。
- 前端：不涉及运行时代码；后续前端实现会受 Vue/Element UI 基线约束。
- 数据库：不涉及 SQL；后续数据库设计需遵守 MySQL、PostgreSQL/pgvector 等已确认基线。
- 权限和安全：不涉及运行时权限；提升依赖和版本变更审查要求。
- 配置和部署：明确项目级基础中间件和 AI 基础设施。
- AI 功能：明确 Spring AI Alibaba、Ollama、DeepSeek R1 7B、bge-m3 和 pgvector 作为当前 AI 方向基线。
- 测试和验证：本次只做文档关键内容检查。
- 发布和回滚：无运行时发布影响；回滚方式为回退本次文档修改。
- 不改动范围：不修改 Java、Vue、SQL、Maven、NPM。

## 验收标准

- `AGENTS.md` 包含“项目基础架构与技术栈基线”章节。
- `AGENTS.md` 记录 JDK 17、RuoYi Cloud 3.6.8、Spring Boot 4.0.3、Spring Cloud 2025.1.0、Spring Cloud Alibaba 2025.1.0.0。
- `AGENTS.md` 记录 Nacos、Redis、MySQL、Sentinel、Seata、MyBatis、Druid 等基础中间件和能力。
- `AGENTS.md` 记录 Spring AI Alibaba、Ollama、DeepSeek R1 7B、bge-m3、PostgreSQL/pgvector 等 AI 方向基础设施。
- 反馈循环文档包含项目技术栈基线缺失的处理规则。
- 需求索引、AI 开发记录索引和变更日志均记录本次治理变更。

## 安全和生产要求

- 权限：不涉及运行时权限。
- 输入校验：不涉及运行时输入。
- 输出安全：不写入真实密钥或生产敏感信息。
- 配置：只记录技术栈和配置方向，不写真实环境地址。
- 日志：更新 Harness 变更日志。
- 回滚：回退本次文档和索引修改。
- 验证：检查关键文件包含项目级技术栈基线规则。

## 关联设计

- `docs/architecture/enterprise-knowledge-base-qa-architecture.md`

## 关联决策

- `harness-engineering/decisions/ADR-001-root-harness-engineering.md`

## 关联 AI 开发记录

- `harness-engineering/records/2026-06-09-004-project-technology-baseline.md`

## 后续流程衔接

- 推荐后续流程：`harness-engineering/governance/feedback-loop.md`
- 推荐读取技能：
  - `harness-engineering/skills/requirements-design.md`
  - `harness-engineering/skills/code-review.md`
- 需要先确认的问题：无。
- 是否需要评测集：不需要，本次为治理入口规则补强。

## 状态流转记录

| 日期 | 状态 | 说明 |
| --- | --- | --- |
| 2026-06-09 | Draft | 根据用户纠正创建项目技术栈基线需求 |
| 2026-06-09 | Implemented | 已更新 AGENTS.md 和反馈循环规则 |
| 2026-06-09 | Verified | 已执行关键内容检查 |
| 2026-06-12 | Deprecated | 被 REQ-20260612-001 替代，AGENTS.md 瘦身，技术栈基线迁移到独立 Markdown |
