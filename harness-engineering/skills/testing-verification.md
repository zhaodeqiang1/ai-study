# 测试验证技能

## 适用场景

当任务涉及编译、测试、构建、验证、回归风险时读取本文件。

## 后端验证

优先选择最小验证范围：

- 新增或更新单元测试。
- 单模块测试。
- 单模块编译。
- 相关服务编译。

如果改动涉及父级依赖或跨模块契约，再扩大验证范围。

## 单元测试要求

非平凡代码开发必须优先新增或更新单元测试。

当前仓库尚未发现稳定的 `src/test` 目录，也未发现明确的 JUnit、Mockito 或 Spring Boot Test 依赖。第一次补充单元测试前，需要确认测试框架和依赖策略。

如果无法新增测试，必须记录：

- 无法新增的原因。
- 替代验证方式。
- 剩余风险。
- 后续补测建议。

推荐读取：

- `harness-engineering/contracts/testing-contract.md`
- `harness-engineering/checklists/unit-test-checklist.md`

可执行命令：

```powershell
# 根工程测试
mvn test

# 根工程完整验证
mvn clean verify

# 指定后端模块测试，示例为系统模块
mvn -pl ruoyi-modules/ruoyi-system -am test

# 指定后端模块跳过测试编译，示例为系统模块
mvn -pl ruoyi-modules/ruoyi-system -am -DskipTests package

# API 契约模块测试
mvn -pl ruoyi-api/ruoyi-api-system -am test
```

新增模块后，应将示例中的模块路径替换为目标模块路径。

## 前端验证

改动 Vue 页面或 API 时，优先执行：

- 构建。
- 关键页面手动检查。

当前 `ruoyi-ui/package.json` 没有定义 `lint` 脚本，因此不能声称已执行 lint。

可执行命令：

```powershell
cd ruoyi-ui
npm run build:prod
npm run build:stage
```

如果依赖未安装，需要先由用户允许安装依赖后再执行安装命令。

## SQL 验证

SQL 文件需要检查：

- 表名是否符合模块前缀。
- 字段类型是否合理。
- 索引是否匹配查询路径。
- 是否有正向 SQL。
- 是否有回滚 SQL 或回滚方案。
- 是否有数据影响说明。
- 是否有部署顺序。
- 是否有验证 SQL。
- 是否有不可逆说明。

SQL 验证命令依赖具体数据库连接。本地无法连接数据库时，必须至少做静态检查，并在最终回复中说明未执行数据库验证。

## 无法验证时

如果本地缺少依赖、服务或数据库，必须在最终回复中说明未验证原因和剩余风险。

## 记录要求

验证结果必须写入对应 AI 开发记录：

- 执行的命令。
- 命令结果。
- 失败摘要。
- 未执行原因。
- 后续验证建议。
