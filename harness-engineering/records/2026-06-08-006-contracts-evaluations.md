# 2026-06-08-006: 增加契约和评测集机制

## 关联需求

- `docs/requirements/REQ-20260608-006-contracts-evaluations.md`

## 背景

用户询问 Harness Engineering 是否有评测集和契约，以及是否需要。当前 Harness 规则较完整，但缺少可判定的合格标准和评测案例。

## 本次改动

- 新增 `harness-engineering/contracts`。
- 新增 `harness-engineering/evaluations`。
- 新增 `harness-engineering/checklists/evaluation-checklist.md`。
- 更新 `AGENTS.md`、feature workflow、review workflow、progressive loading、skill loading index、project map 和 production checklist。
- 更新 HTML 说明文档，说明契约和评测集为什么需要、解决什么问题、有哪些文件。
- 更新需求索引、AI 开发记录索引和变更日志。

## 关键决策

- 契约用于定义“做到什么才算合格”。
- 评测集用于定义“用什么案例检查是否合格”。
- 契约和评测分离，避免把规则和测试样例混在一起。
- 先做最小可用版本，不引入评测运行器。

## 修改文件

- `harness-engineering/contracts/**`
- `harness-engineering/evaluations/**`
- `harness-engineering/checklists/evaluation-checklist.md`
- `AGENTS.md`
- `harness-engineering/workflows/feature-workflow.md`
- `harness-engineering/workflows/review-workflow.md`
- `harness-engineering/loaders/progressive-loading.md`
- `harness-engineering/loaders/skill-loading-index.md`
- `harness-engineering/context/project-map.md`
- `harness-engineering/checklists/production-readiness.md`
- `docs/harness-engineering-guide.html`
- `docs/requirements/REQ-20260608-006-contracts-evaluations.md`
- `docs/requirements/INDEX.md`
- `harness-engineering/records/2026-06-08-006-contracts-evaluations.md`
- `harness-engineering/records/INDEX.md`
- `harness-engineering/changes/CHANGELOG.md`

## 验证

- 检查契约目录和评测目录是否存在。
- 检查 `AGENTS.md` 是否包含契约和评测要求。
- 检查 HTML 是否包含 contracts、evaluations、契约和评测集说明。
- 检查索引是否包含 `REQ-20260608-006` 和 `2026-06-08-006`。

## 风险

- 当前只有文档化评测集和评分标准，还没有自动评测执行器。
- 后续真实 AI 业务开发时，需要为具体业务补充领域评测集。

## 后续事项

- 后续实现 Spring AI Alibaba 业务功能时，为 RAG、Prompt、模型调用新增专项评测数据集。

