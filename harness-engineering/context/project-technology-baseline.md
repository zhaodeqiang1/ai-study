# 项目基础架构与技术栈基线

本文件记录全项目长期稳定的基础架构、技术栈和版本边界，不记录某个需求导致的局部架构变更。

## 项目基础描述

- 本项目基于 RuoYi Cloud 3.6.8。
- 项目形态是前后端分离的分布式微服务架构。
- 后端采用 Spring Boot、Spring Cloud 和 Spring Cloud Alibaba。
- 前端采用 RuoYi Vue、Vue 和 Element UI。

## 后端基础版本

- JDK：17。
- Spring Boot：4.0.3。
- Spring Cloud：2025.1.0。
- Spring Cloud Alibaba：2025.1.0.0。
- MyBatis Spring Boot Starter：4.0.1。
- RuoYi：3.6.8。

## 基础中间件和能力

- 注册中心和配置中心：Nacos。
- 缓存和认证辅助：Redis。
- 关系型数据库：MySQL。
- 流量控制：Sentinel。
- 分布式事务：Seata。
- 数据访问：MyBatis。
- 连接池：Druid。

## AI 方向基础设施

- Java AI 框架方向：Spring AI Alibaba。
- 本地模型运行时：Ollama。
- 本地大模型：DeepSeek R1 7B。
- 本地向量模型：bge-m3。
- 向量数据库：PostgreSQL，已启用 `pgvector`。

## 基线变更规则

- 禁止为了局部需求擅自升级 JDK、Spring Boot、Spring Cloud、Spring Cloud Alibaba、RuoYi 或核心中间件版本。
- 禁止为了局部需求擅自替换基础中间件、模型运行时、AI 框架方向或数据库选型。
- 禁止绕过现有技术栈引入新的重型依赖、模型网关、ORM 框架、权限框架或前端框架。
- 如确需变更项目基础架构或技术栈基线，必须先形成需求编号，说明原因、影响范围、替代方案、回滚方案和验证方式，并更新本文件、需求文档、架构文档、AI 开发记录和变更日志。

## 边界说明

- 项目级基线写入本文件。
- 需求级架构写入对应 `docs/requirements` 和 `docs/architecture`。
- `AGENTS.md` 只保留本文件的指针，不保存本文件的详细内容。

