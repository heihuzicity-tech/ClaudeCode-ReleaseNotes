# Claude Code 发布说明

*注：原始记录中未提供发布日期*

## 版本 1.0.106 - Windows路径权限匹配修复

• Windows：修复路径权限匹配，现在统一使用POSIX格式（例如：`Read(//c/Users/...)`）

## 版本 1.0.97 - 权限规则验证增强

• 设置：/doctor 现在验证权限规则语法并建议更正

## 版本 1.0.94 - Vertex全局端点与待办事项功能

• Vertex：为支持的模型添加对全局端点的支持

• /memory 命令现在允许直接编辑所有导入的内存文件

• SDK：将自定义工具添加为回调

• 添加了 /todos 命令以列出当前待办事项

## 版本 1.0.93 - Windows剪贴板与代理支持

• Windows：添加 Alt + V 快捷键用于从剪贴板粘贴图片

• 支持 NO_PROXY 环境变量以绕过指定主机名和IP的代理

## 版本 1.0.90 - 设置即时生效

• 设置文件更改立即生效 - 无需重启

## 版本 1.0.88 - OAuth 认证修复与模型配置增强

• 修复了导致"当前不支持OAuth认证"的问题

• 状态行输入现在包括 `exceeds_200k_tokens`

• 修复了 /cost 中不正确的使用跟踪

• 引入了 `ANTHROPIC_DEFAULT_SONNET_MODEL` 和 `ANTHROPIC_DEFAULT_OPUS_MODEL` 用于控制模型别名 opusplan、opus 和 sonnet

• Bedrock：将默认 Sonnet 模型更新为 Sonnet 4

## 版本 1.0.86 - 上下文调试与SDK增强
• 添加了 /context 帮助用户自助调试上下文问题

• SDK：为所有SDK消息添加了UUID支持

• SDK：添加了 `--replay-user-messages` 将用户消息重播回 stdout

## 版本 1.0.85 - 会话成本信息与钩子
• 状态行输入现在包括会话成本信息

• 钩子：引入了 SessionEnd 钩子

## 版本 1.0.84 - 网络稳定性与实时引导改进
• 修复了网络不稳定时 tool_use/tool_result id 不匹配错误

• 修复了 Claude 在完成任务时有时忽略实时引导的问题

• @提及：将 ~/.claude/\* 文件添加到建议中，以便更容易编辑代理、输出样式和斜杠命令

• 默认使用内置 ripgrep；要选择退出此行为，请设置 USE_BUILTIN_RIPGREP=0

## 版本 1.0.83 - 路径处理与UI改进
• @提及：支持路径中包含空格的文件

• 新的闪烁旋转器

## 版本 1.0.82 - SDK与设置增强
• SDK：添加请求取消支持

• SDK：新的 additionalDirectories 选项用于搜索自定义路径，改进了斜杠命令处理

• 设置：验证防止 .claude/settings.json 文件中出现无效字段

• MCP：改进工具名称一致性

• Bash：修复了 Claude 尝试自动读取大文件时的崩溃

## 版本 1.0.81 - 输出样式与代理修复
• 发布了输出样式，包括新的内置教育输出样式"解释性"和"学习"。文档：https://docs.anthropic.com/en/docs/claude-code/output-styles

• 代理：修复了代理文件无法解析时的自定义代理加载

## 版本 1.0.80 - UI改进
• UI改进：修复了自定义子代理颜色的文本对比度和旋转器渲染问题

## 版本 1.0.77 - Bash工具与Opus计划模式
• Bash 工具：修复 heredoc 和多行字符串转义，改进 stderr 重定向处理

• SDK：添加会话支持和权限拒绝跟踪

• 修复会话摘要中的令牌限制错误

• Opus 计划模式：/model 中的新设置，仅在计划模式下运行 Opus，否则运行 Sonnet

## 版本 1.0.73 - MCP配置与Linux支持
• MCP：支持多个配置文件，使用 `--mcp-config file1.json file2.json`

• MCP：按 Esc 取消 OAuth 认证流程

• Bash：改进的命令验证和减少误报安全警告

