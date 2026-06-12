# 模块地图

本文件用于快速判断任务归属，避免 AI 盲目扫描项目。

## 后端

### 系统管理

归属路径：

- `ruoyi-modules/ruoyi-system`
- `ruoyi-api/ruoyi-api-system`
- `ruoyi-ui/src/views/system`
- `ruoyi-ui/src/api/system`

常见内容：

- 用户
- 角色
- 菜单
- 部门
- 岗位
- 字典
- 参数配置
- 通知公告
- 操作日志
- 登录日志

### 文件服务

归属路径：

- `ruoyi-modules/ruoyi-file`

常见内容：

- 文件上传
- 文件下载
- 对象存储

### 代码生成

归属路径：

- `ruoyi-modules/ruoyi-gen`
- `ruoyi-ui/src/views/tool/gen`

### 定时任务

归属路径：

- `ruoyi-modules/ruoyi-job`
- `ruoyi-ui/src/views/monitor/job`

## 前端

前端 API 统一放在：

- `ruoyi-ui/src/api`

前端页面统一放在：

- `ruoyi-ui/src/views`

## Harness AI 业务

推荐模块划分：

- `knowledge`：知识库管理。
- `document`：文档上传、解析、切片。
- `conversation`：会话与消息。
- `prompt`：提示词模板。
- `model`：模型配置。
- `retrieval`：检索与 RAG。
- `evaluation`：回答评价与质量评估。
- `log`：模型调用日志和 Token 统计。
