# 技能说明

本目录用于保存 AI 开发技能说明。

本目录保存 Harness Engineering 的详细技能规则，不是 Codex 原生技能发现目录。

Codex 原生 repo 级技能入口位于：

```text
.agents/skills/<skill-name>/SKILL.md
```

`.agents/skills` 中的 `SKILL.md` 是薄封装，用于触发 Codex 技能；详细规则继续指向本目录，避免重复维护。

AI 只有在任务需要时才读取对应技能，避免每次都加载全部知识。

## 技能列表

- `requirements-design.md`：需求设计、影响范围评估和需求文档落盘。
- `ruoyi-cloud-backend.md`：RuoYi Cloud 后端开发。
- `spring-ai-alibaba.md`：Spring AI Alibaba 相关开发。
- `ruoyi-vue-frontend.md`：RuoYi Vue 前端开发。
- `database-mybatis.md`：数据库、实体、Mapper、SQL。
- `testing-verification.md`：测试和验证。
- `code-review.md`：代码审查。
