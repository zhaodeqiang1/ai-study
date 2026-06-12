# 数据库和 MyBatis 技能

## 适用场景

当任务涉及表结构、实体、Mapper、XML、SQL 脚本、分页查询时读取本文件。

## 表设计

新增 Harness 业务表建议使用前缀：

```text
harness_
```

常见审计字段：

- `create_by`
- `create_time`
- `update_by`
- `update_time`
- `remark`
- `del_flag`

## SQL 位置

新增 SQL 脚本放在：

```text
sql/harness
```

生产迁移脚本优先放在：

```text
sql/harness/migrations
```

每个迁移必须关联 `docs/requirements` 中的需求编号。

## Mapper 规则

- XML 命名与 Mapper 接口保持一致。
- 查询字段显式列出，不使用 `select *`。
- 动态条件要避免空字符串误判。
- 分页查询遵循项目已有分页模式。

## 生产注意事项

- 高频查询字段需要索引。
- 大文本字段不要放在频繁列表查询中。
- 删除策略要明确是逻辑删除还是物理删除。
- 表结构变更必须提供回滚 SQL 或明确回滚方案。
- 无法回滚的 SQL 必须写明不可逆原因、风险、备份要求和人工确认要求。

## SQL 迁移硬性要求

每个 SQL/migration 必须包含：

- 正向 SQL。
- 回滚 SQL 或回滚方案。
- 数据影响说明，包括影响表、影响行数预估、是否锁表、是否需要备份。
- 部署顺序。
- 验证 SQL。
- 不可逆说明。

禁止只有正向 SQL。

推荐使用：

- `harness-engineering/templates/sql-migration-template.md`
- `harness-engineering/checklists/sql-migration-checklist.md`
