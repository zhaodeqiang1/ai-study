# 修复问题命令

用途：让 AI 修复一个问题。

```text
请读取 AGENTS.md，并按渐进加载规则执行。

使用 debug-workflow。

问题：<问题描述>
复现方式：<命令、接口、页面或日志>
目标模块：<模块路径>
不能修改：<禁止范围>

请先定位原因，再做最小修复，最后更新 changes/CHANGELOG.md。
如果涉及生产、安全、权限、数据、SQL、多个文件或多个模块，必须新增 harness-engineering/records 独立记录。
```
