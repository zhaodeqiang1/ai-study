# 仓库阅读指南

本文件帮助 AI 在 RuoYi Cloud 项目中快速找文件。

## 后端查找顺序

如果任务是某个业务接口：

1. 找 Controller。
2. 找 Service 接口。
3. 找 Service 实现。
4. 找 Mapper 接口。
5. 找 Mapper XML。
6. 找实体、DTO、VO。
7. 必要时找 SQL。

## 前端查找顺序

如果任务是某个页面：

1. 找 `src/views` 下页面。
2. 找 `src/api` 下 API 文件。
3. 找菜单或路由配置。
4. 找组件。

## AI 业务查找顺序

如果任务是 Spring AI Alibaba 或 RAG：

1. 找 Harness 业务模块。
2. 找模型配置。
3. 找 Prompt。
4. 找文档处理。
5. 找向量检索。
6. 找调用日志。

## 不要一开始就查

- 所有 Java 文件。
- 所有 XML 文件。
- 所有 SQL 文件。
- 所有前端页面。
