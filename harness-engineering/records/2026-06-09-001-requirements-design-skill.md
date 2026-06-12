# 2026-06-09-001: 增加需求设计与影响范围评估技能

## 关联需求

- `docs/requirements/REQ-20260609-001-requirements-design-skill.md`

## 背景

用户询问是否已有需求设计技能，并明确提出需求技能应支持需求设计、影响范围评估，以及将需求文档输出到指定文档供后续流程使用。当前项目已有需求目录和需求契约，但缺少 Codex 原生可触发的需求设计技能。

## 本次改动

- 新增 `.agents/skills/requirements-design` Codex 原生技能入口。
- 新增 `harness-engineering/skills/requirements-design.md` 详细需求设计技能。
- 新增 `harness-engineering/checklists/impact-scope-checklist.md`。
- 更新需求 README、需求模板和需求契约，加入影响范围评估和后续流程衔接。
- 更新 `AGENTS.md`、渐进加载、技能加载索引、项目地图、技能 README 和功能开发流程。
- 更新 HTML 说明文档、需求索引、AI 开发记录索引和变更日志。

## 关键决策

- 需求文档固定输出到 `docs/requirements/REQ-YYYYMMDD-NNN-<english-slug>.md`，避免需求散落在对话或临时文档中。
- 需求技能只负责需求设计，不默认实现代码，避免用户还没确认需求时就进入开发。
- 影响范围评估独立成检查清单，方便后续 feature、review、testing 流程复用。
- `.agents/skills` 继续保持薄入口，详细规则仍在 `harness-engineering/skills`。

## 修改文件

- `.agents/skills/requirements-design/SKILL.md`
- `.agents/skills/requirements-design/agents/openai.yaml`
- `AGENTS.md`
- `docs/harness-engineering-guide.html`
- `docs/requirements/README.md`
- `docs/requirements/REQ-000-template.md`
- `docs/requirements/REQ-20260609-001-requirements-design-skill.md`
- `docs/requirements/INDEX.md`
- `harness-engineering/checklists/impact-scope-checklist.md`
- `harness-engineering/context/project-map.md`
- `harness-engineering/contracts/requirement-contract.md`
- `harness-engineering/loaders/progressive-loading.md`
- `harness-engineering/loaders/skill-loading-index.md`
- `harness-engineering/skills/README.md`
- `harness-engineering/skills/requirements-design.md`
- `harness-engineering/workflows/feature-workflow.md`
- `harness-engineering/records/2026-06-09-001-requirements-design-skill.md`
- `harness-engineering/records/INDEX.md`
- `harness-engineering/changes/CHANGELOG.md`

## 验证

- 执行 Codex skill validator，确认 `requirements-design` 技能结构有效。
- 检查需求索引、AI 开发记录索引、变更日志和 HTML 指南包含 `REQ-20260609-001` 和 `2026-06-09-001`。
- 检查需求模板、需求契约、需求技能和影响范围检查清单包含“影响范围评估”。
- 未执行 Maven/NPM 业务测试或构建，因为本次只修改 Harness 文档和技能入口，不修改业务运行时代码。

## 审查门结论

- 结论：`Pass`。
- 说明：本次变更补齐需求设计技能、影响范围检查清单、固定输出位置和后续流程衔接，不涉及 SQL、权限、生产配置或业务代码。

## 风险

- Codex 可能需要新会话或重启后才刷新新技能列表。
- 技能能约束后续 AI 流程，但不能自动保证历史需求文档都补齐影响范围，需要后续逐步治理。

## 后续事项

- 后续所有新功能开发前，优先用 `requirements-design` 技能创建或更新需求文档。
- 可以选择一个 Spring AI Alibaba 业务能力作为第一条真实业务需求，验证需求设计到开发、审查、测试的完整闭环。

