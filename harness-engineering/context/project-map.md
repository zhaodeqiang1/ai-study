# 项目地图

当前项目是基于 RuoYi Cloud 的微服务后台系统。本文件用于帮助 AI 快速判断“哪个文件负责什么”，避免为了找上下文而扫描全仓库。

## 根目录文件

- `AGENTS.md`：Codex 默认项目入口，只保存最高优先级红线、默认加载顺序和权威文件指针。
- `CLAUDE.md`：Claude Code 兼容入口，只做转发说明，核心规则仍以 `AGENTS.md` 为准。
- `pom.xml`：Maven 父工程配置，管理版本、依赖和聚合模块。默认禁止修改。
- `README.md`：项目说明文档。
- `LICENSE`：开源协议。
- `.gitignore`：Git 忽略规则。

## 根目录目录

- `harness-engineering`：AI 工程约束层，只影响 AI 协作，不参与运行时代码。
- `docs`：项目级文档目录，其中 `docs/requirements` 用于记录需求、需求索引和状态流转，`docs/architecture` 用于记录架构设计。
- `.agents`：Codex repo 级技能目录，标准技能入口位于 `.agents/skills/<skill-name>/SKILL.md`。
- `.claude`：Claude Code 命令模板目录。
- `ruoyi-gateway`：网关服务，负责统一入口、路由转发、网关过滤等。默认禁止修改。
- `ruoyi-auth`：认证服务，负责登录、令牌、认证相关能力。默认禁止修改。
- `ruoyi-api`：远程调用 API 契约，供服务间调用复用。
- `ruoyi-common`：公共能力模块，包括核心工具、安全、日志、Redis、Swagger、数据权限等。默认禁止修改。
- `ruoyi-modules`：业务服务模块，普通业务开发优先落在这里。
- `ruoyi-visual`：监控、可视化相关服务。
- `ruoyi-ui`：前端 Vue 管理后台。
- `sql`：数据库初始化、菜单、权限和业务表脚本。
- `docker`：容器化部署相关文件。默认不要修改。
- `bin`：启动、停止、运维脚本。默认不要修改。

## Harness Engineering 目录

- `.agents/skills`：Codex 原生技能入口，存放标准 `SKILL.md` 薄封装。
- `harness-engineering/context`：项目地图、项目技术栈基线、模块地图、领域地图、仓库阅读指南。
- `harness-engineering/constraints`：编码边界、文件访问策略、安全约束、生产约束、Token 预算、输出格式。
- `harness-engineering/loaders`：Harness 执行路由、渐进式加载规则和技能加载索引。
- `harness-engineering/skills`：不同技术栈的详细技能说明，由 `.agents/skills` 的标准技能入口引用。
- `harness-engineering/workflows`：功能开发、调试、审查、重构流程。
- `harness-engineering/templates`：任务简报、变更记录、ADR、模块地图、技能模板。
- `harness-engineering/checklists`：生产可用、安全、代码审查门、影响范围评估、单元测试、SQL 迁移、Token 节省检查清单。
- `harness-engineering/contracts`：需求、AI 变更、审查门、测试、SQL、AI 功能契约。
- `harness-engineering/evaluations`：评测集、评测用例和评分标准。
- `harness-engineering/changes`：AI 变更日志，每次 AI 修改代码或约束文件后应更新。
- `harness-engineering/records`：每次非平凡 AI 开发的独立记录。
- `harness-engineering/governance`：反熵增治理、反馈循环和审计清单。
- `harness-engineering/memory`：项目长期记忆和当前重点。
- `harness-engineering/commands`：可复制使用的任务命令模板。
- `harness-engineering/decisions`：架构决策记录。

## 后端聚合模块

- `ruoyi-api/pom.xml`：API 契约聚合模块配置。
- `ruoyi-api/ruoyi-api-system`：系统服务远程 API 契约。
- `ruoyi-common/pom.xml`：公共能力聚合模块配置。
- `ruoyi-common/ruoyi-common-core`：核心工具、通用实体、基础常量。
- `ruoyi-common/ruoyi-common-security`：安全、权限、认证上下文相关能力。默认禁止修改。
- `ruoyi-common/ruoyi-common-log`：操作日志相关能力。
- `ruoyi-common/ruoyi-common-redis`：Redis 封装能力。
- `ruoyi-common/ruoyi-common-swagger`：接口文档配置能力。
- `ruoyi-common/ruoyi-common-datascope`：数据权限能力。
- `ruoyi-common/ruoyi-common-datasource`：数据源能力。
- `ruoyi-common/ruoyi-common-sensitive`：敏感信息处理能力。
- `ruoyi-common/ruoyi-common-seata`：分布式事务相关能力。
- `ruoyi-modules/pom.xml`：业务服务聚合模块配置。
- `ruoyi-modules/ruoyi-system`：系统管理业务。
- `ruoyi-modules/ruoyi-gen`：代码生成业务。
- `ruoyi-modules/ruoyi-job`：定时任务业务。
- `ruoyi-modules/ruoyi-file`：文件服务业务。
- `ruoyi-visual/pom.xml`：可视化服务聚合模块配置。
- `ruoyi-visual/ruoyi-monitor`：监控服务。