• UI：增强的旋转器动画和状态行视觉层次

• Linux：添加了对 Alpine 和基于 musl 的发行版的支持（需要单独安装 ripgrep）

## 版本 1.0.72 - 权限管理
• 询问权限：使用 /permissions 让 Claude Code 始终请求确认使用特定工具

## 版本 1.0.71 - 后台命令与状态行自定义
• 后台命令：(Ctrl-b) 在后台运行任何 Bash 命令，以便 Claude 可以继续工作（非常适合开发服务器、跟踪日志等）

• 可自定义的状态行：使用 /statusline 将您的终端提示添加到 Claude Code

## 版本 1.0.70 - 性能优化与Windows修复
• 性能：优化了消息渲染以获得更好的大上下文性能

• Windows：修复了本机文件搜索、ripgrep 和子代理功能

• 添加了对斜杠命令参数中 @提及的支持

## 版本 1.0.69 - Opus升级
• 将 Opus 升级到 4.1 版本

## 版本 1.0.68 - Windows改进与调试增强
• 修复了某些命令（如 `/pr-comments`）使用不正确的模型名称

• Windows：改进了允许/拒绝工具和项目信任的权限检查。这可能会在 `.claude.json` 中创建新的项目条目 - 如需要请手动合并历史字段

• Windows：改进子进程生成，消除运行 pnpm 等命令时的"没有此文件或目录"错误

• 使用 CLAUDE.md 和 MCP 工具上下文增强了 /doctor 命令，用于自助调试

• SDK：添加了用于工具确认的 canUseTool 回调支持

• 添加了 `disableAllHooks` 设置

• 改进了大型仓库中的文件建议性能

## 版本 1.0.65 - IDE连接稳定性
• IDE：修复了连接稳定性问题和诊断的错误处理

• Windows：修复了没有 .bashrc 文件的用户的 shell 环境设置

## 版本 1.0.64 - 代理模型自定义
• 代理：添加了模型自定义支持 - 您现在可以指定代理应使用哪个模型

• 代理：修复了对递归代理工具的意外访问

• 钩子：向钩子 JSON 输出添加了 systemMessage 字段，用于显示警告和上下文

• SDK：修复了跨多轮对话的用户输入跟踪

• 将隐藏文件添加到文件搜索和 @提及建议中

## 版本 1.0.63 - Windows功能修复
• Windows：修复了文件搜索、@代理提及和自定义斜杠命令功能

## 版本 1.0.62 - @提及支持增强
• 为自定义代理添加了带有类型提前的 @提及支持。使用 @<your-custom-agent> 调用它

• 钩子：为新会话初始化添加了 SessionStart 钩子

• /add-dir 命令现在支持目录路径的类型提前

• 改进了网络连接检查的可靠性

## 版本 1.0.61 - 转录模式与设置增强
• 转录模式 (Ctrl+R)：将 Esc 更改为退出转录模式而不是中断

• 设置：添加了 `--settings` 标志以从 JSON 文件加载设置

• 设置：修复了作为符号链接的设置文件路径的解析

• OTEL：修复了身份验证更改后报告错误组织的问题

• 斜杠命令：修复了带有 Bash 的允许工具的权限检查

• IDE：添加了在 VSCode MacOS 中使用 ⌘+V 粘贴图像的支持

• IDE：添加了 `CLAUDE_CODE_AUTO_CONNECT_IDE=false` 用于禁用 IDE 自动连接

• 添加了 `CLAUDE_CODE_SHELL_PREFIX` 用于包装 Claude 和用户提供的由 Claude Code 运行的 shell 命令

## 版本 1.0.60 - 自定义子代理
• 您现在可以为专门任务创建自定义子代理！运行 /agents 开始

## 版本 1.0.59 - SDK工具确认
• SDK：使用 canUseTool 回调添加了工具确认支持

• SDK：允许为生成的进程指定环境

• 钩子：向钩子公开 PermissionDecision（包括"询问"）

• 钩子：UserPromptSubmit 现在在高级 JSON 输出中支持 additionalContext

