# Codex 项目入口

本文件是 Codex 的默认项目指导入口，只保留总入口、最高优先级红线和权威文件指针。

详细路由、触发阈值、技术栈基线、工作流、契约、检查清单和技能规则不得继续堆叠到本文件，应沉淀到 `harness-engineering` 下的对应 Markdown。

## 目标

通过 Codex 默认入口约束 AI 开发行为，让代码变更可控、可审计、可复用，并减少不必要的上下文读取和 Token 消耗。

## 绝对禁止事项

除非用户明确点名要求并确认风险，否则禁止：

- 禁止执行破坏性 Git 操作，例如 `git reset --hard`、强制回滚、覆盖用户未提交改动。
- 禁止删除、移动或重命名大范围文件，尤其是递归删除。
- 禁止默认扫描全仓库、全量读取所有 Java/XML/SQL/Vue 文件。
- 禁止修改 `ruoyi-auth`、`ruoyi-gateway`、`ruoyi-common`、根目录 `pom.xml`、全局安全配置。
- 禁止在源码、配置、SQL 或文档中写入真实密钥、Token、Access Key、Secret。
- 禁止绕过 RuoYi 既有权限体系新增管理接口。
- 禁止生成没有权限校验、没有参数校验、没有错误处理的生产接口。
- 禁止让 AI 输出直接执行高风险动作，例如删库、改权限、执行任意 SQL、发送外部通知。
- 禁止声称已经运行测试或构建，除非确实执行过对应命令。
- 禁止为了解决局部任务进行无关重构、依赖升级、格式化全文件或统一改名。

## 默认加载顺序

每次任务默认只读取以下文件：

1. `AGENTS.md`
2. `harness-engineering/loaders/harness-execution-routing.md`
3. `harness-engineering/loaders/progressive-loading.md`
4. `harness-engineering/context/project-map.md`
5. `harness-engineering/constraints/coding-boundaries.md`
6. `harness-engineering/constraints/token-budget.md`

只有在任务需要时，才继续读取对应技能、工作流、契约、模板、检查清单、需求或开发记录。

## 权威文件指针

- Harness 四层拆分、分支文件走向和触发阈值：`harness-engineering/loaders/harness-execution-routing.md`
- 渐进式加载：`harness-engineering/loaders/progressive-loading.md`
- 技能加载索引：`harness-engineering/loaders/skill-loading-index.md`
- 项目地图：`harness-engineering/context/project-map.md`
- 项目基础架构与技术栈基线：`harness-engineering/context/project-technology-baseline.md`
- 需求体系：`docs/requirements/README.md`
- AI 开发记录：`harness-engineering/records/README.md`
- 反馈循环：`harness-engineering/governance/feedback-loop.md`
- 反熵增治理：`harness-engineering/governance/anti-entropy-governance.md`
- 契约：`harness-engineering/contracts/README.md`
- 评测集：`harness-engineering/evaluations/README.md`

## 执行原则

- 先按 `harness-execution-routing.md` 判断任务类型和触发阈值。
- 再按 `progressive-loading.md` 和 `skill-loading-index.md` 渐进加载最小必要上下文。
- 项目级基础架构、技术栈、版本边界或基础中间件变更，更新 `project-technology-baseline.md`，不要把细节写入本文件。
- 需求级架构变更写入对应 `docs/requirements` 和 `docs/architecture`，不要写入本文件。
- 用户指出规则缺失、验证缺失、追溯缺失或生产风险时，进入 `feedback-loop.md`。

## 输出要求

最终回复只说明：

- 改了什么
- 改了哪些文件
- 做了什么验证
- 还有什么风险或下一步

