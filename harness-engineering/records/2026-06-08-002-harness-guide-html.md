# 2026-06-08-002: Harness Engineering HTML 说明文档

## 关联需求

- `docs/requirements/REQ-20260608-002-harness-guide-html.md`

## 背景

用户要求针对当前项目的 Harness Engineering 生成一份 HTML 说明文档，说明各个文件夹和文件的作用，并包含结构图和流程图。

## 本次改动

- 新增 `docs/harness-engineering-guide.html`。
- 新增需求记录 `REQ-20260608-002`。
- 新增 AI 开发记录。
- 更新需求索引、AI 开发记录索引和总变更日志。

## 关键决策

- HTML 文档使用内联 CSS 和内联 SVG 图，不依赖外部网络资源。
- 文档放在 `docs` 根目录下，作为项目级说明文档。
- 结构图展示入口、上下文、约束、技能、流程、治理、记录和需求体系之间的关系。
- 流程图展示从用户需求到反馈循环和反熵增审计的闭环。

## 修改文件

- `docs/harness-engineering-guide.html`
- `docs/requirements/REQ-20260608-002-harness-guide-html.md`
- `docs/requirements/INDEX.md`
- `harness-engineering/records/2026-06-08-002-harness-guide-html.md`
- `harness-engineering/records/INDEX.md`
- `harness-engineering/changes/CHANGELOG.md`

## 验证

- 执行文件存在性检查。
- 检查 HTML 中包含结构图、流程图、文件说明和目录说明关键词。

## 风险

- 本次只新增和修改文档，不影响运行时代码。
- 后续 Harness 文件新增或删除时，需要同步更新 HTML 文档。

## 后续事项

- 如果 Harness 结构继续演进，建议把本 HTML 作为说明文档入口持续维护。