• 修复了某些指定 Opus 的 Max 用户仍会看到回退到 Sonnet 的问题

## 版本 1.0.58 - PDF支持
• 添加了对阅读 PDF 的支持

• MCP：改进了'claude mcp list'中的服务器健康状态显示

• 钩子：为钩子命令添加了 CLAUDE_PROJECT_DIR 环境变量

## 版本 1.0.57 - 斜杠命令模型指定
• 添加了在斜杠命令中指定模型的支持

• 改进了权限消息以帮助 Claude 理解允许的工具

• 修复：从终端包装的 bash 输出中删除尾随换行符

## 版本 1.0.56 - Windows改进
• Windows：在支持终端 VT 模式的 Node.js 版本上启用 shift+tab 进行模式切换

• 修复了 WSL IDE 检测

• 修复了导致 awsRefreshHelper 对 .aws 目录的更改未被检测到的问题

## 版本 1.0.55 - 知识截止日期澄清
• 澄清了 Opus 4 和 Sonnet 4 模型的知识截止日期

• Windows：修复了 Ctrl+Z 崩溃

• SDK：添加了捕获错误日志的能力

• 添加 --system-prompt-file 选项以在打印模式下覆盖系统提示

## 版本 1.0.54 - 钩子与Windows改进
• 钩子：向钩子输入添加了 UserPromptSubmit 钩子和当前工作目录

• 自定义斜杠命令：向前置内容添加了参数提示

• Windows：OAuth 使用端口 45454 并正确构建浏览器 URL

• Windows：模式切换现在使用 alt + m，计划模式正确渲染

• Shell：切换到内存中的 shell 快照以修复与文件相关的错误

## 版本 1.0.53 - @提及与AWS支持
• 将 @提及文件截断从 100 行更新到 2000 行

• 为 AWS 令牌刷新添加帮助脚本设置：awsAuthRefresh（用于前台操作，如 aws sso login）和 awsCredentialExport（用于带有类似 STS 响应的后台操作）

## 版本 1.0.52 - MCP服务器说明
• 添加了对 MCP 服务器说明的支持

## 版本 1.0.51 - 原生Windows支持
• 添加了对原生 Windows 的支持（需要 Git for Windows）

• 通过环境变量 AWS_BEARER_TOKEN_BEDROCK 添加了对 Bedrock API 密钥的支持

• 设置：/doctor 现在可以帮助您识别和修复无效的设置文件

• `--append-system-prompt` 现在可以在交互模式中使用，而不仅仅是 --print/-p

• 将自动压缩警告阈值从 60% 增加到 80%

• 修复了处理带有空格的用户目录进行 shell 快照的问题

• OTEL 资源现在包括 os.type、os.version、host.arch 和 wsl.version（如果在 Windows 子系统 Linux 上运行）

• 自定义斜杠命令：修复了子目录中的用户级命令

• 计划模式：修复了从子任务拒绝的计划会被丢弃的问题

## 版本 1.0.48 - 启动问题修复
• 修复了 v1.0.45 中应用程序有时会在启动时冻结的错误

• 根据命令输出的最后 5 行向 Bash 工具添加了进度消息

• 为 MCP 服务器配置添加了扩展变量支持

• 将 shell 快照从 /tmp 移动到 ~/.claude 以获得更可靠的 Bash 工具调用

• 改进了 Claude Code 在 WSL 中运行时的 IDE 扩展路径处理

• 钩子：添加了 PreCompact 钩子

• Vim 模式：添加了 c、f/F、t/T

## 版本 1.0.45 - 搜索工具重新设计
• 重新设计的搜索（Grep）工具，具有新的工具输入参数和功能

• 为笔记本文件禁用 IDE 差异，修复了"1000ms 后超时等待"错误

• 通过强制原子写入修复了配置文件损坏问题

• 将提示输入撤消更新为 Ctrl+\_ 以避免破坏现有的 Ctrl+U 行为，匹配 zsh 的撤消快捷键

• 停止钩子：修复了 /clear 后的转录路径，并修复了循环以工具调用结束时的触发

