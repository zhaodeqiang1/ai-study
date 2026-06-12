# 实现功能

请先读取根目录 `AGENTS.md`，并按 `harness-engineering/loaders/progressive-loading.md` 渐进加载上下文。

使用流程：

- `harness-engineering/workflows/feature-workflow.md`

任务输入：

```text
功能描述：
需求编号：
目标模块：
禁止修改：
验收标准：
验证方式：
```

执行要求：

- 先给出简短计划。
- 确认或创建需求编号。
- 只读取目标模块和同类实现。
- 按 RuoYi Cloud 风格实现。
- 涉及 AI 功能时读取 `harness-engineering/skills/spring-ai-alibaba.md`。
- 实现后必须进入审查门，读取 `harness-engineering/workflows/review-workflow.md`、`harness-engineering/skills/code-review.md` 和 `harness-engineering/checklists/code-review-gate-checklist.md`。
- 审查通过后再执行验证。
- 非平凡开发必须新增 `harness-engineering/records` 独立记录。
- 完成后更新 `harness-engineering/changes/CHANGELOG.md`。
