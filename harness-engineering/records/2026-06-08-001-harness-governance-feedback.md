# 2026-06-08-001: Harness 反熵增治理与反馈循环机制

## 关联需求

- `docs/requirements/REQ-20260608-001-harness-governance-feedback.md`

## 背景

用户指出当前 Harness Engineering 仍缺少完整的反熵增治理和反馈循环机制，尤其是需求体系、独立 AI 开发记录、SQL 回滚硬约束、可执行验证命令。

## 本次改动

- 新增 `docs/requirements` 需求体系。
- 新增 `harness-engineering/records` AI 开发记录体系。
- 新增 `harness-engineering/governance` 反熵增治理和反馈循环机制。
- 强化 SQL/migration 的正向、回滚、部署、验证和不可逆说明。
- 强化测试验证命令和无法验证时的报告规则。
- 更新入口、工作流、变更日志和项目地图。

## 关键决策

- 使用根目录 `docs/requirements` 承载项目级需求，因为需求是项目事实，不只是 Harness 内部机制。
- 使用 `harness-engineering/records` 承载 AI 开发记录，和总变更日志分离。
- 将 SQL 回滚规则从“考虑回滚”提升为“必须提供回滚 SQL 或明确不可逆说明”。
- 将验证规则从原则描述提升为可执行命令清单。

## 验证

- 检查新增文件是否存在。
- 检查入口文件是否写入治理和记录要求。
- 检查 SQL 规则是否包含正向 SQL、回滚 SQL、数据影响、部署顺序、验证 SQL、不可逆说明。
- 检查测试验证规则是否包含后端和前端命令。

## 风险

- 本次只修改工程文档，不影响运行时代码。
- 后续如果项目结构变化，需要同步维护项目地图和验证命令。

## 后续事项

- 后续每次非平凡 AI 开发都应新增独立记录。
- 后续每个功能需求都应先进入 `docs/requirements/INDEX.md`。
- 后续 SQL 变更应使用 SQL migration 模板。

