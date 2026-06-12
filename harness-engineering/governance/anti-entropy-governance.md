# 反熵增治理

反熵增治理的目标是防止项目在 AI 频繁参与后出现文档漂移、规则失效、需求失联、验证缺失和历史不可追溯。

## 熵增表现

以下情况代表 Harness 正在熵增：

- 需求没有编号，无法追溯来源。
- 代码变更只有最终结果，没有背景和关键决策。
- `CHANGELOG.md` 记录过粗，无法还原一次 AI 开发过程。
- 项目地图和真实目录结构不一致。
- 技能文件写了原则，但没有可执行命令。
- SQL 脚本只有正向变更，没有回滚或不可逆说明。
- 检查清单长期不更新，和真实生产风险脱节。
- 同一规则散落在多个文件中且互相矛盾。
- 路由规则只存在于 HTML 或对话中，没有权威 Markdown。
- `AGENTS.md` 堆积过多细节，导致入口难维护。

## 治理规则

### 需求治理

- 每个非平凡功能必须有需求编号。
- 需求必须登记在 `docs/requirements/INDEX.md`。
- 需求状态必须随实现推进更新。
- 已废弃需求必须标记为 `Deprecated` 或 `Rejected`，不能直接删除。

### 变更治理

- 每次非平凡 AI 开发必须新增 `harness-engineering/records` 下的独立记录。
- `harness-engineering/changes/CHANGELOG.md` 只保存概览，不替代独立记录。
- 独立记录必须包含背景、改动、关键决策、验证、风险、后续事项。

### 文档治理

- 新增规则前先检查是否已有相同规则。
- 发现重复规则时，应合并到权威文件。
- 项目结构变化后必须更新 `harness-engineering/context/project-map.md`。
- 技能变更后必须检查 `harness-engineering/loaders/skill-loading-index.md` 是否需要更新。
- 路由、触发阈值或分支文件走向变化后，必须更新 `harness-engineering/loaders/harness-execution-routing.md`。
- `AGENTS.md` 只保留入口、红线和权威文件指针，细节必须下沉到对应 Harness Markdown。

### 验证治理

- 能执行命令时必须执行。
- 不能执行命令时必须记录原因。
- 验证失败不能伪装成功，必须记录失败输出摘要和下一步。

## 周期检查

建议每 5 次非平凡 AI 变更或每周执行一次轻量治理检查：

- `docs/requirements/INDEX.md` 是否覆盖所有非平凡需求。
- `harness-engineering/records/INDEX.md` 是否覆盖所有非平凡 AI 开发。
- `harness-engineering/changes/CHANGELOG.md` 是否有对应概览。
- 项目地图是否与目录结构一致。
- SQL 变更是否都有回滚或不可逆说明。
- 验证记录是否可复现。

## 清理规则

- 不删除历史需求和开发记录，只调整状态。
- 不保留无引用的临时规则。
- 不让模板文件混入具体项目事实。
- 不把一次性问题写成永久规则，除非它会重复发生。
