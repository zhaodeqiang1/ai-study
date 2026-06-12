# RuoYi Vue 前端技能

## 适用场景

当任务涉及 `ruoyi-ui`、Vue 页面、前端 API、路由、菜单、权限按钮时读取本文件。

## 目录规则

- API 放在 `ruoyi-ui/src/api/<module>`。
- 页面放在 `ruoyi-ui/src/views/<module>`。
- 组件只在多页面复用时抽取。
- 不把业务请求直接写在页面深层逻辑中。

## 页面要求

后台管理页面应保持清晰、紧凑、可扫描：

- 查询区域。
- 表格区域。
- 分页。
- 新增、编辑、删除按钮。
- 加载态。
- 空状态。
- 错误提示。

## 权限

按钮权限应与后端权限标识一致。

例如：

```text
harness:knowledge:add
harness:knowledge:edit
harness:knowledge:remove
```

## AI 页面额外要求

会话类页面需要考虑：

- 流式输出状态。
- 取消生成。
- 引用来源展示。
- 用户反馈。
- 错误重试。
