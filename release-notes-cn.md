# Claude Code 版本发布说明
*注意：原始发布说明中未提供发布日期*

## 版本 1.0.111 - 模型验证与语法解析修复

• /model 命令现在会验证提供的模型名称

• 修复了由格式错误的 shell 语法解析导致的 Bash 工具崩溃问题

## 版本 1.0.110 - 终端支持与 OAuth 改进
• /terminal-setup 命令现在支持 WezTerm

• MCP：OAuth 令牌现在会在过期前主动刷新

• 修复了后台 Bash 进程的可靠性问题

## 版本 1.0.109 - SDK 消息流支持
• SDK：通过 `--include-partial-messages` CLI 标志添加了部分消息流支持

## 版本 1.0.106 - Windows 路径权限修复
• Windows：修复了路径权限匹配，统一使用 POSIX 格式（例如 `Read(//c/Users/...)`）

## 版本 1.0.97 - 权限规则验证
• 设置：/doctor 现在验证权限规则语法并提供修正建议

## 版本 1.0.94 - Vertex 支持与内存管理改进
• Vertex：为支持的模型添加了全局端点支持

• /memory 命令现在允许直接编辑所有导入的内存文件

• SDK：添加自定义工具作为回调

• 添加了 /todos 命令来列出当前的待办事项

## 版本 1.0.93 - Windows 剪贴板与代理支持
• Windows：添加 Alt + V 快捷键用于从剪贴板粘贴图片

• 支持 NO_PROXY 环境变量来为指定的主机名和 IP 绕过代理

## 版本 1.0.90 - 实时设置更新
• 设置文件更改会立即生效 - 无需重启

## 版本 1.0.88 - OAuth 修复与模型控制
• 修复了导致"OAuth authentication is currently not supported"的问题

• 状态栏输入现在包含 `exceeds_200k_tokens`

• 修复了 /cost 中的错误使用跟踪

• 引入了 `ANTHROPIC_DEFAULT_SONNET_MODEL` 和 `ANTHROPIC_DEFAULT_OPUS_MODEL` 来控制模型别名 opusplan、opus 和 sonnet

• Bedrock：将默认 Sonnet 模型更新为 Sonnet 4

## 版本 1.0.86 - 上下文调试与 SDK 改进
• 添加了 /context 来帮助用户自助调试上下文问题

• SDK：为所有 SDK 消息添加了 UUID 支持

• SDK：添加了 `--replay-user-messages` 来将用户消息重放到 stdout

## 版本 1.0.85 - 成本信息与会话钩子
• 状态栏输入现在包含会话成本信息

• 钩子：引入了 SessionEnd 钩子

## 版本 1.0.84 - 网络稳定性与实时引导修复
• 修复了网络不稳定时的 tool_use/tool_result id 不匹配错误

• 修复了 Claude 在完成任务时有时忽略实时引导的问题

• @-mention：添加 ~/.claude/\* 文件到建议中，以便更容易编辑代理、输出样式和斜杠命令

• 使用内置 ripgrep 作为默认选项；要退出此行为，请设置 USE_BUILTIN_RIPGREP=0

## 版本 1.0.83 - 文件提及与动画改进
• @-mention：支持路径中包含空格的文件

• 新的闪烁加载动画

## 版本 1.0.82 - SDK 取消与设置验证
• SDK：添加请求取消支持

• SDK：新的 additionalDirectories 选项来搜索自定义路径，改进了斜杠命令处理

• 设置：验证防止 .claude/settings.json 文件中的无效字段

• MCP：改进工具名称一致性

• Bash：修复了 Claude 尝试自动读取大文件时的崩溃

## 版本 1.0.81 - 输出样式发布
• 发布了输出样式，包括新的内置教育输出样式"解释性"和"学习"。文档：https://docs.anthropic.com/en/docs/claude-code/output-styles

• 代理：修复了当代理文件无法解析时的自定义代理加载

## 版本 1.0.80 - UI 改进
• UI 改进：修复了自定义子代理颜色的文本对比度和加载动画渲染问题

## 版本 1.0.77 - Bash 工具与会话支持
• Bash 工具：修复 heredoc 和多行字符串转义，改进 stderr 重定向处理

• SDK：添加会话支持和权限拒绝跟踪

• 修复了对话摘要中的令牌限制错误

