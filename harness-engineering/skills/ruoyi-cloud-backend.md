# RuoYi Cloud 后端技能

## 适用场景

当任务涉及 Java 后端、Controller、Service、Mapper、Feign API、权限注解、日志注解时读取本文件。

## 开发规则

- Controller 只负责参数接收、权限控制、调用 Service、返回结果。
- Service 负责业务校验、状态流转、事务边界。
- Mapper 负责数据库访问。
- 远程调用契约放在 `ruoyi-api`。
- 业务实现放在 `ruoyi-modules`。

## 权限

新增管理接口时，应按 RuoYi 风格设计权限标识，例如：

```text
harness:knowledge:list
harness:knowledge:add
harness:knowledge:edit
harness:knowledge:remove
```

## 日志

关键增删改操作需要考虑操作日志。

AI 模型调用日志不应只依赖操作日志，应有独立调用日志表或审计记录。

## 异常

不要吞异常。

业务异常应返回用户可理解的信息，技术细节进入服务端日志。
