# REQ-20260609-001: 增加需求设计与影响范围评估技能

## 状态

Verified

## 背景

用户指出当前需要一个专门的需求设计技能。该技能不仅要整理需求，还要评估影响范围，并把需求文档写入固定位置，供后续功能开发、审查、测试和治理流程使用。

## 目标

- 新增 Codex 原生 repo 级需求设计技能。
- 在 Harness 详细技能中定义需求设计流程。
- 强化需求模板和需求契约，要求包含影响范围评估和后续流程衔接。
- 新增影响范围评估检查清单。
- 明确需求文档固定输出到 `docs/requirements`。

## 范围

包含：

- `.agents/skills/requirements-design/SKILL.md`
- `.agents/skills/requirements-design/agents/openai.yaml`
- `harness-engineering/skills/requirements-design.md`
- `harness-engineering/checklists/impact-scope-checklist.md`
- `docs/requirements/REQ-000-template.md`
- `docs/requirements/README.md`
- `harness-engineering/contracts/requirement-contract.md`
- `AGENTS.md`
- `harness-engineering/loaders/progressive-loading.md`
- `harness-engineering/loaders/skill-loading-index.md`
- `harness-engineering/context/project-map.md`
- `harness-engineering/skills/README.md`
- `harness-engineering/workflows/feature-workflow.md`
- `docs/harness-engineering-guide.html`
- 需求索引、AI 开发记录索引和变更日志。

## 非目标

- 不开发业务功能。
- 不修改 Java、Vue、SQL 业务代码。
- 不新增需求管理运行时模块。
- 不改变需求编号格式。

## 业务规则

- 需求设计必须写入 `docs/requirements/REQ-YYYYMMDD-NNN-<english-slug>.md`。
- 需求文档必须登记到 `docs/requirements/INDEX.md`。
- 非平凡需求必须包含影响范围评估。
- 需求设计阶段不得默认进入代码实现，除非用户明确要求继续实现。
- 后续实现必须引用需求编号。

## 影响范围评估

- 后端：不涉及业务后端代码，仅新增 Harness 技能和文档。
- 前端：不涉及运行时前端代码，仅更新 HTML 说明文档。
- 数据库：不涉及 SQL 和数据迁移。
- 权限：不涉及运行时权限。
- 配置：不涉及生产配置。
- 测试：需要执行 Codex skill validator，并检查关键文档索引。
- 发布：仅文档和 Harness 技能变更，无运行时发布影响。
- 回滚：删除新增技能、检查清单和需求记录，并回退相关索引、HTML 和入口说明。

## 验收标准

- `.agents/skills/requirements-design/SKILL.md` 存在且通过 Codex skill validator。
- `harness-engineering/skills/requirements-design.md` 明确需求设计流程和固定输出位置。
- `harness-engineering/checklists/impact-scope-checklist.md` 存在。
- `docs/requirements/REQ-000-template.md` 包含影响范围评估和后续流程衔接。
- `harness-engineering/contracts/requirement-contract.md` 要求影响范围评估。
- `AGENTS.md` 和 HTML 指南能看到需求设计技能入口。

## 安全和生产要求

- 权限：不涉及运行时权限。
- 输入校验：需求设计阶段必须标记待确认问题，不能臆造高风险业务规则。
- 输出安全：需求文档不得写入真实密钥、Token 或生产敏感数据。
- 配置：不涉及运行时配置。
- 日志：更新 Harness 变更日志。
- 回滚：回退新增技能、检查清单和文档索引。
- 验证：执行 skill validator 和关键内容检查。

## 关联设计

- `.agents/skills/requirements-design/SKILL.md`
- `harness-engineering/skills/requirements-design.md`
- `harness-engineering/checklists/impact-scope-checklist.md`

## 关联决策

- `harness-engineering/decisions/ADR-001-root-harness-engineering.md`

## 关联 AI 开发记录

- `harness-engineering/records/2026-06-09-001-requirements-design-skill.md`

## 状态流转记录

| 日期 | 状态 | 说明 |
| --- | --- | --- |
| 2026-06-09 | Draft | 根据用户反馈创建需求设计技能需求 |
| 2026-06-09 | Implemented | 已新增技能、检查清单并接入 Harness 流程 |
| 2026-06-09 | Verified | 已执行 skill validator 和关键内容检查 |