• 自定义斜杠命令：基于子目录恢复了命令名称中的命名空间。例如，.claude/commands/frontend/component.md 现在是 /frontend:component，而不是 /component

## 版本 1.0.44 - 导出功能
• 新的 /export 命令让您快速导出对话进行分享

• MCP：现在支持 resource_link 工具结果

• MCP：工具注释和工具标题现在显示在 /mcp 视图中

• 将 Ctrl+Z 更改为暂停 Claude Code。通过运行 `fg` 恢复。提示输入撤消现在是 Ctrl+U

## 版本 1.0.43 - 主题选择器修复
• 修复了主题选择器过度保存的错误

• 钩子：添加了 EPIPE 系统错误处理

## 版本 1.0.42 - 波浪号扩展
• 向 `/add-dir` 命令添加了波浪号（`~`）扩展支持

## 版本 1.0.41 - 钩子增强
• 钩子：将停止钩子触发拆分为 Stop 和 SubagentStop

• 钩子：为每个命令启用了可选的超时配置

• 钩子：向钩子输入添加了"hook_event_name"

• 修复了 MCP 工具在工具列表中显示两次的错误

• `tool_decision` 事件中 Bash 工具的新工具参数 JSON

## 版本 1.0.40 - 证书问题修复
• 修复了如果设置了 `NODE_EXTRA_CA_CERTS` 导致 UNABLE_TO_GET_ISSUER_CERT_LOCALLY 的 API 连接错误

## 版本 1.0.39 - 活动时间指标
• OpenTelemetry 日志中的新活动时间指标

## 版本 1.0.38 - 钩子发布
• 发布了钩子。特别感谢 https://github.com/anthropics/claude-code/issues/712 中的社区意见。文档：https://docs.anthropic.com/en/docs/claude-code/hooks

## 版本 1.0.37 - 安全更新
• 删除了通过 ANTHROPIC_AUTH_TOKEN 或 apiKeyHelper 设置 `Proxy-Authorization` 标头的能力

## 版本 1.0.36 - Web搜索增强
• Web 搜索现在会考虑今天的日期

• 修复了 stdio MCP 服务器在退出时未正确终止的错误

## 版本 1.0.35 - OAuth支持
• 添加了对 MCP OAuth 授权服务器发现的支持

## 版本 1.0.34 - 内存泄漏修复
• 修复了导致出现 MaxListenersExceededWarning 消息的内存泄漏

## 版本 1.0.33 - 日志功能改进
• 改进了带有会话 ID 支持的日志功能

• 添加了提示输入撤消功能（Ctrl+Z 和 vim 'u' 命令）

• 计划模式的改进

## 版本 1.0.32 - 登录方法配置
• 更新了 litellm 的环回配置

• 添加了 forceLoginMethod 设置以绕过登录选择屏幕

## 版本 1.0.31 - JSON配置修复
• 修复了当文件包含无效 JSON 时 ~/.claude.json 被重置的错误

## 版本 1.0.30 - 自定义斜杠命令增强
• 自定义斜杠命令：运行 bash 输出，@提及文件，使用思考关键字启用思考

• 使用文件名匹配改进了文件路径自动完成

• 在 Ctrl-r 模式下添加了时间戳并修复了 Ctrl-c 处理

• 增强了对带有管道和选择的复杂过滤器的 jq 正则表达式支持

## 版本 1.0.29 - CJK字符支持
• 改进了光标导航和渲染中的 CJK 字符支持

## 版本 1.0.28 - 性能优化
• 斜杠命令：修复历史导航期间的选择器显示

• 上传前调整图像大小以防止 API 大小限制错误

• 向配置目录添加了 XDG_CONFIG_HOME 支持

• 内存使用的性能优化

• OpenTelemetry 日志中的新属性（terminal.type、language）

## 版本 1.0.27 - MCP增强
• 现在支持可流式传输的 HTTP MCP 服务器

• 远程 MCP 服务器（SSE 和 HTTP）现在支持 OAuth

• MCP 资源现在可以被 @提及

• /resume 斜杠命令用于在 Claude Code 中切换对话