• Opus 计划模式：在 `/model` 中新设置，仅在计划模式下运行 Opus，否则运行 Sonnet

## 版本 1.0.73 - MCP 多配置与 Bash 改进
• MCP：支持使用 `--mcp-config file1.json file2.json` 的多个配置文件

• MCP：按 Esc 键取消 OAuth 认证流程

• Bash：改进了命令验证并减少了错误的安全警告

• UI：增强了加载动画和状态栏视觉层次

• Linux：添加了对 Alpine 和基于 musl 的发行版的支持（需要单独安装 ripgrep）

## 版本 1.0.72 - 权限请求
• 询问权限：让 Claude Code 始终请求确认使用特定工具，使用 /permissions

## 版本 1.0.71 - 后台命令与状态栏
• 后台命令：(Ctrl-b) 在后台运行任何 Bash 命令，这样 Claude 可以继续工作（非常适合开发服务器、跟踪日志等）

• 可自定义状态栏：使用 /statusline 将您的终端提示添加到 Claude Code

## 版本 1.0.70 - 性能优化与 Windows 修复
• 性能：优化了消息渲染以提高大上下文的性能

• Windows：修复了原生文件搜索、ripgrep 和子代理功能

• 添加了对斜杠命令参数中 @-mentions 的支持

## 版本 1.0.69 - Opus 升级
• 将 Opus 升级到 4.1 版本

## 版本 1.0.68 - 模型名称修复与 Windows 改进
• 修复了某些命令（如 `/pr-comments`）使用错误模型名称的问题

• Windows：改进了允许/拒绝工具和项目信任的权限检查。这可能会在 `.claude.json` 中创建新的项目条目 - 如果需要，请手动合并历史记录字段

• Windows：改进了子进程生成，消除了运行 pnpm 等命令时的"No such file or directory"错误

• 使用 CLAUDE.md 和 MCP 工具上下文增强了 /doctor 命令，用于自助调试

• SDK：添加了 canUseTool 回调支持，用于工具确认

• 添加了 `disableAllHooks` 设置

• 改进了大型仓库中文件建议的性能

## 版本 1.0.65 - IDE 连接与 Windows 环境
• IDE：修复了诊断的连接稳定性问题和错误处理

• Windows：为没有 .bashrc 文件的用户修复了 shell 环境设置

## 版本 1.0.64 - 代理模型自定义与钩子改进
• 代理：添加了模型自定义支持 - 现在可以指定代理应使用哪个模型

• 代理：修复了对递归代理工具的意外访问

• 钩子：在钩子 JSON 输出中添加了 systemMessage 字段，用于显示警告和上下文

• SDK：修复了多轮对话中的用户输入跟踪

• 将隐藏文件添加到文件搜索和 @-mention 建议中

## 版本 1.0.63 - Windows 功能修复
• Windows：修复了文件搜索、@agent mentions 和自定义斜杠命令功能

## 版本 1.0.62 - 代理提及与钩子
• 添加了对自定义代理的 @-mention 支持和自动完成。@<your-custom-agent> 来调用它

• 钩子：为新会话初始化添加了 SessionStart 钩子

• /add-dir 命令现在支持目录路径的自动完成

• 改进了网络连接检查的可靠性

## 版本 1.0.61 - 转录模式与设置改进
• 转录模式 (Ctrl+R)：更改 Esc 退出转录模式而不是中断

• 设置：添加了 `--settings` 标志从 JSON 文件加载设置

• 设置：修复了作为符号链接的设置文件路径的解析

• OTEL：修复了认证更改后错误组织的报告

• 斜杠命令：修复了使用 Bash 的 allowed-tools 的权限检查

• IDE：添加了在 VSCode MacOS 中使用 ⌘+V 粘贴图片的支持

• IDE：添加了 `CLAUDE_CODE_AUTO_CONNECT_IDE=false` 来禁用 IDE 自动连接

• 添加了 `CLAUDE_CODE_SHELL_PREFIX` 来包装 Claude Code 运行的 Claude 和用户提供的 shell 命令

## 版本 1.0.60 - 自定义子代理
• 现在可以为专门任务创建自定义子代理！运行 /agents 开始使用

## 版本 1.0.59 - SDK 工具确认与钩子改进
• SDK：添加了 canUseTool 回调的工具确认支持

