# 修复问题

请先读取根目录 `AGENTS.md`，并按渐进加载规则执行。

使用流程：

- `harness-engineering/workflows/debug-workflow.md`

任务输入：

```text
问题描述：
复现方式：
目标模块：
禁止修改：
期望结果：
```

执行要求：

- 先定位问题原因。
- 只做最小修复。
- 不顺手重构。
- 修复后运行相关验证。
- 涉及生产、安全、权限、数据或多文件时，新增独立 AI 开发记录。
- 完成后更新 `harness-engineering/changes/CHANGELOG.md`。