## 版本 1.0.25 - 斜杠命令改进
• 斜杠命令：将"project"和"user"前缀移动到描述中

• 斜杠命令：改进了命令发现的可靠性

• 改进了对 Ghostty 的支持

• 改进了 web 搜索的可靠性

## 版本 1.0.24 - MCP输出改进
• 改进了 /mcp 输出

• 修复了设置数组被覆盖而不是合并的错误

## 版本 1.0.23 - Python SDK发布
• 发布了 Python SDK：pip install claude-code-sdk 开始使用

## 版本 1.0.22 - SDK成本重命名
• SDK：将 `total_cost` 重命名为 `total_cost_usd`

## 版本 1.0.21 - Tab缩进编辑改进
• 改进了基于制表符缩进的文件编辑

• 修复了没有匹配 tool_result 的 tool_use 错误

• 修复了退出 Claude Code 后 stdio MCP 服务器进程会滞留的错误

## 版本 1.0.18 - 多目录支持
• 添加了 --add-dir CLI 参数用于指定额外的工作目录

• 添加了流式输入支持，无需 -p 标志

• 改进了启动性能和会话存储性能

• 添加了 CLAUDE_BASH_MAINTAIN_PROJECT_WORKING_DIR 环境变量以冻结 bash 命令的工作目录

• 添加了详细的 MCP 服务器工具显示（/mcp）

• MCP 身份验证和权限改进

• 为 MCP SSE 连接添加了断开时的自动重新连接

• 修复了出现对话框时粘贴内容丢失的问题

## 版本 1.0.17 - 子任务消息
• 我们现在在 -p 模式下发出子任务的消息（查找 parent_tool_use_id 属性）

• 修复了快速多次调用 VS Code 差异工具时的崩溃

• MCP 服务器列表 UI 改进

• 将 Claude Code 进程标题更新为显示"claude"而不是"node"

## 版本 1.0.11 - Claude Pro支持
• Claude Code 现在也可以与 Claude Pro 订阅一起使用

• 添加了 /upgrade 以更顺畅地切换到 Claude Max 计划

• 改进了来自 API 密钥和 Bedrock/Vertex/外部身份验证令牌的身份验证 UI

• 改进了 shell 配置错误处理

• 改进了压缩期间的待办事项列表处理

## 版本 1.0.10 - Markdown表格支持
• 添加了 markdown 表格支持

• 改进了流式传输性能

## 版本 1.0.8 - 各种修复
• 修复了使用 CLOUD_ML_REGION 时的 Vertex AI 区域回退

• 将默认 otel 间隔从 1s 增加到 5s

• 修复了 MCP_TIMEOUT 和 MCP_TOOL_TIMEOUT 未被尊重的边缘情况

• 修复了搜索工具不必要地请求权限的回归

• 添加了对触发非英语思考的支持

• 改进了压缩 UI

## 版本 1.0.7 - 权限重命名
• 将 /allowed-tools 重命名为 /permissions

• 将 allowedTools 和 ignorePatterns 从 .claude.json 迁移到 settings.json

• 弃用了 claude 配置命令，转而编辑 settings.json

• 修复了 --dangerously-skip-permissions 有时在 --print 模式下不起作用的错误

• 改进了 /install-github-app 的错误处理

• 错误修复、UI 改进和工具可靠性改进

## 版本 1.0.6 - 编辑可靠性
• 改进了制表符缩进文件的编辑可靠性

• 在所有地方都遵守 CLAUDE_CONFIG_DIR

• 减少了不必要的工具权限提示

• 添加了对 @file 类型提前中符号链接的支持

• 错误修复、UI 改进和工具可靠性改进

## 版本 1.0.4 - MCP工具错误修复
• 修复了 MCP 工具错误未正确解析的错误

## 版本 1.0.1 - 交错思考选项
• 添加了 `DISABLE_INTERLEAVED_THINKING` 让用户选择退出交错思考

• 改进了模型引用以显示特定于提供商的名称（Bedrock 的 Sonnet 3.7，控制台的 Sonnet 4）

• 更新了文档链接和 OAuth 过程描述

