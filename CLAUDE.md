# Claude Code 入口

本文件用于兼容 Claude Code 的项目级记忆机制。

本项目的 Codex 默认工程约束入口是：

- `AGENTS.md`

Claude Code 在执行任何代码变更前，也应先读取 `AGENTS.md`，再按以下文件渐进加载：

- `harness-engineering/loaders/progressive-loading.md`
- `harness-engineering/context/project-map.md`
- `harness-engineering/constraints/coding-boundaries.md`
- `harness-engineering/constraints/token-budget.md`
- `harness-engineering/loaders/skill-loading-index.md`

规则摘要：

- 不默认扫描全仓库。
- 不做无关重构。
- 不修改认证、网关、公共模块或父级构建配置，除非用户明确要求。
- 只读取任务相关模块和同类实现。
- 每次变更更新 `harness-engineering/changes/CHANGELOG.md`。
- 最终输出保持简短，说明变更文件、验证结果和风险。
