# REQ-20260608-002: 生成 Harness Engineering HTML 说明文档

## 状态

Verified

## 背景

当前项目已经建立 Harness Engineering 目录、Codex 入口、需求体系、AI 开发记录、反熵增治理和反馈循环机制。用户需要一份 HTML 说明文档，用于集中说明各个文件夹和文件的作用，并提供 Harness 结构图和流程图。

## 目标

- 生成一份可直接打开的 HTML 文档。
- 说明 Harness Engineering 各目录和关键文件的作用。
- 包含 Harness 结构图。
- 包含 AI 开发流程图。
- 不依赖外部网络资源。

## 范围

包含：

- `docs/harness-engineering-guide.html`
- 本需求记录。
- AI 开发记录。
- 需求索引、开发记录索引、变更日志更新。

不包含：

- 修改业务运行代码。
- 修改 Maven、NPM、数据库或部署配置。

## 验收标准

- HTML 文档存在。
- HTML 文档包含目录说明。
- HTML 文档包含文件说明。
- HTML 文档包含结构图。
- HTML 文档包含流程图。
- HTML 文档可脱离外部网络阅读。

## 安全和生产要求

- 权限：不涉及。
- 输入校验：不涉及。
- 输出安全：文档中不得包含真实密钥。
- 配置：不涉及。
- 日志：更新 Harness 变更日志。
- 回滚：删除本次新增文档并回退索引和变更日志即可。
- 验证：检查 HTML 文件存在，并检查关键章节内容。

## 关联设计

- `harness-engineering/context/project-map.md`
- `harness-engineering/governance/anti-entropy-governance.md`
- `harness-engineering/governance/feedback-loop.md`

## 关联决策

- `harness-engineering/decisions/ADR-001-root-harness-engineering.md`

## 关联 AI 开发记录

- `harness-engineering/records/2026-06-08-002-harness-guide-html.md`

## 状态流转记录

| 日期 | 状态 | 说明 |
| --- | --- | --- |
| 2026-06-08 | Draft | 根据用户要求创建说明文档需求 |
| 2026-06-08 | Implemented | 已生成 HTML 文档 |
| 2026-06-08 | Verified | 已检查文件和关键内容 |

