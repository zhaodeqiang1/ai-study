# 反馈循环机制

反馈循环用于把一次 AI 开发中的经验、失败、风险和用户反馈沉淀回 Harness Engineering。

## 循环路径

```text
需求 -> 计划 -> 实现 -> 审查 -> 验证 -> 记录 -> 复盘 -> 更新 Harness -> 下一次开发
```

## 每次非平凡开发后的必做事项

1. 更新需求状态。
2. 执行审查门，并记录 Pass、NeedsFix 或 Blocked。
3. 新增或更新 AI 开发记录。
4. 更新总变更日志。
5. 记录验证命令和结果。
6. 记录风险和后续事项。
7. 如果发现规则缺口，更新对应 Harness 文件。

## 用户反馈处理

当用户指出遗漏、方向错误、风险或质量问题时，AI 必须判断反馈类型：

- 需求缺失：更新 `docs/requirements`。
- 规则缺失：更新 `harness-engineering/constraints`。
- 技能缺失：更新 `harness-engineering/skills`。
- 流程缺失：更新 `harness-engineering/workflows`。
- 验证缺失：更新 `harness-engineering/skills/testing-verification.md` 或检查清单。
- 记录缺失：更新 `harness-engineering/records`。
- 契约缺失：更新 `harness-engineering/contracts`。
- 评测缺失：更新 `harness-engineering/evaluations`。
- 路由缺失：更新 `harness-engineering/loaders/harness-execution-routing.md`。
- 项目技术栈基线缺失：如果用户确认或纠正了项目级基础架构、技术栈、版本边界、基础中间件或 AI 基础设施，更新 `harness-engineering/context/project-technology-baseline.md`，并同步更新对应需求、架构文档、AI 开发记录和变更日志。

## 失败反馈

如果验证失败、构建失败、测试失败或上线风险暴露，必须沉淀：

- 失败现象。
- 触发条件。
- 根因判断。
- 修复方式。
- 防止复发的 Harness 更新。

## 规则升级条件

满足以下任一条件，应把经验升级为 Harness 规则：

- 同类问题出现两次以上。
- 问题影响生产安全、权限、数据或部署。
- 问题导致大量 Token 浪费。
- 问题导致 AI 修改了无关文件。
- 用户明确指出这是长期要求。
- 用户指出入口过长、路由分散、触发阈值不清或 HTML 规则没有 Markdown 权威来源。
- 用户确认或纠正了项目级基础架构、技术栈、版本边界、基础中间件或 AI 基础设施。

## 反馈闭环完成标准

一次反馈闭环完成时，应能回答：

- 需求记录在哪里？
- AI 开发记录在哪里？
- 变更日志是否有概览？
- 验证结果是什么？
- 审查结果是什么？
- 风险是否被记录？
- 是否需要更新约束、技能或工作流？
- 是否需要更新契约或评测集？
