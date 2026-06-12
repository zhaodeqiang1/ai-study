# SQL 迁移模板

每个 SQL/migration 变更必须包含以下内容。不能只提供正向 SQL。

## 迁移编号

MIG-YYYYMMDD-NNN

## 关联需求

- REQ-YYYYMMDD-NNN

## 适用环境

- 开发：
- 测试：
- 预发：
- 生产：

## 正向 SQL

```sql
-- forward sql here
```

## 回滚 SQL

```sql
-- rollback sql here
```

如果无法提供回滚 SQL，必须填写“不可逆说明”。

## 数据影响

- 影响表：
- 影响行数预估：
- 是否锁表：
- 是否影响在线业务：
- 是否需要备份：

## 部署顺序

1. 
2. 
3. 

## 验证 SQL

```sql
-- verification sql here
```

## 不可逆说明

如果存在不可逆操作，必须说明：

- 为什么不可逆。
- 如何降低风险。
- 是否需要生产备份。
- 谁确认可以执行。