• SDK：允许为生成的进程指定环境

• 钩子：向钩子公开了 PermissionDecision（包括"ask"）

• 钩子：UserPromptSubmit 现在在高级 JSON 输出中支持 additionalContext

• 修复了某些指定 Opus 的 Max 用户仍会看到回退到 Sonnet 的问题

## 版本 1.0.58 - PDF 支持与 MCP 改进
• 添加了对读取 PDF 的支持

• MCP：改进了 'claude mcp list' 中的服务器健康状态显示

• 钩子：为钩子命令添加了 CLAUDE_PROJECT_DIR 环境变量

## 版本 1.0.57 - 斜杠命令模型支持
• 添加了在斜杠命令中指定模型的支持

• 改进了权限消息以帮助 Claude 理解允许的工具

• 修复：删除终端包装中 bash 输出的尾随换行符

## 版本 1.0.56 - Windows VT 模式与 WSL 修复
• Windows：在支持终端 VT 模式的 Node.js 版本上启用了 shift+tab 进行模式切换

• WSL IDE 检测的修复

• 修复了导致 awsRefreshHelper 对 .aws 目录的更改未被捕获的问题

## 版本 1.0.55 - 知识截止与系统提示
• 明确了 Opus 4 和 Sonnet 4 模型的知识截止点

• Windows：修复了 Ctrl+Z 崩溃

• SDK：添加了捕获错误日志的能力

• 添加了 --system-prompt-file 选项来在打印模式下覆盖系统提示

## 版本 1.0.54 - 钩子与自定义斜杠命令改进
• 钩子：添加了 UserPromptSubmit 钩子和当前工作目录到钩子输入

• 自定义斜杠命令：在 frontmatter 中添加了 argument-hint

• Windows：OAuth 使用端口 45454 并正确构造浏览器 URL

• Windows：模式切换现在使用 alt + m，计划模式正确渲染

• Shell：切换到内存中的 shell 快照以修复文件相关错误

## 版本 1.0.53 - MCP 服务器指令
• 添加了对 MCP 服务器指令的支持

## 版本 1.0.52 - MCP 服务器指令支持
• 添加了对 MCP 服务器指令的支持

## 版本 1.0.51 - Windows 原生支持与 Bedrock API 密钥
• 添加了对原生 Windows 的支持（需要 Git for Windows）

• 添加了通过环境变量 AWS_BEARER_TOKEN_BEDROCK 对 Bedrock API 密钥的支持

• 设置：/doctor 现在可以帮助您识别和修复无效的设置文件

• `--append-system-prompt` 现在可以在交互模式下使用，不仅仅是 --print/-p

• 将自动压缩警告阈值从 60% 增加到 80%

• 修复了处理用户目录中包含空格的 shell 快照的问题

• OTEL 资源现在包括 os.type、os.version、host.arch 和 wsl.version（如果在 Windows Subsystem for Linux 上运行）

• 自定义斜杠命令：修复了子目录中的用户级命令

• 计划模式：修复了来自子任务的被拒绝计划被丢弃的问题

## 版本 1.0.48 - 启动修复与 Bash 进度
• 修复了 v1.0.45 中应用有时在启动时冻结的错误

• 基于命令输出的最后 5 行向 Bash 工具添加了进度消息

• 为 MCP 服务器配置添加了扩展变量支持

• 将 shell 快照从 /tmp 移动到 ~/.claude 以获得更可靠的 Bash 工具调用

• 改进了 Claude Code 在 WSL 中运行时的 IDE 扩展路径处理

• 钩子：添加了 PreCompact 钩子

• Vim 模式：添加了 c、f/F、t/T

## 版本 1.0.45 - 搜索工具重新设计
• 重新设计了搜索 (Grep) 工具，具有新的工具输入参数和功能

• 禁用了笔记本文件的 IDE 差异，修复了"Timeout waiting after 1000ms"错误

• 通过强制原子写入修复了配置文件损坏问题

• 将提示输入撤销更新为 Ctrl+\_ 以避免破坏现有的 Ctrl+U 行为，匹配 zsh 的撤销快捷键

• 停止钩子：修复了 /clear 后的转录路径，修复了循环以工具调用结束时的触发

• 自定义斜杠命令：基于子目录恢复了命令名称的命名空间。例如，.claude/commands/frontend/component.md 现在是 /frontend:component，而不是 /component

