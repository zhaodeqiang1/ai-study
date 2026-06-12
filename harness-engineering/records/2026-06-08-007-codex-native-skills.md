# 2026-06-08-007: 调整技能到 Codex 原生发现位置

## 关联需求

- `docs/requirements/REQ-20260608-007-codex-native-skills.md`

## 背景

用户要求按 Codex 规范调整技能位置。此前 `harness-engineering/skills/*.md` 是 Harness 内部详细技能文档，但不是 Codex 原生可自动发现的 skill。

## 本次改动

- 新增 `.agents/skills`。
- 为 6 个技能创建标准 `SKILL.md` 薄封装。
- 为 6 个技能补充 `agents/openai.yaml` UI 元数据。
- 保留 `harness-engineering/skills` 作为详细规则源。
- 更新 `AGENTS.md`、技能 README、项目地图、技能加载索引和 HTML 说明文档。
- 更新需求索引、AI 开发记录索引和变更日志。

## 关键决策

- 使用 `.agents/skills/<skill-name>/SKILL.md` 作为 Codex 原生发现入口。
- 不删除 `harness-engineering/skills`，避免丢失现有 Harness 治理结构。
- `SKILL.md` 只做薄封装，指向 Harness 详细规则、契约和评测集。
- 这样既符合 Codex 规范，又避免两套长文档分叉。

## 修改文件

- `.agents/skills/**/SKILL.md`
- `.agents/skills/**/agents/openai.yaml`
- `AGENTS.md`
- `harness-engineering/skills/README.md`
- `harness-engineering/context/project-map.md`
- `harness-engineering/loaders/skill-loading-index.md`
- `docs/harness-engineering-guide.html`
- `docs/requirements/REQ-20260608-007-codex-native-skills.md`
- `docs/requirements/INDEX.md`
- `harness-engineering/records/2026-06-08-007-codex-native-skills.md`
- `harness-engineering/records/INDEX.md`
- `harness-engineering/changes/CHANGELOG.md`

## 验证

- 使用 `quick_validate.py` 验证 `.agents/skills` 下 6 个技能。
- 结果：6 个技能均输出 `Skill is valid!`。

## 风险

- Codex 可能需要新会话或重启后才刷新技能列表。
- 当前只是 repo 级技能，不是可分发 plugin。

## 后续事项

- 后续新增 Harness 技能时，先在 `.agents/skills/<skill-name>/SKILL.md` 增加薄封装，再把详细规则放到 `harness-engineering/skills`。

