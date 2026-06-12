# REQ-20260612-001: Harness 路由权威文档与 AGENTS 瘦身

## 状态

Verified

## 背景

用户指出当前 Harness 存在几个治理问题：缺少权威 Markdown 明确“四层拆分”；分支文件走向表主要在 HTML 中，AI 实际执行依赖的 `progressive-loading.md` 和 `skill-loading-index.md` 不够权威；“简单修复、非平凡功能、治理缺口、生产风险”的触发阈值分散；`AGENTS.md` 已经比较长，后续不宜继续塞细节，应该只保留总入口和红线。

## 目标

- 新增权威 Markdown，集中定义四层拆分、分支文件走向表和触发阈值表。
- 将 `AGENTS.md` 瘦身为总入口、红线、默认加载顺序和权威文件指针。
- 将项目基础架构与技术栈基线迁移到独立 Markdown。
- 更新渐进加载、技能加载索引、项目地图、反馈循环和反熵增治理。

## 范围

包含：

- `AGENTS.md`
- `harness-engineering/loaders/harness-execution-routing.md`
- `harness-engineering/loaders/progressive-loading.md`
- `harness-engineering/loaders/skill-loading-index.md`
- `harness-engineering/context/project-technology-baseline.md`
- `harness-engineering/context/project-map.md`
- `harness-engineering/governance/feedback-loop.md`
- `harness-engineering/governance/anti-entropy-governance.md`
- `docs/requirements/REQ-20260612-001-harness-routing-and-agents-slimming.md`
- 需求索引、AI 开发记录索引和变更日志。

## 非目标

- 不修改业务代码。
- 不修改运行时配置。
- 不新增 Java、Vue、SQL 或依赖。
- 不删除历史需求和 AI 开发记录。

## 业务规则

- Harness 四层拆分、触发阈值和分支文件走向以 `harness-engineering/loaders/harness-execution-routing.md` 为权威来源。
- `AGENTS.md` 只保留入口、红线、默认加载顺序和权威文件指针。
- 项目技术栈基线写入 `harness-engineering/context/project-technology-baseline.md`，不再堆到 `AGENTS.md`。
- HTML 说明文档可以作为展示材料，但不能替代 Markdown 权威路由。

## 影响范围评估

- 后端：不涉及运行时代码。
- 前端：不涉及运行时代码。
- 数据库：不涉及 SQL。
- 权限和安全：不涉及运行时权限。
- 配置和部署：不涉及部署配置。
- AI 功能：影响后续 AI 执行路由和上下文加载方式。
- 测试和验证：本次验证为文档关键内容检查。
- 发布和回滚：无运行时发布影响；回滚方式为回退本次文档修改。
- 不改动范围：不修改 Java、Vue、SQL、Maven、NPM。

## 验收标准

- 存在 `harness-engineering/loaders/harness-execution-routing.md`。
- 路由文档包含四层拆分。
- 路由文档包含触发阈值表。
- 路由文档包含分支文件走向表。
- `AGENTS.md` 不再保存详细技术栈清单、完整触发表或长流程细节。
- `AGENTS.md` 指向权威 Markdown。
- `progressive-loading.md` 和 `skill-loading-index.md` 指向权威路由文档。
- 项目技术栈基线迁移到 `project-technology-baseline.md`。
- 反馈循环和反熵增治理覆盖路由分散、入口过长的问题。

## 安全和生产要求

- 权限：不涉及运行时权限。
- 输入校验：不涉及运行时输入。
- 输出安全：不写入真实密钥或生产敏感信息。
- 配置：不涉及运行时配置。
- 日志：更新 Harness 变更日志。
- 回滚：回退本次文档修改。
- 验证：检查关键文件包含四层拆分、触发阈值、分支文件走向和 AGENTS 边界。

## 关联设计

- `harness-engineering/loaders/harness-execution-routing.md`
- `harness-engineering/context/project-technology-baseline.md`

## 关联决策

- `harness-engineering/decisions/ADR-001-root-harness-engineering.md`

## 关联 AI 开发记录

- `harness-engineering/records/2026-06-12-001-harness-routing-and-agents-slimming.md`

## 后续流程衔接

- 推荐后续流程：`harness-engineering/governance/feedback-loop.md`
- 推荐读取技能：
  - `harness-engineering/skills/code-review.md`
  - `harness-engineering/skills/testing-verification.md`
- 需要先确认的问题：无。
- 是否需要评测集：不需要，本次为 Harness 路由和入口治理修正。

## 状态流转记录

| 日期 | 状态 | 说明 |
| --- | --- | --- |
| 2026-06-12 | Draft | 根据用户反馈创建路由权威文档和 AGENTS 瘦身需求 |
| 2026-06-12 | Implemented | 已新增路由文档、迁移技术栈基线并瘦身 AGENTS.md |
| 2026-06-12 | Verified | 已执行关键内容检查 |

