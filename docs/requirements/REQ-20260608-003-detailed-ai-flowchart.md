# REQ-20260608-003: 追加 AI 开发详细分支流程图

## 状态

Verified

## 背景

现有 HTML 说明文档已经包含一张 AI 开发流程图，但粒度偏概览。用户要求追加一张更详细的流程图，明确每个分支应该走哪个文件、读取哪些 Harness 规则、加载哪些技能、最后更新哪些记录。

## 目标

- 在 `docs/harness-engineering-guide.html` 中追加一张 AI 开发详细分支流程图。
- 明确公共入口、渐进加载、任务分类和各分支文件走向。
- 用表格补充说明每个分支必须读取、按需读取和必须更新的文件。

## 范围

包含：

- 更新 HTML 说明文档。
- 新增本需求记录。
- 新增 AI 开发记录。
- 更新需求索引、AI 开发记录索引和变更日志。

不包含：

- 修改业务运行代码。
- 修改 Harness 约束规则本身。

## 验收标准

- HTML 中存在 “AI 开发详细分支流程图”。
- 详细流程图说明公共入口、默认加载、任务分类和主要分支。
- 文档中存在分支文件走向表。
- 分支文件走向表包含必须读取、按需读取、必须更新。
- 需求索引和 AI 开发记录索引已更新。

## 安全和生产要求

- 权限：不涉及。
- 输入校验：不涉及。
- 输出安全：不得包含真实密钥。
- 配置：不涉及。
- 日志：更新 Harness 变更日志。
- 回滚：回退 HTML 修改并删除本次新增需求和记录。
- 验证：检查 HTML 关键内容和索引记录。

## 关联设计

- `docs/harness-engineering-guide.html`
- `harness-engineering/loaders/progressive-loading.md`
- `harness-engineering/loaders/skill-loading-index.md`

## 关联决策

- `harness-engineering/decisions/ADR-001-root-harness-engineering.md`

## 关联 AI 开发记录

- `harness-engineering/records/2026-06-08-003-detailed-ai-flowchart.md`

## 状态流转记录

| 日期 | 状态 | 说明 |
| --- | --- | --- |
| 2026-06-08 | Draft | 根据用户要求创建详细分支流程图需求 |
| 2026-06-08 | Implemented | 已追加详细分支流程图和分支文件走向表 |
| 2026-06-08 | Verified | 已检查 HTML 关键内容和索引记录 |

