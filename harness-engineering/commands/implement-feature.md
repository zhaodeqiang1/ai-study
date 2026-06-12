# 实现功能命令

用途：让 AI 实现一个新功能。

```text
请读取 AGENTS.md，并按渐进加载规则执行。

使用 feature-workflow。

任务：<功能描述>
需求编号：<REQ-YYYYMMDD-NNN，没有则先创建>
目标模块：<模块路径>
不能修改：<禁止范围>
验收标准：<验收标准>

请先确认或创建需求编号，再给出简短计划。
实现后必须进入审查门，读取 review-workflow、code-review skill 和 code-review-gate checklist。
审查通过后再执行验证。
最后必须新增 harness-engineering/records 独立记录，并更新 changes/CHANGELOG.md。
```
