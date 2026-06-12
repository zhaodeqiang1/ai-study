# 功能开发流程

新功能开发流程。

## 1. 确定范围

先确认：

- 需求编号。
- 业务目标。
- 目标模块。
- 需要新增的 API、页面、表结构。
- 不允许修改的范围。

如果是非平凡功能但没有需求编号，先使用 `harness-engineering/skills/requirements-design.md` 进行需求设计，在 `docs/requirements` 创建需求文件，并登记到 `docs/requirements/INDEX.md`。

需求文件必须包含影响范围评估，供后续实现、审查、测试和发布判断使用。

## 2. 读取上下文

按渐进加载规则读取：

- 入口文件。
- 项目地图。
- 编码边界。
- 相关技能。
- 同模块同类实现。

## 3. 输出简短计划

计划必须包含：

- 关联需求编号。
- 适用契约。
- 是否需要评测集。
- 单元测试计划。
- 要编辑的文件。
- 要新增的文件。
- 验证命令。
- 生产风险。

## 4. 实现

按照已有 RuoYi 风格实现。

新增或修改业务逻辑时，优先新增或更新单元测试。

如果无法新增测试，必须在计划和 AI 开发记录中说明原因、替代验证方式、剩余风险和后续补测建议。

## 5. 审查门

非平凡代码实现后，必须进入审查门，再进入验证。

读取：

- `harness-engineering/workflows/review-workflow.md`
- `harness-engineering/skills/code-review.md`
- `harness-engineering/checklists/code-review-gate-checklist.md`
- `harness-engineering/contracts/ai-change-contract.md`
- `harness-engineering/contracts/testing-contract.md`
- `harness-engineering/checklists/unit-test-checklist.md`

审查结论必须是：

- `Pass`：可以进入验证。
- `NeedsFix`：先修复问题，再重新审查。
- `Blocked`：需要用户确认或外部条件。

审查结果必须写入 AI 开发记录。

## 6. 契约和评测

非平凡功能必须检查适用契约：

- `harness-engineering/contracts/requirement-contract.md`
- `harness-engineering/contracts/ai-change-contract.md`
- `harness-engineering/contracts/testing-contract.md`
- 领域相关契约，例如 SQL、AI 功能、审查门。

如果是 AI、SQL、审查门或 Harness 治理变更，必须说明是否使用评测集：

- 使用评测集时，记录评测集编号、通过项和失败项。
- 不使用评测集时，说明不适用原因。

契约检查和评测结果必须写入 AI 开发记录。

## 7. 记录变更

更新：

- `harness-engineering/changes/CHANGELOG.md`
- `harness-engineering/records/INDEX.md`

非平凡 AI 开发必须新增：

- `harness-engineering/records/YYYY-MM-DD-NNN-<change-name>.md`

必要时更新：

- `docs/requirements/INDEX.md`
- 对应 `docs/requirements/REQ-*.md`
- `harness-engineering/decisions/ADR-*.md`

## 8. 验证

运行最小有效验证。

验证结果必须写入 AI 开发记录。无法验证时，必须写明原因和剩余风险。

## 9. 汇报

最终说明变更、文件、验证和风险。
