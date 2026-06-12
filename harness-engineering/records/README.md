# AI 开发记录说明

本目录记录每次非平凡 AI 开发过程。它用于回答“AI 是怎么改的、为什么这么改、验证了什么、还有什么债”。

## 何时必须新增记录

满足任一条件时，必须新增独立记录：

- 新增或修改业务功能。
- 修改数据库、权限、菜单、配置、构建或部署。
- 修改 Harness Engineering 规则。
- 修复生产风险或安全问题。
- 涉及多个文件或多个模块。
- 有未完成风险、验证失败或后续事项。

## 记录编号

推荐格式：

```text
YYYY-MM-DD-NNN-short-name.md
```

示例：

```text
2026-06-08-001-harness-governance-feedback.md
```

## 与其他文档关系

- `docs/requirements`：记录为什么要做。
- `harness-engineering/records`：记录 AI 怎么做。
- `harness-engineering/changes/CHANGELOG.md`：记录变更概览。
- `harness-engineering/decisions`：记录架构决策。

