# 2026-06-08-003: 追加 AI 开发详细分支流程图

## 关联需求

- `docs/requirements/REQ-20260608-003-detailed-ai-flowchart.md`

## 背景

用户在打开 HTML 说明文档后，要求在 AI 开发流程图后追加一张更详细的流程图，详细到每个分支走哪个文件。

## 本次改动

- 在 `docs/harness-engineering-guide.html` 中新增 “AI 开发详细分支流程图”。
- 新增分支文件走向表，说明每个分支必须读取、按需读取和必须更新的文件。
- 顺延后续章节编号。
- 新增需求记录和 AI 开发记录。
- 更新需求索引、记录索引和变更日志。

## 关键决策

- 详细图采用内联 SVG，继续保持 HTML 离线可读。
- 图中展示主流程和核心分支，表格承载更完整的文件路径细节，避免 SVG 文字过密。
- 分支覆盖公共入口、新功能、Bug 修复、代码审查、后端、前端、Spring AI、SQL、反馈治理。

## 修改文件

- `docs/harness-engineering-guide.html`
- `docs/requirements/REQ-20260608-003-detailed-ai-flowchart.md`
- `docs/requirements/INDEX.md`
- `harness-engineering/records/2026-06-08-003-detailed-ai-flowchart.md`
- `harness-engineering/records/INDEX.md`
- `harness-engineering/changes/CHANGELOG.md`

## 验证

- 检查 HTML 是否包含 “AI 开发详细分支流程图”。
- 检查 HTML 是否包含 “分支文件走向表”。
- 检查需求索引和 AI 开发记录索引是否包含本次编号。

## 风险

- 本次只修改文档，不影响运行时代码。
- 如果后续 Harness 分支策略变化，需要同步更新这张详细流程图和分支表。

## 后续事项

- 后续新增任务分支时，同步更新详细分支流程图。

