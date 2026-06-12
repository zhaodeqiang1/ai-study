# ADR-001: 根路径 Harness Engineering

## 状态

已接受

## 背景

项目计划使用 AI 辅助开发 Spring AI Alibaba 和 RuoYi Cloud 相关业务。如果没有统一约束，AI 容易扫描过多代码、修改无关模块、生成不可控实现，并造成 Token 浪费。

## 决策

在项目根路径创建 `AGENTS.md` 和 `harness-engineering` 目录。

`AGENTS.md` 作为 Codex 默认 AI 入口文件，`harness-engineering` 保存上下文、约束、技能、工作流、模板、检查清单、变更记录和架构决策。

## 影响

正向影响：

- AI 上下文加载更小。
- 代码变更边界更清楚。
- 生产约束提前暴露。
- 每次变更更容易追踪。

负向影响：

- 需要持续维护这些约束文件。
- 如果后续 AI 没有被要求读取入口文件，约束不会自动生效。
