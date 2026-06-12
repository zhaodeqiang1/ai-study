# REQ-20260608-004: 补充 Harness Engineering 设计原因说明

## 状态

Verified

## 背景

HTML 说明文档已经说明了 Harness Engineering 的目录、文件、结构图和流程图，但缺少“为什么这样设计、解决了什么问题、设计代价是什么”的解释。用户要求补充设计原因说明。

## 目标

- 在 HTML 文档中说明 Harness Engineering 的设计动机。
- 映射原始问题、设计方案、解决效果和代价。
- 说明核心设计取舍，例如为什么使用 `AGENTS.md`、为什么需求放在 `docs/requirements`、为什么记录和变更日志分离。

## 范围

包含：

- 更新 `docs/harness-engineering-guide.html`。
- 新增本需求记录。
- 新增 AI 开发记录。
- 更新需求索引、AI 开发记录索引和变更日志。

不包含：

- 修改业务运行代码。
- 修改 Harness 目录结构。

## 验收标准

- HTML 中存在 “为什么这样设计” 章节。
- 章节包含问题和设计映射表。
- 章节包含核心设计取舍表。
- 索引和变更日志已更新。

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
- `AGENTS.md`
- `harness-engineering/governance/anti-entropy-governance.md`
- `harness-engineering/governance/feedback-loop.md`

## 关联决策

- `harness-engineering/decisions/ADR-001-root-harness-engineering.md`

## 关联 AI 开发记录

- `harness-engineering/records/2026-06-08-004-harness-design-rationale.md`

## 状态流转记录

| 日期 | 状态 | 说明 |
| --- | --- | --- |
| 2026-06-08 | Draft | 根据用户要求创建设计原因说明需求 |
| 2026-06-08 | Implemented | 已在 HTML 中补充设计原因和问题映射 |
| 2026-06-08 | Verified | 已检查 HTML 关键内容和索引记录 |