## 后端模块内部结构

以下结构适用于 `ruoyi-modules/*` 下的大多数业务服务：

- `pom.xml`：当前模块依赖和构建配置。
- `src/main/java`：Java 源码。
- `src/main/java/**/controller`：Controller 层，负责请求入口、权限注解、参数接收、返回响应。
- `src/main/java/**/domain`：领域对象目录，通常包含实体、DTO、VO。
- `src/main/java/**/mapper`：MyBatis Mapper 接口。
- `src/main/java/**/service`：Service 接口，定义业务能力。
- `src/main/java/**/service/impl`：Service 实现，承载主要业务逻辑。
- `src/main/resources/mapper`：MyBatis XML 映射文件。
- `src/main/resources`：模块配置、Mapper XML、其他资源文件。
- `src/test`：测试代码。

## 前端根文件

- `ruoyi-ui/package.json`：前端依赖、脚本命令。
- `ruoyi-ui/vue.config.js`：Vue CLI 构建和代理配置。
- `ruoyi-ui/babel.config.js`：Babel 配置。
- `ruoyi-ui/.env.development`：开发环境变量。
- `ruoyi-ui/.env.production`：生产环境变量。
- `ruoyi-ui/.env.staging`：预发布环境变量。

## 前端源码结构

- `ruoyi-ui/src/main.js`：前端应用入口。
- `ruoyi-ui/src/App.vue`：根组件。
- `ruoyi-ui/src/permission.js`：前端路由权限控制。默认不要修改。
- `ruoyi-ui/src/settings.js`：前端基础设置。
- `ruoyi-ui/src/api`：后端接口封装，新增业务 API 应放在对应模块目录。
- `ruoyi-ui/src/views`：页面目录，新增业务页面应放在对应模块目录。
- `ruoyi-ui/src/router`：路由配置。
- `ruoyi-ui/src/store`：Vuex 状态管理。
- `ruoyi-ui/src/layout`：后台布局。
- `ruoyi-ui/src/components`：通用组件。
- `ruoyi-ui/src/utils`：前端工具函数。
- `ruoyi-ui/src/assets`：静态资源、图标、样式。
- `ruoyi-ui/src/directive`：自定义指令。
- `ruoyi-ui/src/plugins`：前端插件封装。

## SQL 目录

- `sql`：项目数据库脚本总目录。
- `sql/harness`：Harness / AI 业务推荐 SQL 落点。
- `sql/harness/migrations`：Harness / AI 业务生产迁移推荐目录，要求正向、回滚、验证和不可逆说明。

新增 AI 业务表、菜单、权限、字典脚本时，优先放在 `sql/harness`，不要直接修改已有主初始化脚本，除非用户明确要求。

## AI / Harness 推荐落点

如果后续实现 AI 业务模块，优先使用：

- 后端业务：`ruoyi-modules/ruoyi-harness`
- 远程 API：`ruoyi-api/ruoyi-api-harness`
- 前端 API：`ruoyi-ui/src/api/harness`
- 前端页面：`ruoyi-ui/src/views/harness`
- SQL：`sql/harness`

推荐业务子域：

- `knowledge`：知识库管理。
- `document`：文档上传、解析、切片、索引。
- `conversation`：会话与消息。
- `prompt`：提示词模板。
- `model`：模型配置。
- `retrieval`：检索与 RAG。
- `evaluation`：回答评价与质量评估。
- `log`：模型调用日志和 Token 统计。

## 默认不要修改

除非用户明确要求，AI 不应修改：

- `ruoyi-auth`
- `ruoyi-gateway`
- `ruoyi-common`
- 根目录 `pom.xml`
- `ruoyi-ui/src/permission.js`
- 全局安全配置
- Docker 和运维脚本
- 已有系统管理核心逻辑
