# 2026-06-12-001: Harness 路由权威文档与 AGENTS 瘦身

## 关联需求

- `docs/requirements/REQ-20260612-001-harness-routing-and-agents-slimming.md`

## 背景

用户指出 Harness 缺少权威 Markdown 承载四层拆分、分支文件走向表和触发阈值表，相关规则分散在 HTML、渐进加载、技能加载索引和多个工作流中。同时 `AGENTS.md` 已经过长，不宜继续承载细节。

## 本次改动

- 新增 `harness-engineering/loaders/harness-execution-routing.md`。
- 新增 `harness-engineering/context/project-technology-baseline.md`。
- 瘦身 `AGENTS.md`，只保留入口、红线、默认加载顺序和权威文件指针。
- 更新 `progressive-loading.md` 和 `skill-loading-index.md`，将触发阈值权威来源指向路由文档。
- 更新项目地图、反馈循环和反熵增治理。
- 将 `REQ-20260609-003` 标记为 `Deprecated`，由 `REQ-20260612-001` 替代。
- 新增需求记录、AI 开发记录，并更新索引和变更日志。

## 关键决策

- `harness-execution-routing.md` 是 AI 执行任务的权威 Markdown 路由表。
- HTML 指南只作为说明展示，不作为 AI 执行时的唯一权威来源。
- `AGENTS.md` 不再承载详细技术栈、触发表、流程表或需求级事实。
- 项目技术栈基线独立沉淀到 `project-technology-baseline.md`。

## 修改文件

- `AGENTS.md`
- `harness-engineering/loaders/harness-execution-routing.md`
- `harness-engineering/loaders/progressive-loading.md`
- `harness-engineering/loaders/skill-loading-index.md`
- `harness-engineering/context/project-technology-baseline.md`
- `harness-engineering/context/project-map.md`
- `harness-engineering/governance/feedback-loop.md`
- `harness-engineering/governance/anti-entropy-governance.md`
- `docs/requirements/REQ-20260609-003-project-technology-baseline.md`
- `docs/requirements/REQ-20260612-001-harness-routing-and-agents-slimming.md`
- `docs/requirements/INDEX.md`
- `harness-engineering/records/2026-06-12-001-harness-routing-and-agents-slimming.md`
- `harness-engineering/records/INDEX.md`
- `harness-engineering/changes/CHANGELOG.md`

## 验证

- 检查路由文档包含“四层拆分”。
- 检查路由文档包含“触发阈值表”。
- 检查路由文档包含“分支文件走向表”。
- 检查 `AGENTS.md` 包含权威文件指针，并不再保存详细技术栈清单。
- 检查 `progressive-loading.md` 和 `skill-loading-index.md` 指向路由文档。
- 检查需求索引、AI 开发记录索引和变更日志包含本次记录。
- 未执行 Maven/NPM 业务测试或构建，因为本次只修改 Harness 文档，不修改业务代码。

## 审查门结论

- 结论：`Pass`。
- 说明：本次变更只调整 Harness 文档组织、路由权威来源和入口边界，不涉及运行时业务代码、SQL、权限或生产配置。

## 风险

- 后续新增路由规则时必须更新 `harness-execution-routing.md`，否则规则会再次分散。
- HTML 指南暂未同步完整重写，后续如继续作为展示材料，应引用本次新增的权威 Markdown。

## 后续事项

- 后续开发任务先读 `AGENTS.md`，再读 `harness-execution-routing.md`。
- 如用户继续指出触发阈值或路由缺口，应优先更新 `harness-execution-routing.md`。

