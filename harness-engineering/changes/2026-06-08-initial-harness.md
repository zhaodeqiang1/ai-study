# 初始化 Harness

## 日期

2026-06-08

## 任务

在项目根路径生成 Harness Engineering 目录和文件，用于约束 AI 开发行为，支持渐进加载、变更记录、模块地图、安全约束和技能加载。

## 变更文件

- `CLAUDE.md`
- `AGENTS.md`
- `.claude/commands/**`
- `harness-engineering/**`

## 变更内容

- 建立 AI 开发入口。
- 建立渐进加载机制。
- 建立项目模块地图。
- 建立编码、安全、生产和 Token 约束。
- 建立技能文件。
- 建立工作流、模板、检查清单和变更记录。
- 建立 Claude Code 兼容入口和命令模板。

## 验证

- 已检查文件生成结果。

## 风险

- 这些文件是工程约束文档，不参与运行时逻辑。
- 后续项目结构变化时，需要同步维护模块地图。

## 回滚方式

删除 `AGENTS.md`、`CLAUDE.md`、`.claude` 和 `harness-engineering` 目录即可回滚。
