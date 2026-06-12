# 2026-06-08-004: 补充 Harness Engineering 设计原因说明

## 关联需求

- `docs/requirements/REQ-20260608-004-harness-design-rationale.md`

## 背景

用户指出 HTML 说明文档还需要说明为什么这样设计，以及解决了什么问题。

## 本次改动

- 在 `docs/harness-engineering-guide.html` 中新增 “为什么这样设计” 章节。
- 新增问题和设计映射表。
- 新增核心设计取舍表。
- 顺延后续章节编号。
- 新增需求记录和 AI 开发记录。
- 更新需求索引、记录索引和变更日志。

## 关键决策

- 使用“原始问题、设计方案、解决效果、代价”的表格表达设计价值。
- 单独补充“核心设计取舍”，说明为什么选择 `AGENTS.md`、需求目录、独立记录、按技能加载和 SQL 硬约束。

## 修改文件

- `docs/harness-engineering-guide.html`
- `docs/requirements/REQ-20260608-004-harness-design-rationale.md`
- `docs/requirements/INDEX.md`
- `harness-engineering/records/2026-06-08-004-harness-design-rationale.md`
- `harness-engineering/records/INDEX.md`
- `harness-engineering/changes/CHANGELOG.md`

## 验证

- 检查 HTML 是否包含 “为什么这样设计”。
- 检查 HTML 是否包含 “问题和设计映射”。
- 检查 HTML 是否包含 “核心设计取舍”。
- 检查索引是否包含 `REQ-20260608-004` 和 `2026-06-08-004`。

## 风险

- 本次只修改文档，不影响运行时代码。
- 后续 Harness 设计发生变化时，需要同步更新本说明章节。

## 后续事项

- 后续新增机制时，同步补充它解决的问题和设计代价。

