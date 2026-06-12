# Harness 执行路由

本文件是 AI 执行任务时的权威 Markdown 路由表。

它定义四层拆分、分支文件走向和触发阈值，避免只依赖 HTML 说明文档或分散规则。

## 四层拆分

| 层级 | 名称 | 作用 | 权威文件 |
| --- | --- | --- | --- |
| 第 1 层 | 入口路由层 | 判断任务类型、触发阈值、需要读取哪些文件 | `AGENTS.md`、`harness-engineering/loaders/harness-execution-routing.md`、`harness-engineering/loaders/progressive-loading.md`、`harness-engineering/loaders/skill-loading-index.md` |
| 第 2 层 | 治理契约层 | 定义需求、变更、审查、测试、SQL、AI 功能必须满足什么条件 | `harness-engineering/contracts/*`、`harness-engineering/constraints/*`、`harness-engineering/checklists/*` |
| 第 3 层 | 任务执行层 | 按任务类型执行需求设计、开发、调试、审查、SQL、前端、AI 功能 | `harness-engineering/workflows/*`、`harness-engineering/skills/*`、`.agents/skills/*/SKILL.md` |
| 第 4 层 | 证据沉淀层 | 记录为什么改、怎么改、验证什么、风险是什么、后续做什么 | `docs/requirements/*`、`docs/architecture/*`、`harness-engineering/records/*`、`harness-engineering/changes/CHANGELOG.md`、`harness-engineering/decisions/*` |

## 触发阈值表

| 任务类型 | 触发条件 | 必须读取 | 必须沉淀 |
| --- | --- | --- | --- |
| 简单修复 | 单文件或少量局部改动；不改变接口、权限、SQL、配置、依赖、状态流转；无生产风险 | `AGENTS.md`、`project-map.md`、相关局部文件 | 视情况更新 `CHANGELOG.md`；无需新增需求和独立记录 |
| 非平凡功能 | 新增功能；新增接口；新增页面；新增表；跨模块改动；涉及 AI、SQL、权限、配置、状态流转或生产行为 | `requirements-design.md`、`feature-workflow.md`、相关技能、相关契约和检查清单 | 需求文件、需求索引、AI 开发记录、记录索引、变更日志；必要时架构文档和 ADR |
| Bug 修复 | 修复已知错误、失败命令、接口异常、页面异常、数据异常 | `debug-workflow.md`、`testing-verification.md`、相关局部文件 | 简单 Bug 更新变更日志；生产、安全、数据、SQL、跨模块 Bug 必须新增 AI 开发记录 |
| 代码审查 | 用户要求 review；实现后审查门；检查生产风险、安全、权限、事务、SQL、测试或 Harness 合规 | `review-workflow.md`、`code-review.md`、`code-review-gate-checklist.md`、相关契约 | 审查结论写入 AI 开发记录；独立审查任务按用户要求输出 |
| 治理缺口 | 用户指出规则缺失、验证缺失、追溯缺失、文档漂移、路由不清、入口过长 | `feedback-loop.md`、`anti-entropy-governance.md`、受影响的 Harness 文件 | 需求文件、AI 开发记录、变更日志；更新对应 Harness 文件 |
| 生产风险 | 涉及权限、安全、配置、外部调用、SQL、数据迁移、回滚、部署顺序、模型输出驱动动作 | `production-constraints.md`、`security-constraints.md`、相关契约和检查清单 | AI 开发记录必须记录风险、验证、回滚或不可逆说明 |
| SQL/migration | 新增或修改表、索引、字段、迁移脚本、Mapper 查询条件 | `database-mybatis.md`、`sql-migration-contract.md`、`sql-migration-checklist.md` | 正向 SQL、回滚 SQL 或方案、数据影响、部署顺序、验证 SQL、AI 开发记录 |
| AI 功能 | 模型调用、Prompt、RAG、Embedding、向量检索、工具调用、Token 统计、AI 审计日志 | `spring-ai-alibaba.md`、`ai-feature-contract.md`、`evaluations/README.md` | 需求、架构或评测集说明、AI 开发记录、验证或不适用原因 |

## 分支文件走向表

| 分支 | 先读 | 再读 | 修改或新增 | 收尾 |
| --- | --- | --- | --- | --- |
| 需求设计 | `requirements-design.md`、`requirement-contract.md`、`impact-scope-checklist.md` | `docs/requirements/README.md`、`REQ-000-template.md` | `docs/requirements/REQ-*.md`、`docs/requirements/INDEX.md` | 如为非平凡 AI 开发，新增 `records/*` 和更新 `CHANGELOG.md` |
| 后端功能 | `feature-workflow.md`、`ruoyi-cloud-backend.md`、`testing-contract.md` | `database-mybatis.md`、`security-constraints.md`、目标模块相邻实现 | Controller、Service、Mapper、Domain、SQL、测试 | 审查门、测试验证、AI 开发记录、变更日志 |
| Spring AI 功能 | `spring-ai-alibaba.md`、`ai-feature-contract.md` | `database-mybatis.md`、`testing-verification.md`、`evaluations/README.md` | AI Service、Prompt、RAG、Vector、Log、评测集 | 审查门、评测说明、AI 开发记录 |
| Vue 前端 | `ruoyi-vue-frontend.md` | 目标页面、API 封装、权限按钮示例 | `ruoyi-ui/src/api/*`、`ruoyi-ui/src/views/*` | 前端构建或无法验证说明、AI 开发记录 |
| SQL 迁移 | `database-mybatis.md`、`sql-migration-contract.md`、`sql-migration-checklist.md` | 目标 Mapper、实体、业务表设计 | `sql/harness/migrations/*` 或指定 SQL | SQL 验证、回滚说明、AI 开发记录 |
| 审查门 | `review-workflow.md`、`code-review.md`、`code-review-gate-checklist.md` | 本次 diff、需求验收标准、相关契约 | 修复审查发现的阻塞问题 | `Pass`、`NeedsFix` 或 `Blocked` 写入 AI 开发记录 |
| 治理反馈 | `feedback-loop.md`、`anti-entropy-governance.md` | 受影响的 loader、workflow、skill、contract、checklist | 对应 Harness 文件、需求记录、AI 开发记录 | 更新索引和 `CHANGELOG.md` |

## AGENTS.md 边界

`AGENTS.md` 只保存：

- 默认入口说明。
- 最高优先级红线。
- 默认加载顺序。
- 权威文件指针。
- 极简执行原则。

以下内容不得继续堆到 `AGENTS.md`：

- 详细技术栈清单。
- 某个需求的架构事实。
- 完整触发阈值表。
- 详细技能说明。
- 详细契约和检查清单。
- 长流程图或文件走向表。

这些内容必须写入 `harness-engineering` 或 `docs` 下的权威 Markdown。

