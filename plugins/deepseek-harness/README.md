# 在 DeepSeek Harness 中使用 NEST

此插件把 Harness 随附的 MCP 客户端连接到当前 Windows 用户的 NEST。需要 Windows x64 和设置里带「AI 讨论」的 NEST。2026 年 11 月 25 日的配套便携版使用版本号 0.2.2。

1. 解压整个 NEST 便携包，打开 `NEST.exe`，创建或打开笔记空间。在「更多工具 → 设置 → AI 讨论」打开「允许 AI 客户端连接」。
2. 在 DeepSeek Harness 侧栏打开「插件」，选择「添加插件 → 安装第三方插件」。粘贴本目录中 `nest-discussion-0.2.2.tgz` 的 GitHub **Raw 下载地址**，确认安装 `@kiteyui/nest-discussion`，然后启用。若 Harness 提示重启，按提示操作。
3. 在常用项目里新开会话，说「用 NEST 看一下我当前打开的是哪一条，只读」。对应工具是 `mcp__nest__nest_current`。在 NEST 的「AI 讨论」设置页能看到 DeepSeek Harness 的连接状态。
4. 想开始记录时，在聊天里点名一个普通条目，或说「在 NEST 新开一个讨论，叫……」。写入后核对回答末尾的回执，或说「撤回刚才那次写入」。

连接程序由 NEST 部署到 `%LOCALAPPDATA%\NEST\bin\nest-mcp.exe`。插件通过标准输入输出连接它，讨论约定随握手提供。需要批准工具调用时，核对 `mcp__nest__` 开头的工具名后自行选择。在 Harness 的插件页停用或卸载此插件即可断开这条接入路径。要收回某一枝的写入权限，在 NEST 中收回该枝的授权。
