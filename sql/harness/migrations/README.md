# Harness SQL Migrations

本目录用于放置 Harness / AI 业务相关 SQL 迁移。

## 文件命名

推荐格式：

```text
MIG-YYYYMMDD-NNN-short-name.sql
MIG-YYYYMMDD-NNN-short-name.rollback.sql
MIG-YYYYMMDD-NNN-short-name.verify.sql
```

## 必须包含

每个迁移必须在对应文档或 SQL 注释中说明：

- 关联需求编号。
- 正向 SQL。
- 回滚 SQL 或回滚方案。
- 数据影响。
- 部署顺序。
- 验证 SQL。
- 不可逆说明。

## 模板

使用：

- `harness-engineering/templates/sql-migration-template.md`
- `harness-engineering/checklists/sql-migration-checklist.md`

