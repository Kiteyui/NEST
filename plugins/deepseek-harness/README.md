# 在 DeepSeek Harness 中使用 NEST

此插件把 Harness 随附的 MCP 客户端连接到当前 Windows 用户的 NEST。需要 Windows x64 和设置里带「AI 讨论」的 NEST。

1. 解压整个 NEST 便携包，打开 `NEST.exe`，创建或打开笔记空间。在「更多工具 → 设置 → AI 讨论」打开「允许 AI 客户端连接」。
2. 在 DeepSeek Harness 侧栏打开「插件」，选择「添加插件」。在安装框填入下面的包名，使用 npm 官方源或中国大陆镜像安装。核对版本 0.2.2 并点「立即启用」。若 Harness 提示需要重启，按提示操作。[npm 包页面](https://www.npmjs.com/package/@kiteyui/nest-discussion)

   ```text
   @kiteyui/nest-discussion
   ```

3. 在常用项目里新开会话，说「用 NEST 看一下我当前打开的是哪一条，只读」。对应工具是 `mcp__nest__nest_current`。在 NEST 的「AI 讨论」设置页能看到 DeepSeek Harness 的连接状态。
4. 想开始记录时，在聊天里点名一个普通条目，或说「在 NEST 新开一个讨论，叫……」。写入后核对回答末尾的回执，或说「撤回刚才那次写入」。

连接程序由 NEST 部署到 `%LOCALAPPDATA%\NEST\bin\nest-mcp.exe`。插件通过标准输入输出连接它，讨论约定随握手提供。需要批准工具调用时，核对 `mcp__nest__` 开头的工具名后自行选择。在 Harness 的插件页停用或卸载此插件即可断开这条接入路径。要收回某一枝的写入权限，在 NEST 中收回该枝的授权。

也支持从 Git 安装。NEST 的接入说明中可复制固定提交的 Git 安装地址，子目录为 `plugins/deepseek-harness`，其中 `package.json` 的 `dsh.bundle.patch` 指向同目录的 `cordis.patch.yml`。[插件源文件](https://github.com/Kiteyui/NEST/tree/b088757e4a7249da3c68071e417d7731df9b44ce/plugins/deepseek-harness) · [DSH 打包与安装说明](https://github.com/deepseek-ai/deepseek-harness/blob/master/docs/user/develop/basic/publish.zh.md)