## 版本 1.0.44 - 导出命令与 MCP 改进
• 新的 /export 命令让您快速导出对话以进行分享

• MCP：现在支持 resource_link 工具结果

• MCP：工具注释和工具标题现在显示在 /mcp 视图中

• 将 Ctrl+Z 更改为暂停 Claude Code。通过运行 `fg` 恢复。提示输入撤销现在是 Ctrl+U

## 版本 1.0.43 - 主题选择器修复
• 修复了主题选择器过度保存的错误

• 钩子：添加了 EPIPE 系统错误处理

## 版本 1.0.42 - 波浪号扩展
• 为 `/add-dir` 命令添加了波浪号 (`~`) 扩展支持

## 版本 1.0.41 - 钩子分离与超时
• 钩子：将停止钩子触发分为 Stop 和 SubagentStop

• 钩子：为每个命令启用了可选的超时配置

• 钩子：在钩子输入中添加了"hook_event_name"

• 修复了 MCP 工具在工具列表中显示两次的错误

• `tool_decision` 事件中 Bash 工具的新工具参数 JSON

## 版本 1.0.40 - SSL 证书修复
• 修复了如果设置了 `NODE_EXTRA_CA_CERTS` 会导致 UNABLE_TO_GET_ISSUER_CERT_LOCALLY API 连接错误的错误

## 版本 1.0.39 - Active Time 指标
• 在 OpenTelemetry 日志记录中新增了 Active Time 指标

## 版本 1.0.38 - 钩子发布
• 发布了钩子。特别感谢社区在 https://github.com/anthropics/claude-code/issues/712 中的输入。文档：https://docs.anthropic.com/en/docs/claude-code/hooks

## 版本 1.0.37 - 代理授权头移除
• 移除了通过 ANTHROPIC_AUTH_TOKEN 或 apiKeyHelper 设置 `Proxy-Authorization` 头的能力

## 版本 1.0.36 - Web 搜索日期感知
• Web 搜索现在将今天的日期纳入上下文

• 修复了 stdio MCP 服务器在退出时未正确终止的错误

## 版本 1.0.35 - MCP OAuth 发现
• 添加了对 MCP OAuth 授权服务器发现的支持

## 版本 1.0.34 - 内存泄漏修复
• 修复了导致 MaxListenersExceededWarning 消息出现的内存泄漏

## 版本 1.0.33 - 日志记录与撤销功能
• 改进了具有会话 ID 支持的日志记录功能

• 添加了提示输入撤销功能（Ctrl+Z 和 vim 'u' 命令）

• 计划模式的改进

## 版本 1.0.32 - Litellm 配置与登录方法
• 更新了 litellm 的回环配置

• 添加了 forceLoginMethod 设置来绕过登录选择屏幕

## 版本 1.0.31 - JSON 配置修复
• 修复了当文件包含无效 JSON 时 ~/.claude.json 会被重置的错误

## 版本 1.0.30 - 自定义斜杠命令增强
• 自定义斜杠命令：运行 bash 输出，@-mention 文件，使用思考关键词启用思考

• 改进了文件路径自动完成与文件名匹配

• 在 Ctrl-r 模式中添加了时间戳并修复了 Ctrl-c 处理

• 为带有管道和选择的复杂过滤器增强了 jq 正则表达式支持

## 版本 1.0.29 - CJK 字符支持
• 改进了光标导航和渲染中的 CJK 字符支持

## 版本 1.0.28 - 斜杠命令修复与性能优化
• 斜杠命令：修复历史导航期间的选择器显示

• 上传前调整图片大小以防止 API 大小限制错误

• 添加了对配置目录的 XDG_CONFIG_HOME 支持

• 内存使用的性能优化

• OpenTelemetry 日志记录中的新属性（terminal.type、language）

## 版本 1.0.27 - HTTP MCP 服务器与 OAuth
• 现在支持可流式传输的 HTTP MCP 服务器

• 远程 MCP 服务器（SSE 和 HTTP）现在支持 OAuth

• MCP 资源现在可以被 @-mentioned

• /resume 斜杠命令在 Claude Code 内切换对话

## 版本 1.0.25 - 斜杠命令与 Web 搜索改进
• 斜杠命令：将"project"和"user"前缀移动到描述中