## 版本 1.0.0 - 正式发布
• Claude Code 现已正式发布

• 引入 Sonnet 4 和 Opus 4 模型

## 版本 0.2.125 - Bedrock ARN格式更改
• 重大更改：传递给 `ANTHROPIC_MODEL` 或 `ANTHROPIC_SMALL_FAST_MODEL` 的 Bedrock ARN 不应再包含转义斜杠（指定 `/` 而不是 `%2F`）

• 删除了 `DEBUG=true`，改用 `ANTHROPIC_LOG=debug` 来记录所有请求

## 版本 0.2.117 - JSON输出格式更改
• 重大更改：--print JSON 输出现在返回嵌套消息对象，以便在引入新元数据字段时向前兼容

• 引入了 settings.cleanupPeriodDays

• 引入了 CLAUDE_CODE_API_KEY_HELPER_TTL_MS 环境变量

• 引入了 --debug 模式

## 版本 0.2.108 - 实时引导
• 您现在可以在 Claude 工作时向 Claude 发送消息以实时引导 Claude

• 引入了 BASH_DEFAULT_TIMEOUT_MS 和 BASH_MAX_TIMEOUT_MS 环境变量

• 修复了思考在 -p 模式下不工作的错误

• 修复了 /cost 报告中的回归

• 弃用了 MCP 向导界面，转而使用其他 MCP 命令

• 许多其他错误修复和改进

## 版本 0.2.107 - CLAUDE.md文件导入
• CLAUDE.md 文件现在可以导入其他文件。将 @path/to/file.md 添加到 ./CLAUDE.md 以在启动时加载其他文件

## 版本 0.2.106 - MCP SSE服务器配置
• MCP SSE 服务器配置现在可以指定自定义标头

• 修复了 MCP 权限提示并不总是正确显示的错误

## 版本 0.2.105 - Web搜索
• Claude 现在可以搜索网络

• 将系统和帐户状态移至 /status

• 为 Vim 添加了单词移动键绑定

• 改进了启动、待办工具和文件编辑的延迟

## 版本 0.2.102 - 思考触发改进
• 改进了思考触发的可靠性

• 改进了图像和文件夹 @提及的可靠性

• 您现在可以将多个大块粘贴到一个提示中

## 版本 0.2.100 - 栈溢出修复
• 修复了栈溢出错误导致的崩溃

• 使数据库存储可选；缺少数据库支持会禁用 --continue 和 --resume

## 版本 0.2.98 - 自动压缩修复
• 修复了自动压缩运行两次的问题

