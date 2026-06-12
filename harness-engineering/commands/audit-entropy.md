# 反熵增审计命令

用途：让 AI 检查 Harness Engineering 是否出现需求、记录、SQL、验证、项目地图等治理漂移。

```text
请读取 AGENTS.md，并按渐进加载规则执行。

使用：
- harness-engineering/governance/anti-entropy-governance.md
- harness-engineering/governance/entropy-audit-checklist.md
- docs/requirements/INDEX.md
- harness-engineering/records/INDEX.md
- harness-engineering/changes/CHANGELOG.md

请检查：
- 是否有非平凡变更缺少需求编号
- 是否有非平凡 AI 开发缺少独立记录
- SQL/migration 是否缺少回滚和验证
- 测试验证是否不可复现
- 项目地图是否与目录结构不一致
- Harness 文件是否有重复、冲突或过期规则
```

