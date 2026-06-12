# Harness Engineering 说明

`harness-engineering` 是项目根路径下的 AI 工程约束层。

它的作用不是参与运行时业务，而是为 AI 开发提供稳定的上下文、边界、技能、任务模板和变更记录，使每次代码生成都更可控、更节省 Token。

## 目录说明

- `context`：项目上下文和模块地图。
- `constraints`：编码边界、安全约束、Token 预算。
- `loaders`：渐进式上下文加载规则。
- `memory`：项目长期记忆和当前重点。
- `skills`：面向不同技术栈和任务类型的技能说明。
- `workflows`：功能开发、调试、审查等流程。
- `prompts`：可复用提示词。
- `templates`：任务简报、变更记录、ADR 模板。
- `checklists`：上线前、安全、测试检查清单。
- `changes`：每次 AI 变更记录。
- `records`：每次非平凡 AI 开发的独立记录。
- `governance`：反熵增治理和反馈循环。
- `decisions`：架构决策记录。
- `commands`：类似 Claude Code slash commands 的任务指令模板。

## 使用方式

给 AI 发任务时可以这样描述：

```text
请先读取 AGENTS.md，并按 harness-engineering/loaders/progressive-loading.md 渐进加载上下文。
本次任务是：<你的任务>
不要扫描全仓库，不要修改公共模块。
```
