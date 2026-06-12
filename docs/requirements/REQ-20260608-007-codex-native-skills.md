# REQ-20260608-007: 调整技能到 Codex 原生发现位置

## 状态

Verified

## 背景

当前项目已有 `harness-engineering/skills` 技能说明文件，但它们不在 Codex 原生技能发现目录中。根据 Codex 技能规范，repo 级技能应位于 `.agents/skills/<skill-name>/SKILL.md`，并包含 `name` 和 `description` frontmatter。

## 目标

- 在 `.agents/skills` 下创建 Codex 原生 repo 级技能入口。
- 保留 `harness-engineering/skills` 作为详细规则源。
- 使用薄封装方式，避免维护两套长文档。
- 验证所有新增技能符合 Codex skill 基本结构。

## 范围

包含：

- `.agents/skills/ruoyi-cloud-backend`
- `.agents/skills/spring-ai-alibaba`
- `.agents/skills/ruoyi-vue-frontend`
- `.agents/skills/database-mybatis`
- `.agents/skills/testing-verification`
- `.agents/skills/code-review`
- `AGENTS.md`
- `harness-engineering/skills/README.md`
- `harness-engineering/context/project-map.md`
- `harness-engineering/loaders/skill-loading-index.md`
- `docs/harness-engineering-guide.html`
- 需求索引、AI 开发记录索引和变更日志。

不包含：

- 删除 `harness-engineering/skills`。
- 将详细技能规则复制到 `.agents/skills`。
- 打包成 Codex plugin。

## 验收标准

- `.agents/skills` 下存在 6 个技能目录。
- 每个技能目录包含 `SKILL.md`。
- 每个 `SKILL.md` 包含 `name` 和 `description` frontmatter。
- 技能验证脚本通过。
- 文档说明 `.agents/skills` 和 `harness-engineering/skills` 的职责区别。

## 安全和生产要求

- 权限：不涉及运行时权限。
- 输入校验：不涉及运行时输入。
- 输出安全：不得包含真实密钥。
- 配置：不涉及业务配置。
- 日志：更新 Harness 变更日志。
- 回滚：删除 `.agents/skills` 并回退相关文档修改。
- 验证：执行 Codex skill validator。

## 关联设计

- `.agents/skills`
- `harness-engineering/skills/README.md`
- `docs/harness-engineering-guide.html`

## 关联决策

- `harness-engineering/decisions/ADR-001-root-harness-engineering.md`

## 关联 AI 开发记录

- `harness-engineering/records/2026-06-08-007-codex-native-skills.md`

## 状态流转记录

| 日期 | 状态 | 说明 |
| --- | --- | --- |
| 2026-06-08 | Draft | 根据用户要求创建技能位置调整需求 |
| 2026-06-08 | Implemented | 已创建 `.agents/skills` 标准技能入口 |
| 2026-06-08 | Verified | 已执行 skill validator 并通过 |