## 版本 0.2.96 - Claude Max订阅支持
• Claude Code 现在也可以与 Claude Max 订阅一起使用 (https://claude.ai/upgrade)

## 版本 0.2.93 - 会话恢复与待办列表
• 使用"claude --continue"和"claude --resume"从中断的地方恢复对话

• Claude 现在可以访问待办事项列表，帮助它保持正轨并更有组织

## 版本 0.2.82 - 工具重命名
• 添加了对 --disallowedTools 的支持

• 为了一致性重命名了工具：LSTool -> LS，View -> Read 等

## 版本 0.2.75 - 交互增强
• 在 Claude 工作时按 Enter 排队额外的消息

• 直接将图像文件拖入或复制/粘贴到提示中

• @提及文件以直接将它们添加到上下文

• 使用 `claude --mcp-config <path-to-file>` 运行一次性 MCP 服务器

• 改进了文件名自动完成的性能

## 版本 0.2.74 - API密钥刷新
• 添加了对刷新动态生成的 API 密钥（通过 apiKeyHelper）的支持，TTL 为 5 分钟

• 任务工具现在可以执行写入和运行 bash 命令

## 版本 0.2.72 - 旋转器更新
• 更新了旋转器以指示加载的令牌和工具使用

## 版本 0.2.70 - 网络命令支持
• 像 curl 这样的网络命令现在可供 Claude 使用

• Claude 现在可以并行运行多个 web 查询

• 在自动接受模式下按一次 ESC 立即中断 Claude

## 版本 0.2.69 - UI修复
• 通过改进的选择组件行为修复了 UI 故障

• 通过更好的文本截断逻辑增强了终端输出显示

## 版本 0.2.67 - 共享项目权限
• 共享项目权限规则可以保存在 .claude/settings.json 中

## 版本 0.2.66 - 打印模式流输出
• 打印模式 (-p) 现在通过 --output-format=stream-json 支持流输出

• 修复了粘贴可能意外触发内存或 bash 模式的问题

## 版本 0.2.63 - MCP工具加载修复
• 修复了 MCP 工具加载两次导致工具调用错误的问题

## 版本 0.2.61 - 导航增强
• 使用 vim 风格的键（j/k）或 bash/emacs 快捷键（Ctrl+n/p）导航菜单以获得更快的交互

• 增强了图像检测以获得更可靠的剪贴板粘贴功能

• 修复了 ESC 键可能导致对话历史选择器崩溃的问题

## 版本 0.2.59 - 图像粘贴
• 直接将图像复制粘贴到您的提示中

• 改进了 bash 和 fetch 工具的进度指示器

• 非交互模式 (-p) 的错误修复

## 版本 0.2.54 - 内存功能
• 通过以'#'开始您的消息快速添加到内存

• 按 ctrl+r 查看长工具结果的完整输出

• 添加了对 MCP SSE 传输的支持

## 版本 0.2.53 - Web获取工具
• 新的 web 获取工具让 Claude 查看您粘贴的 URL

• 修复了 JPEG 检测的错误

## 版本 0.2.50 - MCP项目范围
• 新的 MCP"项目"范围现在允许您将 MCP 服务器添加到 .mcp.json 文件并将它们提交到您的存储库

## 版本 0.2.49 - MCP范围重命名
• 先前的 MCP 服务器范围已重命名：先前的"项目"范围现在是"本地"，"全局"范围现在是"用户"

## 版本 0.2.47 - 自动完成与压缩
• 按 Tab 自动完成文件和文件夹名称

• 按 Shift + Tab 切换文件编辑的自动接受

• 无限对话长度的自动对话压缩（使用 /config 切换）

## 版本 0.2.44 - 思考模式
• 使用思考模式让 Claude 制定计划：只需说"思考"或"深入思考"甚至"超级思考"

## 版本 0.2.41 - MCP服务器配置
• MCP 服务器启动超时现在可以通过 MCP_TIMEOUT 环境变量配置

• MCP 服务器启动不再阻止应用程序启动

## 版本 0.2.37 - 发布说明命令
• 新的 /release-notes 命令让您随时查看发布说明

• `claude config add/remove` 命令现在接受用逗号或空格分隔的多个值

## 版本 0.2.36 - MCP导入
• 使用 `claude mcp add-from-claude-desktop` 从 Claude Desktop 导入 MCP 服务器

• 使用 `claude mcp add-json <n> <json>` 将 MCP 服务器添加为 JSON 字符串

## 版本 0.2.34 - Vim绑定
• 文本输入的 Vim 绑定 - 使用 /vim 或 /config 启用

## 版本 0.2.32 - MCP设置向导
• 交互式 MCP 设置向导：运行"claude mcp add"以使用分步界面添加 MCP 服务器

• 修复了一些 PersistentShell 问题

## 版本 0.2.31 - 自定义斜杠命令
• 自定义斜杠命令：.claude/commands/ 目录中的 Markdown 文件现在作为自定义斜杠命令出现，用于将提示插入到您的对话中

• MCP 调试模式：使用 --mcp-debug 标志运行以获取有关 MCP 服务器错误的更多信息

## 版本 0.2.30 - ANSI颜色主题
• 添加了 ANSI 颜色主题以获得更好的终端兼容性

• 修复了斜杠命令参数未正确发送的问题

•（仅限 Mac）API 密钥现在存储在 macOS 钥匙串中

## 版本 0.2.26 - 工具权限管理
• 新的 /approved-tools 命令用于管理工具权限

• 单词级差异显示以提高代码可读性

• 斜杠命令的模糊匹配

## 版本 0.2.21 - 模糊匹配
• /commands 的模糊匹配