• 斜杠命令：改进了命令发现的可靠性

• 改进了对 Ghostty 的支持

• 改进了 web 搜索的可靠性

## 版本 1.0.24 - MCP 输出与设置修复
• 改进了 /mcp 输出

• 修复了设置数组被覆盖而不是合并的错误

## 版本 1.0.23 - Python SDK 发布
• 发布了 TypeScript SDK：导入 @anthropic-ai/claude-code 开始使用

• 发布了 Python SDK：pip install claude-code-sdk 开始使用

## 版本 1.0.22 - SDK 成本重命名
• SDK：将 `total_cost` 重命名为 `total_cost_usd`

## 版本 1.0.21 - 制表符缩进与工具修复
• 改进了对制表符缩进文件的编辑

• 修复了没有匹配 tool_result 错误的 tool_use

• 修复了 stdio MCP 服务器进程在退出 Claude Code 后仍会逗留的错误

## 版本 1.0.18 - 目录支持与性能改进
• 添加了 --add-dir CLI 参数来指定额外的工作目录

• 添加了不需要 -p 标志的流式输入支持

• 改进了启动性能和会话存储性能

• 添加了 CLAUDE_BASH_MAINTAIN_PROJECT_WORKING_DIR 环境变量来冻结 bash 命令的工作目录

• 添加了详细的 MCP 服务器工具显示 (/mcp)

• MCP 认证和权限改进

• 为 MCP SSE 连接在断开时添加了自动重新连接

• 修复了出现对话框时粘贴内容丢失的问题

## 版本 1.0.17 - 子任务消息与进程标题
• 我们现在在 -p 模式下发出来自子任务的消息（查找 parent_tool_use_id 属性）

• 修复了 VS Code 差异工具被快速多次调用时的崩溃

• MCP 服务器列表 UI 改进

• 更新 Claude Code 进程标题以显示"claude"而不是"node"

## 版本 1.0.11 - Claude Pro 支持与认证改进
• Claude Code 现在也可以与 Claude Pro 订阅一起使用

• 添加了 /upgrade 以更顺畅地切换到 Claude Max 计划

• 改进了从 API 密钥和 Bedrock/Vertex/外部认证令牌的认证 UI

• 改进了 shell 配置错误处理

• 改进了压缩期间的待办事项列表处理

## 版本 1.0.10 - Markdown 表格与流式性能
• 添加了 markdown 表格支持

• 改进了流式性能

## 版本 1.0.8 - Vertex AI 与超时修复
• 修复了使用 CLOUD_ML_REGION 时的 Vertex AI 区域回退

• 将默认 otel 间隔从 1s 增加到 5s

• 修复了 MCP_TIMEOUT 和 MCP_TOOL_TIMEOUT 未被遵守的边缘情况

• 修复了搜索工具不必要地请求权限的回归

• 添加了对非英语语言触发思考的支持

• 改进了压缩 UI

## 版本 1.0.7 - 权限迁移与错误处理
• 将 /allowed-tools 重命名为 /permissions

• 将 allowedTools 和 ignorePatterns 从 .claude.json 迁移到 settings.json

• 弃用 claude config 命令，支持编辑 settings.json

• 修复了 --dangerously-skip-permissions 在 --print 模式下有时不起作用的错误

• 改进了 /install-github-app 的错误处理

• 错误修复、UI 改进和工具可靠性改进

## 版本 1.0.6 - 编辑可靠性与符号链接支持
• 改进了制表符缩进文件的编辑可靠性

• 在各处遵守 CLAUDE_CONFIG_DIR

• 减少不必要的工具权限提示

• 添加了对 @file 自动完成中符号链接的支持

• 错误修复、UI 改进和工具可靠性改进

## 版本 1.0.4 - MCP 工具错误修复
• 修复了 MCP 工具错误未被正确解析的错误

## 版本 1.0.1 - 交错思考与模型参考
• 添加了 `DISABLE_INTERLEAVED_THINKING` 给用户选择退出交错思考的选项

• 改进了模型参考以显示提供商特定的名称（Bedrock 的 Sonnet 3.7，Console 的 Sonnet 4）

• 更新了文档链接和 OAuth 过程描述

## 版本 1.0.0 - 正式发布
• Claude Code 现已正式发布

• 引入 Sonnet 4 和 Opus 4 模型