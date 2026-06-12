# REQ-20260608-001: 建立 Harness 反熵增治理与反馈循环机制

## 状态

Verified

## 背景

当前 Harness Engineering 已经具备入口、模块地图、编码边界、Token 预算、技能和工作流，但仍存在治理体系不足：

- 需求记录没有形成体系，难以追溯“为什么改”。
- AI 开发记录粒度不够，只有总变更日志，缺少每次非平凡开发的独立记录。
- SQL 回滚要求偏弱，无法稳定支撑生产迁移。
- 测试验证说明不可执行，缺少明确命令和失败记录规则。

## 目标

- 建立项目级需求目录、需求编号、需求索引、状态流转和验收标准沉淀。
- 建立每次非平凡 AI 开发的独立记录机制。
- 强化 SQL/migration 的正向、回滚、部署、验证和不可逆说明。
- 让测试验证从“应该验证”变成“按命令验证或明确说明无法验证”。
- 建立反熵增治理和反馈循环机制，防止 Harness 文档和实际项目持续漂移。

## 范围

包含：

- `docs/requirements` 需求体系。
- `harness-engineering/records` AI 开发记录体系。
- `harness-engineering/governance` 反熵增治理和反馈循环文档。
- SQL 迁移模板和检查清单。
- 测试验证命令约束。
- 入口、工作流、变更日志更新。

不包含：

- 修改业务运行代码。
- 新增真实数据库迁移。
- 执行后端或前端构建。

## 验收标准

- 存在需求索引和需求模板。
- 存在当前需求的独立需求文件。
- 存在 AI 开发记录索引、模板和当前变更记录。
- 存在反熵增治理和反馈循环机制文档。
- SQL 规则明确要求正向 SQL、回滚 SQL 或回滚方案、数据影响、部署顺序、验证 SQL、不可逆说明。
- 测试验证规则包含可执行 Maven 和前端命令。
- `AGENTS.md` 明确要求需求记录、开发记录和反馈循环。

## 安全和生产要求

- 权限：本次不涉及运行时权限。
- 输入校验：本次不涉及运行时输入。
- 输出安全：文档中不得包含真实密钥。
- 配置：本次不涉及运行时配置。
- 日志：需要更新 Harness 变更日志。
- 回滚：删除新增文档或回退文档修改即可。
- 验证：检查文件存在、旧入口引用不存在、关键规则已写入。

## 关联设计

- `harness-engineering/governance/anti-entropy-governance.md`
- `harness-engineering/governance/feedback-loop.md`

## 关联决策

- `harness-engineering/decisions/ADR-001-root-harness-engineering.md`

## 关联 AI 开发记录

- `harness-engineering/records/2026-06-08-001-harness-governance-feedback.md`

## 状态流转记录

| 日期 | 状态 | 说明 |
| --- | --- | --- |
| 2026-06-08 | Draft | 根据治理缺口创建需求 |
| 2026-06-08 | Implemented | 已补充需求、记录、治理、SQL、验证文档 |
| 2026-06-08 | Verified | 已完成文件生成和关键规则检查 |

