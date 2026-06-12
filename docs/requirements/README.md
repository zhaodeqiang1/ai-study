# 需求体系说明

本目录记录项目级需求。它用于回答“为什么要改”，不是记录“AI 改了什么”。

每个非平凡功能、架构约束、生产治理要求，都应有独立需求文件，并在 `INDEX.md` 中登记。

需求设计必须使用 `requirements-design` 技能，需求文件固定写入本目录：

```text
docs/requirements/REQ-YYYYMMDD-NNN-<english-slug>.md
```

文件名使用英文，正文使用中文。

## 需求编号

格式：

```text
REQ-YYYYMMDD-NNN
```

示例：

```text
REQ-20260608-001
```

## 状态流转

允许状态：

- `Draft`：草稿，需求还在整理。
- `Reviewed`：已评审，目标和边界清楚。
- `Approved`：已批准，可以进入实现。
- `InProgress`：实现中。
- `Implemented`：已实现，等待验证。
- `Verified`：已验证，满足验收标准。
- `Released`：已发布或已合入主流程。
- `Rejected`：不做。
- `Deprecated`：需求已废弃或被替代。

## 需求文件必须包含

- 需求编号。
- 背景。
- 目标。
- 范围。
- 非目标。
- 影响范围评估。
- 验收标准。
- 安全和生产要求。
- 关联设计或决策。
- 关联 AI 开发记录。
- 当前状态。

## 影响范围评估

非平凡需求必须说明后端、前端、数据库、权限、安全、配置、测试、发布、回滚和 AI 功能影响。

评估时使用：

```text
harness-engineering/checklists/impact-scope-checklist.md
```

## 与 Harness Engineering 的关系

- 需求记录“为什么改”。
- AI 开发记录记录“怎么改”。
- 变更日志记录“改动概览”。
- ADR 记录“为什么选择这个方案”。
