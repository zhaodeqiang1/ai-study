# 2026-06-09-004: 项目基础架构与技术栈基线写入入口

## 关联需求

- `docs/requirements/REQ-20260609-003-project-technology-baseline.md`

## 背景

用户纠正入口记录粒度：主入口应记录整体项目架构和技术栈，例如项目基础描述、JDK 版本等；不应记录某个需求导致的局部架构变更。该反馈属于 Harness 入口治理规则修正。

## 本次改动

- 在 `AGENTS.md` 新增“项目基础架构与技术栈基线”章节。
- 记录 RuoYi Cloud、JDK、Spring Boot、Spring Cloud、Spring Cloud Alibaba、Nacos、Redis、MySQL、Sentinel、Seata、MyBatis、Druid 等项目级基础技术。
- 记录 AI 方向基础设施：Spring AI Alibaba、Ollama、DeepSeek R1 7B、bge-m3、PostgreSQL/pgvector。
- 更新反馈循环，要求后续项目级技术栈确认同步入口。
- 新增需求记录、AI 开发记录，并更新索引和变更日志。

## 关键决策

- `AGENTS.md` 只记录项目级长期稳定基线，不记录某个需求的局部架构细节。
- 需求级架构变更继续记录在对应需求文档和架构文档中。
- 升级版本、替换基础中间件或引入重型依赖前，必须先检查入口基线并形成需求。

## 修改文件

- `AGENTS.md`
- `harness-engineering/governance/feedback-loop.md`
- `docs/requirements/REQ-20260609-003-project-technology-baseline.md`
- `docs/requirements/INDEX.md`
- `harness-engineering/records/2026-06-09-004-project-technology-baseline.md`
- `harness-engineering/records/INDEX.md`
- `harness-engineering/changes/CHANGELOG.md`

## 验证

- 检查 `AGENTS.md` 包含“项目基础架构与技术栈基线”。
- 检查 `AGENTS.md` 包含 JDK 17、RuoYi Cloud 3.6.8、Spring Boot 4.0.3、Spring Cloud 2025.1.0、Spring Cloud Alibaba 2025.1.0.0。
- 检查 `AGENTS.md` 包含 Nacos、Redis、MySQL、Sentinel、Seata、MyBatis、Druid。
- 检查 `AGENTS.md` 包含 Spring AI Alibaba、Ollama、DeepSeek R1 7B、bge-m3、PostgreSQL 和 pgvector。
- 检查反馈循环包含项目技术栈基线缺失处理规则。
- 未执行 Maven/NPM 业务测试或构建，因为本次只修改 Harness 文档，不修改业务代码。

## 审查门结论

- 结论：`Pass`。
- 说明：本次变更只补充 Harness 入口项目技术栈基线和反馈循环规则，不涉及运行时业务代码、SQL、权限或生产配置。

## 风险

- `AGENTS.md` 不应扩展成完整架构设计文档，只保留项目级、长期稳定、会影响依赖和版本选择的事实。
- 如果项目实际版本升级，必须同步更新 `pom.xml`、架构文档、需求记录和 `AGENTS.md`，避免入口基线过期。

## 后续事项

- 后续进入 SQL 或代码实现前，先检查 `AGENTS.md` 的项目基础架构与技术栈基线。
- 需求级架构细节继续写入对应 `docs/requirements` 和 `docs/architecture`。

