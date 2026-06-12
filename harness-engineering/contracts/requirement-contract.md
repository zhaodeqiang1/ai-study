# 需求记录契约

每个非平凡需求必须满足本契约。

## 必须字段

- 需求编号，格式为 `REQ-YYYYMMDD-NNN`。
- 标题。
- 状态。
- 背景。
- 目标。
- 范围。
- 非目标。
- 影响范围评估。
- 验收标准。
- 安全和生产要求。
- 关联设计。
- 关联决策。
- 关联 AI 开发记录。
- 后续流程衔接。
- 状态流转记录。

## 存放位置

需求文档必须写入：

```text
docs/requirements/REQ-YYYYMMDD-NNN-<english-slug>.md
```

并登记到：

```text
docs/requirements/INDEX.md
```

文件名使用英文，正文使用中文。

## 状态要求

状态必须属于：

- `Draft`
- `Reviewed`
- `Approved`
- `InProgress`
- `Implemented`
- `Verified`
- `Released`
- `Rejected`
- `Deprecated`

## 验收要求

验收标准必须是可判断的，不能只有抽象描述。

不合格示例：

- “功能正常”
- “代码优雅”
- “体验好”

合格示例：

- “HTML 中存在结构图和流程图”
- “SQL 迁移包含正向 SQL、回滚 SQL、验证 SQL”
- “审查门结论必须为 Pass、NeedsFix 或 Blocked”

## 影响范围要求

非平凡需求必须按 `harness-engineering/checklists/impact-scope-checklist.md` 评估影响范围。

至少说明：

- 后端。
- 前端。
- 数据库和 SQL。
- 权限和安全。
- 配置和部署。
- 测试和验证。
- 发布和回滚。

不涉及的项必须写“不涉及”，不能省略。
