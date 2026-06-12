# 技能加载索引

本文件用于告诉 AI 如何按任务加载技能，避免一次性读取全部技能文件。

任务类型和触发阈值以 `harness-engineering/loaders/harness-execution-routing.md` 为权威来源。

Codex 原生技能入口位于 `.agents/skills/<skill-name>/SKILL.md`。

本文件中的 `skills/*.md` 指 `harness-engineering/skills` 下的详细规则文件。

## 需求设计

读取：

- `skills/requirements-design.md`
- `contracts/requirement-contract.md`
- `checklists/impact-scope-checklist.md`
- `docs/requirements/README.md`
- `docs/requirements/REQ-000-template.md`

输出：

- `docs/requirements/REQ-YYYYMMDD-NNN-<english-slug>.md`
- `docs/requirements/INDEX.md`

## 后端接口开发

读取：

- `skills/ruoyi-cloud-backend.md`
- `skills/database-mybatis.md`
- `contracts/testing-contract.md`
- `checklists/unit-test-checklist.md`

可选读取：

- `constraints/security-constraints.md`
- `checklists/production-readiness.md`

## Spring AI Alibaba 功能

读取：

- `skills/spring-ai-alibaba.md`
- `constraints/security-constraints.md`
- `constraints/production-constraints.md`

可选读取：

- `skills/database-mybatis.md`
- `skills/testing-verification.md`

## 前端页面开发

读取：

- `skills/ruoyi-vue-frontend.md`

可选读取：

- `checklists/production-readiness.md`

## SQL 或表结构

读取：

- `skills/database-mybatis.md`
- `constraints/production-constraints.md`
- `contracts/sql-migration-contract.md`
- `checklists/sql-migration-checklist.md`

## Debug

读取：

- `workflows/debug-workflow.md`
- `skills/testing-verification.md`
- `contracts/testing-contract.md`

只在涉及具体技术时读取对应技能。

## Review

读取：

- `workflows/review-workflow.md`
- `skills/code-review.md`
- `constraints/security-constraints.md`
- `contracts/ai-change-contract.md`
- `contracts/review-gate-contract.md`

## AI 功能评测

读取：

- `contracts/ai-feature-contract.md`
- `evaluations/README.md`
- `evaluations/INDEX.md`
- `checklists/evaluation-checklist.md`
