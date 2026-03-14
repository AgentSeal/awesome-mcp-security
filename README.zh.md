# 🛡️ MCP 服务器安全注册表

> 已扫描并分析 **764 个 MCP 服务器**的 AI 代理安全风险。
> 分数反映 AI 代理使用该服务器的安全程度，而非服务器本身的代码质量。
> 每日更新。由 [AgentSeal](https://agentseal.org) 提供支持。

[English](README.md) · **中文** · [日本語](README.ja.md) · [한국어](README.ko.md)

## 快速统计

| 指标 | 数量 |
|------|------|
| 已扫描服务器总数 | **764** |
| ✅ 安全 (分数 ≥ 80) | **598** |
| ⚠️ 需审查 (分数 50-79) | **166** |
| 安全发现总数 | **6098** |
| 最后更新 | 2026年3月13日 |

## 评分方式

每个服务器通过 **9 个安全分析器**进行测试：

- **Schema 分析** - 验证工具参数类型和约束
- **静态模式检测** - 发现命令注入、SSRF、路径遍历模式
- **提示注入扫描** - 检测工具描述中的隐藏指令
- **毒性流映射** - 识别危险的工具链（如：读取密钥 → 发送到外部 URL）
- **Unicode 检测** - 捕获不可见字符攻击
- **深度解剖** - 使用 45+ MCP 特定攻击模式进行主动探测
- **注释和指令分析** - 检查行为修改元数据
- **资源分析** - 评估暴露的资源和模板
- **LLM 分类** - Claude 驱动的工具意图语义分析

**信任分数：** 0-100 衡量 AI 代理使用此服务器的安全程度。
较低的分数并不意味着服务器有 bug 或是恶意的。它意味着使用该服务器的 AI 代理具有更大的攻击面（如代码执行、文件访问、网络请求），攻击者可以通过提示注入或工具投毒来利用这些攻击面。

- **安全 (>= 80)：** 攻击面小。代理可以以最小风险使用。
- **需审查 (50-79)：** 具有扩展攻击面的显著能力。需配合适当的防护措施使用。
- **有风险 (20-49)：** 攻击面大。需要严格的沙箱和人工监督。
- **危险 (< 20)：** 存在严重安全问题。不建议自动化使用。

## 图例

| 符号 | 含义 |
|------|------|
| ✅ | 安全 - AI 代理攻击面小 |
| ⚠️ | 需审查 - 功能更广泛，需配合防护措施 |
| 🟠 | 有风险 - 攻击面大，需要沙箱 |
| 🔴 | 危险 - 不建议自动化使用 |

## 分类

- [🛠️ Developer Tools](#developer-tools) (240)
- [🔍 Search & Knowledge](#search--knowledge) (59)
- [💻 Code & IDE](#code--ide) (27)
- [☁️ Cloud & Infrastructure](#cloud--infrastructure) (32)
- [📝 Content & Media](#content--media) (45)
- [🔌 API Development](#api-development) (17)
- [🗄️ Database & SQL](#database--sql) (25)
- [💬 Communication](#communication) (27)
- [⚙️ System Administration](#system-administration) (11)
- [🔒 Security & Auth](#security--auth) (40)
- [🕸️ Web Scraping & Collection](#web-scraping--collection) (23)
- [📁 File System & Storage](#file-system--storage) (13)
- [💰 Finance & Crypto](#finance--crypto) (35)
- [🧠 Data Science & ML](#data-science--ml) (17)
- [📡 IoT & Hardware](#iot--hardware) (11)

### 🛠️ <a name="developer-tools"></a>Developer Tools

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [markitdown](https://github.com/microsoft/markitdown) | 将文件和办公文档转换为 Markdown 的 Python 工具。 | 88 ✅ | 90.7k | [View](https://agentseal.org/mcp/https-githubcom-microsoft-markitdown) |
| [chrome-devtools-mcp](https://github.com/chromedevtools/chrome-devtools-mcp) | 面向编程代理的 Chrome 开发者工具 | 73 ⚠️ | 28.8k | [View](https://agentseal.org/mcp/chrome-devtools-mcp) |
| [Playwright](https://github.com/microsoft/playwright-mcp) | 使用 Playwright 为大语言模型 (LLM) 自动化浏览器交互... | 62 ⚠️ | 28.7k | [View](https://agentseal.org/mcp/https-githubcom-microsoft-playwright-mcp) |
| [GitHub](https://github.com/github/github-mcp-server) | 为 AI 代理提供与 GitHub API 的高级自动化和交互能力... | 70 ⚠️ | 27.8k | [View](https://agentseal.org/mcp/https-githubcom-github-github-mcp-server) |
| [claude-flow](https://github.com/ruvnet/claude-flow) | 企业级 AI 编排平台，用于部署具备安全保障的多代理集群... | 86 ✅ | 20.9k | [View](https://agentseal.org/mcp/https-githubcom-ruvnet-claude-flow) |
| [beads](https://github.com/steveyegge/beads) | Beads - 为你的编程代理提供记忆升级 | 86 ✅ | 18.9k | [View](https://agentseal.org/mcp/https-githubcom-steveyegge-beads) |
| [archon](https://github.com/coleam00/archon) | Archon OS 测试版 - AI 代理的知识和任务管理核心... | 92 ✅ | 13.8k | [View](https://agentseal.org/mcp/https-githubcom-coleam00-archon) |
| [mcp-go](https://github.com/mark3labs/mcp-go) | 模型上下文协议 (MCP) 的 Go 语言实现，实现无缝集成... | 89 ✅ | 8.3k | [View](https://agentseal.org/mcp/https-githubcom-mark3labs-mcp-go) |
| [git-mcp](https://github.com/idosal/git-mcp) | 终结代码幻觉！GitMCP 是一个免费、开源的远程 MCP 服务... | 78 ⚠️ | 7.8k | [View](https://agentseal.org/mcp/git-mcp) |
| [browser-tools-mcp](https://github.com/agentdeskai/browser-tools-mcp) | 直接从 Cursor 和其他兼容 MCP 的 IDE 中监控浏览器日志。 | 91 ✅ | 7.1k | [View](https://agentseal.org/mcp/https-githubcom-agentdeskai-browser-tools-mcp) |
| [cursor-talk-to-figma-mcp](https://github.com/sonnylazuardi/cursor-talk-to-figma-mcp) | MCP 集成，使 Cursor 和 Claude Code 等 AI 代理能够读取和修改 Figma 设计... | 88 ✅ | 6.5k | [View](https://agentseal.org/mcp/https-githubcom-sonnylazuardi-cursor-talk-to-figma-mcp) |
| [cursor-talk-to-figma-mcp](https://github.com/grab/cursor-talk-to-figma-mcp) | TalkToFigma：AI 代理 (Cursor、Claude Code) 与 Figma 之间的 MCP 集成... | 88 ✅ | 6.5k | [View](https://agentseal.org/mcp/https-githubcom-grab-cursor-talk-to-figma-mcp) |
| [ida-pro-mcp](https://github.com/mrexodia/ida-pro-mcp) | AI 驱动的逆向工程助手，将 IDA Pro 与语言模型连接... | 88 ✅ | 6.3k | [View](https://agentseal.org/mcp/ida-pro-mcp) |
| [mcp](https://github.com/browsermcp/mcp) | Browser MCP 是一个模型上下文提供者 (MCP) 服务器，允许 AI 应用程序与浏览器交互... | 86 ✅ | 6.0k | [View](https://agentseal.org/mcp/browsermcp-mcp) |
| [desktopcommandermcp](https://github.com/wonderwhy-er/desktopcommandermcp) | 为 Claude 提供终端控制、文件系统搜索功能的 MCP 服务器... | 63 ⚠️ | 5.7k | [View](https://agentseal.org/mcp/https-githubcom-wonderwhy-er-desktopcommandermcp) |
| [klavis](https://github.com/klavis-ai/klavis) | Klavis AI (YC X25)：让 AI 代理通过 MCP 集成平台远程使用工具... | 68 ⚠️ | 5.7k | [View](https://agentseal.org/mcp/https-githubcom-klavis-ai-klavis) |
| [praisonai](https://github.com/mervinpraison/praisonai) | PraisonAI - 你的全天候 AI 员工团队。自动化并解决复杂挑战... | 78 ⚠️ | 5.7k | [View](https://agentseal.org/mcp/https-githubcom-mervinpraison-praisonai) |
| [playwright-mcp-server](https://github.com/executeautomation/mcp-playwright) | Playwright 模型上下文协议服务器 - 用于自动化浏览器和 API 的工具... | 73 ⚠️ | 5.3k | [View](https://agentseal.org/mcp/executeautomation-playwright-mcp-server) |
| [magic](https://github.com/21st-dev/magic-mcp) | 类似 v0 但在你的 Cursor/WindSurf/Cline 中运行。21st dev Magic MCP 服务器... | 82 ✅ | 4.4k | [View](https://agentseal.org/mcp/21st-dev-magic) |
| [osaurus](https://github.com/osaurus-ai/osaurus) | 掌控你的 AI。原生 macOS AI 代理平台 - 任意模型、持久化运行... | 79 ⚠️ | 4.1k | [View](https://agentseal.org/mcp/osaurus-ai-osaurus) |
| [context-mode](https://github.com/mksglu/context-mode) | MCP 是工具访问的协议。我们是上下文的虚拟化层。 | 78 ⚠️ | 3.7k | [View](https://agentseal.org/mcp/https-githubcom-mksglu-context-mode) |
| [mcp-feedback-enhanced](https://github.com/minidoracat/mcp-feedback-enhanced) | 增强版 MCP 服务器，用于 AI 辅助开发中的交互式用户反馈和命令执行... | 91 ✅ | 3.6k | [View](https://agentseal.org/mcp/https-githubcom-minidoracat-mcp-feedback-enhanced) |
| [archestra](https://github.com/archestra-ai/archestra) | 企业 AI 平台，带有防护机制、MCP 注册表、网关和编排器 | 92 ✅ | 3.5k | [View](https://agentseal.org/mcp/https-githubcom-archestra-ai-archestra) |
| [refact-chat-js](https://github.com/smallcloudai/refact) | 端到端处理工程任务的 AI 代理：集成开发者工具... | 92 ✅ | 3.5k | [View](https://agentseal.org/mcp/refact-chat-js) |
| [shadcn-ui-mcp-server](https://github.com/jpisnice/shadcn-ui-mcp-server) | 让 LLM 了解 shadcn UI 组件结构、用法的 MCP 服务器... | 83 ✅ | 2.7k | [View](https://agentseal.org/mcp/jpisnice-shadcn-ui-mcp-server) |
| [mcp-cli](https://github.com/chrishayuk/mcp-cli) | 与模型上下文协议服务器交互的命令行界面... | 92 ✅ | 1.9k | [View](https://agentseal.org/mcp/https-githubcom-chrishayuk-mcp-cli) |
| [ios-simulator-mcp](https://github.com/joshuayoes/ios-simulator-mcp) | 用于与 iOS 模拟器交互的 MCP 服务器 | 91 ✅ | 1.7k | [View](https://agentseal.org/mcp/https-githubcom-joshuayoes-ios-simulator-mcp) |
| [mcp-installer](https://github.com/anaisbetts/mcp-installer) | 为你自动安装其他 MCP 服务器的 MCP 服务器 | 89 ✅ | 1.5k | [View](https://agentseal.org/mcp/anaisbetts-mcp-installer) |
| [notebooklm-mcp](https://github.com/pleaseprompto/notebooklm-mcp) | NotebookLM 的 MCP 服务器 - 让你的 AI 代理 (Claude Code、Codex) 进行研究... | 73 ⚠️ | 1.4k | [View](https://agentseal.org/mcp/https-githubcom-pleaseprompto-notebooklm-mcp) |
| [coderunner](https://github.com/instavm/coderunner) | 面向 AI 代理的本地沙箱 | 80 ⚠️ | 801 | [View](https://agentseal.org/mcp/https-githubcom-instavm-coderunner) |
| [vibetest-use](https://github.com/browser-use/vibetest-use) | Vibetest MCP - 使用 Browser-Use 代理的自动化 QA 测试 | 87 ✅ | 772 | [View](https://agentseal.org/mcp/https-githubcom-browser-use-vibetest-use) |
| [driftdetect-mcp](https://github.com/dadbodgeoff/drift) | 面向 AI 的代码库智能分析。检测模式和约定 + 记忆决策... | 85 ✅ | 760 | [View](https://agentseal.org/mcp/driftdetect-mcp) |
| [just-prompt](https://github.com/disler/just-prompt) | just-prompt 是一个 MCP 服务器，提供与顶级 LLM 提供商的统一接口... | 89 ✅ | 719 | [View](https://agentseal.org/mcp/https-githubcom-disler-just-prompt) |
| [blueprint-mcp](https://github.com/arcadeai/blueprint-mcp) | 用于理解代码库和系统架构的图表生成工具... | 92 ✅ | 585 | [View](https://agentseal.org/mcp/https-githubcom-arcadeai-blueprint-mcp) |
| [n8n-workflow-builder](https://github.com/makafeli/n8n-workflow-builder) | 通过模型上下文协议将 AI 助手集成到 n8n 工作流自动化... | 87 ✅ | 501 | [View](https://agentseal.org/mcp/https-githubcom-makafeli-n8n-workflow-builder) |
| [web-agent-protocol](https://github.com/ota-tech-ai/web-agent-protocol) | Web Agent Protocol (WAP) - 在浏览器中录制和回放用户交互... | 92 ✅ | 493 | [View](https://agentseal.org/mcp/https-githubcom-ota-tech-ai-web-agent-protocol) |
| [airtable-mcp-server](https://github.com/domdomegg/airtable-mcp-server) | Airtable 模型上下文协议服务器，允许 AI 系统与 Airtable 交互... | 81 ✅ | 430 | [View](https://agentseal.org/mcp/https-githubcom-domdomegg-airtable-mcp-server) |
| [kicad-mcp](https://github.com/lamaalrajih/kicad-mcp) | 适用于 Mac、Windows 和 Linux 的 KiCad 模型上下文协议服务器 | 92 ✅ | 401 | [View](https://agentseal.org/mcp/https-githubcom-lamaalrajih-kicad-mcp) |
| [lingti-bot](https://github.com/ruilisi/lingti-bot) | 🐕⚡「极简至上 效率为王 秒级接入 一链即用」的 AI Bot | 75 ⚠️ | 368 | [View](https://agentseal.org/mcp/https-githubcom-ruilisi-lingti-bot) |
| [MemoryMesh](https://github.com/CheMiguel23/MemoryMesh) | 使用模型上下文协议 (MCP) 提供知识图谱服务的服务器... | 81 ✅ | 335 | [View](https://agentseal.org/mcp/https-githubcom-chemiguel23-memorymesh) |
| [paws-on-mcp](https://github.com/hemanth/paws-on-mcp) | 实现最新规范的综合性模型上下文协议 (MCP) 服务器... | 86 ✅ | 331 | [View](https://agentseal.org/mcp/https-githubcom-hemanth-paws-on-mcp) |
| [moling](https://github.com/gojue/moling) | MoLing 是基于计算机控制和浏览器控制的 MCP 服务器。本地部署运行... | 78 ⚠️ | 330 | [View](https://agentseal.org/mcp/https-githubcom-gojue-moling) |
| [consult7](https://github.com/szeider/consult7) | 用于咨询大上下文语言模型的 MCP 服务器 | 85 ✅ | 291 | [View](https://agentseal.org/mcp/https-githubcom-szeider-consult7) |
| [chrome-devtools-mcp](https://github.com/benjaminr/chrome-devtools-mcp) | 遵循 Chrome DevTools Protocol 的 Chrome 开发者工具 MCP 服务器... | 74 ⚠️ | 289 | [View](https://agentseal.org/mcp/https-githubcom-benjaminr-chrome-devtools-mcp) |
| [FileScopeMCP](https://github.com/admica/FileScopeMCP) | 分析代码库，根据依赖关系识别重要文件... | 82 ✅ | 283 | [View](https://agentseal.org/mcp/https-githubcom-admica-filescopemcp) |
| [MCP-Server-Playwright](https://github.com/Automata-Labs-team/MCP-Server-Playwright) | 基于 Playwright 的浏览器自动化 MCP 服务器，提供完整的远程控制... | 74 ⚠️ | 283 | [View](https://agentseal.org/mcp/https-githubcom-automata-labs-team-mcp-server-playwright) |
| [mcp-reasoner](https://github.com/jacck/mcp-reasoner) | 面向 Claude Desktop 的系统化推理 MCP 服务器实现，支持束搜索... | 92 ✅ | 277 | [View](https://agentseal.org/mcp/https-githubcom-jacck-mcp-reasoner) |
| [lucid](https://github.com/get-lucid/lucid) | 将自主代理建立在经过验证的实时知识基础上的智能层... | 92 ✅ | 260 | [View](https://agentseal.org/mcp/https-githubcom-get-lucid-lucid) |
| [weather-mcp-server](https://github.com/tuankiri/weather-mcp-server) | 使 AI 助手能够获取任意位置实时天气数据的 MCP 服务器... | 92 ✅ | 239 | [View](https://agentseal.org/mcp/https-githubcom-tuankiri-weather-mcp-server) |
| [frida-mcp](https://github.com/dnakov/frida-mcp) | Frida 的 MCP stdio 服务器 | 91 ✅ | 237 | [View](https://agentseal.org/mcp/https-githubcom-dnakov-frida-mcp) |
| [tmux-mcp](https://github.com/nickgnd/tmux-mcp) | 面向终端复用器 tmux 的 MCP 服务器。 | 83 ✅ | 235 | [View](https://agentseal.org/mcp/https-githubcom-nickgnd-tmux-mcp) |
| [tmux-mcp](https://github.com/nickgnd/tmux-mcp) | 面向终端复用器 tmux 的 MCP 服务器。 | 83 ✅ | 235 | [View](https://agentseal.org/mcp/tmux-mcp) |
| [overseer](https://github.com/dmmulroy/overseer) | 面向代理任务管理的 CLI 和 Codemode MCP 服务器 | 92 ✅ | 222 | [View](https://agentseal.org/mcp/https-githubcom-dmmulroy-overseer) |
| [mcp-taskmanager](https://github.com/kazuph/mcp-taskmanager) | 使 Claude 能够以队列方式管理和执行任务的 MCP 服务器... | 91 ✅ | 212 | [View](https://agentseal.org/mcp/kazuph-mcp-taskmanager) |
| [opik-mcp](https://github.com/comet-ml/opik-mcp) | Opik 的模型上下文协议 (MCP) 实现，支持无缝 IDE 集成... | 92 ✅ | 199 | [View](https://agentseal.org/mcp/https-githubcom-comet-ml-opik-mcp) |
| [@rocketshipai](https://github.com/rocketship-ai/rocketship) | 开源 QA 测试框架，使编程代理能够编写和运行测试... | 92 ✅ | 182 | [View](https://agentseal.org/mcp/rocketshipai) |
| [anki-mcp-server](https://github.com/scorzeth/anki-mcp-server) | 与本地 Anki 闪卡应用集成的 MCP 服务器，支持创建和管理卡组... | 98 ✅ | 178 | [View](https://agentseal.org/mcp/https-githubcom-scorzeth-anki-mcp-server) |
| [mcp-doc](https://github.com/meterlong/mcp-doc) | 基于 FastMCP 的强大 Word 文档处理服务，使 AI 助手能够处理文档... | 89 ✅ | 173 | [View](https://agentseal.org/mcp/https-githubcom-meterlong-mcp-doc) |
| [llmctx](https://github.com/khromov/llmctx) | 为 AI 代码助手提供 Svelte 5 和 SvelteKit 开发者文档的 MCP 端点... | 92 ✅ | 160 | [View](https://agentseal.org/mcp/https-githubcom-khromov-llmctx) |
| [mcp-server-langfuse](https://github.com/langfuse/mcp-server-langfuse) | 用于 Langfuse 提示词管理的模型上下文协议 (MCP) 服务器... | 92 ✅ | 158 | [View](https://agentseal.org/mcp/https-githubcom-langfuse-mcp-server-langfuse) |
| [erickwendel-contributions-mcp](https://github.com/erickwendel/erickwendel-contributions-mcp) | 提供查询 Erick Wendel 贡献记录工具的模型上下文协议 (MCP) 服务器... | 92 ✅ | 136 | [View](https://agentseal.org/mcp/https-githubcom-erickwendel-erickwendel-contributions-mcp) |
| [mcp-server](https://github.com/browserstack/mcp-server) | BrowserStack 官方 MCP 服务器 | 69 ⚠️ | 130 | [View](https://agentseal.org/mcp/https-githubcom-browserstack-mcp-server) |
| [mcp-server-atlassian-bitbucket](https://github.com/aashari/mcp-server-atlassian-bitbucket) | 用于 Atlassian Bitbucket 的 Node.js/TypeScript MCP 服务器。使 AI 系统 (LLM) 能够交互... | 74 ⚠️ | 127 | [View](https://agentseal.org/mcp/https-githubcom-aashari-mcp-server-atlassian-bitbucket) |
| [pluggedin-mcp-proxy](https://github.com/VeriTeknik/pluggedin-mcp-proxy) | Plugged.in MCP 服务器在一个 MCP 中管理你所有的其他 MCP。 | 81 ✅ | 124 | [View](https://agentseal.org/mcp/https-githubcom-veriteknik-pluggedin-mcp-proxy) |
| [mcp-gdb](https://github.com/signal-slot/mcp-gdb) | 为 AI 助手提供 GDB 调试功能的 MCP 服务器... | 86 ✅ | 110 | [View](https://agentseal.org/mcp/https-githubcom-signal-slot-mcp-gdb) |
| [sourcerer-mcp](https://github.com/st3v3nmw/sourcerer-mcp) | 用于语义代码搜索和导航、减少 token 浪费的 MCP | 86 ✅ | 108 | [View](https://agentseal.org/mcp/https-githubcom-st3v3nmw-sourcerer-mcp) |
| [lapras-mcp-server](https://github.com/lapras-inc/lapras-mcp-server) | lapras.com 公式MCP Server | 89 ✅ | 100 | [View](https://agentseal.org/mcp/https-githubcom-lapras-inc-lapras-mcp-server) |
| [terminal-controller-mcp](https://github.com/gongrzhe/terminal-controller-mcp) | 实现安全终端命令执行的模型上下文协议 (MCP) 服务器... | 80 ⚠️ | 99 | [View](https://agentseal.org/mcp/https-githubcom-gongrzhe-terminal-controller-mcp) |
| [json-mcp-server](https://github.com/gongrzhe/json-mcp-server) | JSON 处理和操作的 MCP 服务器 | 88 ✅ | 89 | [View](https://agentseal.org/mcp/https-githubcom-gongrzhe-json-mcp-server) |
| [unreal-mcp](https://github.com/runreal/unreal-mcp) | 使用 Unreal Python 远程执行的虚幻引擎 MCP 服务器 | 71 ⚠️ | 82 | [View](https://agentseal.org/mcp/runreal-unreal-mcp) |
| [mcp-server-circleci](https://github.com/CircleCI-Public/mcp-server-circleci) | 为 CircleCI 设计的专用模型上下文协议 (MCP) 服务器实现... | 80 ✅ | 80 | [View](https://agentseal.org/mcp/https-githubcom-circleci-public-mcp-server-circleci) |
| [mcp-server-openai](https://github.com/pierrebrunelle/mcp-server-openai) | 使用 MCP 协议直接从 Claude 查询 OpenAI 模型。 | 92 ✅ | 79 | [View](https://agentseal.org/mcp/mcp-server-openai) |
| [multi-ai-advisor-mcp](https://github.com/yuchenssr/multi-ai-advisor-mcp) | 多模型决策顾问 | 92 ✅ | 78 | [View](https://agentseal.org/mcp/https-githubcom-yuchenssr-multi-ai-advisor-mcp) |
| [roundtable](https://github.com/askbudi/roundtable) | 本地 MCP 服务器，协调多个 AI 编程助手 (Claude、Gemini 等)... | 81 ✅ | 78 | [View](https://agentseal.org/mcp/https-githubcom-askbudi-roundtable) |
| [unifai-sdk-js](https://github.com/unifai-network/unifai-sdk-js) | unifai-sdk-js 是 Unifai 的 Javascript/Typescript SDK，面向 AI 原生平台... | 86 ✅ | 75 | [View](https://agentseal.org/mcp/https-githubcom-unifai-network-unifai-sdk-js) |
| [energyplus-mcp](https://github.com/lbnl-eta/energyplus-mcp) | 首个开源模型上下文协议服务器，使 AI 助手和代理能够进行建筑能耗模拟... | 90 ✅ | 69 | [View](https://agentseal.org/mcp/https-githubcom-lbnl-eta-energyplus-mcp) |
| [alibabacloud-devops-mcp-server](https://github.com/aliyun/alibabacloud-devops-mcp-server) | 云效 MCP 服务器为 AI 助手提供与阿里云 DevOps 平台交互的能力... | 87 ✅ | 69 | [View](https://agentseal.org/mcp/https-githubcom-aliyun-alibabacloud-devops-mcp-server) |
| [clarity-mcp-server](https://github.com/microsoft/clarity-mcp-server) | Microsoft Clarity 的模型上下文协议 (MCP) 服务器 | 84 ✅ | 68 | [View](https://agentseal.org/mcp/microsoft-clarity-mcp-server) |
| [deepseek-thinker-mcp](https://github.com/ruixingshi/deepseek-thinker-mcp) | 通过 OpenAI API 访问 Deepseek 推理过程的 MCP 服务器... | 92 ✅ | 67 | [View](https://agentseal.org/mcp/https-githubcom-ruixingshi-deepseek-thinker-mcp) |
| [xiaozhi-autoglm-mcp](https://github.com/xinnan-tech/xiaozhi-autoglm-mcp) | 用于 Android 设备自动化和 AI 驱动的移动代理控制的 MCP 服务器... | 92 ✅ | 64 | [View](https://agentseal.org/mcp/https-githubcom-xinnan-tech-xiaozhi-autoglm-mcp) |
| [mcp-miro](https://github.com/k-jarzyna/mcp-miro) | Miro 的模型上下文协议集成 | 84 ✅ | 62 | [View](https://agentseal.org/mcp/https-githubcom-k-jarzyna-mcp-miro) |
| [mcp-server-atlassian-jira](https://github.com/aashari/mcp-server-atlassian-jira) | 用于 Atlassian Jira 的 Node.js/TypeScript MCP 服务器。为 AI 系统 (LLM) 提供工具... | 80 ⚠️ | 60 | [View](https://agentseal.org/mcp/https-githubcom-aashari-mcp-server-atlassian-jira) |
| [gdb-mcp](https://github.com/smadi0x86/gdb-mcp) | 为 GDB 和 LLDB 提供调试功能的多调试器 MCP 服务器... | 86 ✅ | 56 | [View](https://agentseal.org/mcp/https-githubcom-smadi0x86-gdb-mcp) |
| [whois-mcp](https://github.com/bharathvaj-ganesan/whois-mcp) | 用于 WHOIS 查询的 MCP 服务器。 | 92 ✅ | 52 | [View](https://agentseal.org/mcp/https-githubcom-bharathvaj-ganesan-whois-mcp) |
| [webpage-screenshot-mcp](https://github.com/ananddtyagi/webpage-screenshot-mcp) | 使用 Puppeteer 捕获网页截图的 MCP 服务器，使 AI 能够进行视觉分析... | 87 ✅ | 52 | [View](https://agentseal.org/mcp/https-githubcom-ananddtyagi-webpage-screenshot-mcp) |
| [iphone-mcp](https://github.com/blitzdotdev/iphone-mcp) | 让 AI 使用 iPhone 的 MCP 服务器 | 86 ✅ | 50 | [View](https://agentseal.org/mcp/blitzdev-iphone-mcp) |
| [random-number-mcp](https://github.com/zazencodes/random-number-mcp) | 为 LLM 提供基本随机数生成能力的生产就绪 MCP 服务器... | 90 ✅ | 47 | [View](https://agentseal.org/mcp/https-githubcom-zazencodes-random-number-mcp) |
| [shadowgit-mcp](https://github.com/blade47/shadowgit-mcp) | 为 AI 助手提供安全 Git 操作能力的模型上下文协议 (MCP) 服务器... | 85 ✅ | 46 | [View](https://agentseal.org/mcp/https-githubcom-blade47-shadowgit-mcp) |
| [xray](https://github.com/srijanshukla18/xray) | XRAY MCP 为 AI 代理提供渐进式代码智能和导航能力... | 82 ✅ | 46 | [View](https://agentseal.org/mcp/https-githubcom-srijanshukla18-xray) |
| [frida-game-hacking-mcp](https://github.com/0xhackerfren/frida-game-hacking-mcp) | Frida 的 MCP 实现，旨在模拟 Cheat Engine 的功能... | 71 ⚠️ | 46 | [View](https://agentseal.org/mcp/https-githubcom-0xhackerfren-frida-game-hacking-mcp) |
| [mcp_weather_server](https://github.com/isdaniel/mcp_weather_server) | 提供当前天气和预报、空气质量数据的只读 MCP 服务器... | 100 ✅ | 44 | [View](https://agentseal.org/mcp/https-githubcom-isdaniel-mcpweatherserver) |
| [mcp-server-taskwarrior](https://github.com/awwaiid/mcp-server-taskwarrior) | Taskwarrior MCP 服务器，允许代理列出、添加和完成任务... | 91 ✅ | 44 | [View](https://agentseal.org/mcp/https-githubcom-awwaiid-mcp-server-taskwarrior) |
| [mobile-dev-mcp-server](https://github.com/jsuarezruiz/mobile-dev-mcp-server) | 用于管理移动设备和模拟器交互的 MCP 服务器... | 83 ✅ | 42 | [View](https://agentseal.org/mcp/https-githubcom-jsuarezruiz-mobile-dev-mcp-server) |
| [powertools-mcp](https://github.com/aws-powertools/powertools-mcp) | Powertools for AWS 的官方 MCP 服务器 | 88 ✅ | 41 | [View](https://agentseal.org/mcp/https-githubcom-aws-powertools-powertools-mcp) |
| [dynamic-shell-server](https://github.com/codelion/dynamic-shell-server) | 动态 Shell 命令 MCP 服务器 | 86 ✅ | 41 | [View](https://agentseal.org/mcp/https-githubcom-codelion-dynamic-shell-server) |
| [unreal-api-mcp](https://github.com/Codeturion/unreal-api-mcp) | 只读参考服务器，让代理搜索和检索虚幻引擎 API 文档... | 93 ✅ | 40 | [View](https://agentseal.org/mcp/https-githubcom-codeturion-unreal-api-mcp) |
| [test-coverage-mcp](https://github.com/goldbergyoni/test-coverage-mcp) | 上下文工程：让你的代理了解它们如何影响测试覆盖率... | 89 ✅ | 40 | [View](https://agentseal.org/mcp/https-githubcom-goldbergyoni-test-coverage-mcp) |
| [mcp-tasks](https://github.com/flesler/mcp-tasks) | 全面高效的任务管理 MCP 服务器，支持多种格式... | 91 ✅ | 39 | [View](https://agentseal.org/mcp/https-githubcom-flesler-mcp-tasks) |
| [anki-mcp](https://github.com/nietus/anki-mcp) | Anki 闪卡管理服务器，支持创建、更新和复习闪卡... | 75 ⚠️ | 39 | [View](https://agentseal.org/mcp/https-githubcom-nietus-anki-mcp) |
| [mcp](https://github.com/screenshotone/mcp) | ScreenshotOne API 的简单 MCP 服务器实现 | 88 ✅ | 35 | [View](https://agentseal.org/mcp/https-githubcom-screenshotone-mcp) |
| [package-registry-mcp](https://github.com/artmann/package-registry-mcp) | 用于搜索和获取 NPM、Cargo 等包最新信息的 MCP 服务器... | 86 ✅ | 35 | [View](https://agentseal.org/mcp/package-registry-mcp) |
| [kilntainers](https://github.com/kiln-ai/kilntainers) | 为每个代理提供临时 Linux 沙箱以执行 Shell 命令的 MCP 服务器... | 85 ✅ | 34 | [View](https://agentseal.org/mcp/https-githubcom-kiln-ai-kilntainers) |
| [actor-critic-thinking-mcp](https://github.com/aquarius-wing/actor-critic-thinking-mcp) | 基于模型上下文协议 (MCP) 的双视角思维分析服务器... | 100 ✅ | 32 | [View](https://agentseal.org/mcp/https-githubcom-aquarius-wing-actor-critic-thinking-mcp) |
| [maven-mcp-server](https://github.com/Bigsy/maven-mcp-server) | 提供检查 Maven 包版本工具的 MCP (模型上下文协议) 服务器... | 92 ✅ | 31 | [View](https://agentseal.org/mcp/https-githubcom-bigsy-maven-mcp-server) |
| [PiloTY](https://github.com/yiwenlu66/PiloTY) | PiloTY：通过 MCP 进行 PTY 操作的 AI 驾驶员 - 使 AI 代理能够控制交互式终端... | 74 ⚠️ | 30 | [View](https://agentseal.org/mcp/https-githubcom-yiwenlu66-piloty) |
| [splunk-mcp-server2](https://github.com/splunk/splunk-mcp-server2) | 非官方 Splunk MCP 服务器。使用 Python 和 TypeScript/JS 实现。运行... | 86 ✅ | 29 | [View](https://agentseal.org/mcp/https-githubcom-splunk-splunk-mcp-server2) |
| [mcpcap](https://github.com/mcpcap/mcpcap) | 模块化 Python MCP 服务器，用于分析网络数据包捕获，带有专业分析模块... | 75 ⚠️ | 28 | [View](https://agentseal.org/mcp/https-githubcom-mcpcap-mcpcap) |
| [mcp-simple-timeserver](https://github.com/andybrandt/mcp-simple-timeserver) | 提供本地时间、NTP UTC 时间、时区转换等功能的时间日期工具 MCP 服务器... | 92 ✅ | 27 | [View](https://agentseal.org/mcp/https-githubcom-andybrandt-mcp-simple-timeserver) |
| [gemini-cli-orchestrator](https://github.com/dnnyngyen/gemini-cli-orchestrator) | 允许 Claude Code 编排 Gemini 进行分析和协作的 MCP 服务器... | 91 ✅ | 25 | [View](https://agentseal.org/mcp/https-githubcom-dnnyngyen-gemini-cli-orchestrator) |
| [ScreenshotMCP](https://github.com/upnorthmedia/ScreenshotMCP) | 具有全功能网站截图捕获能力的模型上下文协议 MCP 服务器... | 88 ✅ | 25 | [View](https://agentseal.org/mcp/https-githubcom-upnorthmedia-screenshotmcp) |
| [mcp-task-orchestrator](https://github.com/EchoingVesper/mcp-task-orchestrator) | 提供任务编排能力的模型上下文协议服务器... | 88 ✅ | 24 | [View](https://agentseal.org/mcp/https-githubcom-echoingvesper-mcp-task-orchestrator) |
| [code-memory](https://github.com/kapillamba4/code-memory) | 使用向量嵌入的本地代码库语义搜索。零遥测... | 72 ⚠️ | 24 | [View](https://agentseal.org/mcp/https-githubcom-kapillamba4-code-memory) |
| [anti-bullshit-mcp-server](https://github.com/bmorphism/anti-bullshit-mcp-server) | 用于分析声明、验证来源和检测操控手法的 MCP 服务器... | 92 ✅ | 23 | [View](https://agentseal.org/mcp/https-githubcom-bmorphism-anti-bullshit-mcp-server) |
| [blowback-context](https://github.com/esnark/blowback) | 面向前端开发环境的 MCP 服务器，与 AI 工具集成... | 87 ✅ | 22 | [View](https://agentseal.org/mcp/blowback-context) |
| [create-mcp-ts](https://github.com/stephencme/create-mcp-ts) | 用 TypeScript 创建新的 MCP 服务器，开箱即用。 | 91 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-stephencme-create-mcp-ts) |
| [mcpretentious](https://github.com/oetiker/mcpretentious) | 强大的模型上下文协议 (MCP) 服务器，通过木偶化控制 iTerm2 终端。 | 88 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-oetiker-mcpretentious) |
| [securitycopilotmcpserver](https://github.com/jguimera/securitycopilotmcpserver) | 集成 Security Copilot、Sentinel 和其他工具的 MCP 服务器... | 82 ✅ | 20 | [View](https://agentseal.org/mcp/https-githubcom-jguimera-securitycopilotmcpserver) |
| [termlink](https://github.com/chu2bard/termlink) | 用于 Shell 和终端操作的 MCP 服务器 | 91 ✅ | 19 | [View](https://agentseal.org/mcp/https-githubcom-chu2bard-termlink) |
| [hyperbolic-mcp](https://github.com/HyperbolicLabs/hyperbolic-mcp) | 使 Claude 能够与 Hyperbolic GPU 云交互、查看和管理资源的 MCP 服务器... | 86 ✅ | 19 | [View](https://agentseal.org/mcp/https-githubcom-hyperboliclabs-hyperbolic-mcp) |
| [anki-connect-mcp](https://github.com/spacholski1225/anki-connect-mcp) | 面向 Anki Web 的自定义模型上下文协议 (MCP) 实现，支持无缝集成... | 80 ⚠️ | 18 | [View](https://agentseal.org/mcp/https-githubcom-spacholski1225-anki-connect-mcp) |
| [alertmanager-mcp-server](https://github.com/ntk148v/alertmanager-mcp-server) | 使 AI 助手能够集成 Alertmanager 的模型上下文协议 (MCP) 服务器... | 87 ✅ | 16 | [View](https://agentseal.org/mcp/https-githubcom-ntk148v-alertmanager-mcp-server) |
| [mcp_server_pcileech](https://github.com/evan7198/mcp_server_pcileech) | 使用 pcileech 读写另一台电脑内存的简单 MCP 服务器 | 85 ✅ | 16 | [View](https://agentseal.org/mcp/https-githubcom-evan7198-mcpserverpcileech) |
| [Autogen_MCP](https://github.com/DynamicEndpoints/Autogen_MCP) | 支持创建、配置和执行 Microsoft AutoGen 代理的 MCP 服务器... | 76 ⚠️ | 16 | [View](https://agentseal.org/mcp/https-githubcom-dynamicendpoints-autogenmcp) |
| [npm-search-mcp-server](https://github.com/btwiuse/npm-search-mcp-server) | 用于搜索 npm 包的 MCP 服务器 | 92 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-btwiuse-npm-search-mcp-server) |
| [android-mcp-server](https://github.com/jiantao88/android-mcp-server) | Android MCP 服务器实现 | 87 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-jiantao88-android-mcp-server) |
| [networksdb-mcp](https://github.com/mordavid/networksdb-mcp) | NetworksDB API 的快速 MCP 集成 - 查询 IP 地址、组织信息等... | 86 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-mordavid-networksdb-mcp) |
| [context-crystallizer](https://github.com/hubertciebiada/context-crystallizer) | 将大型代码仓库转化为结晶化的、AI 可消费的知识库... | 82 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-hubertciebiada-context-crystallizer) |
| [agentops-mcp](https://github.com/AgentOps-AI/agentops-mcp) | 用于查询 AgentOps 代理遥测数据的 MCP 服务器 - 通过 API 密钥授权... | 96 ✅ | 14 | [View](https://agentseal.org/mcp/https-githubcom-agentops-ai-agentops-mcp) |
| [argus-mcp](https://github.com/lokafinnsw/argus-mcp) | 采用零信任方式的 AI 代码审查 MCP 服务器。支持多模型、缓存... | 92 ✅ | 14 | [View](https://agentseal.org/mcp/https-githubcom-lokafinnsw-argus-mcp) |
| [mcp-time](https://github.com/TheoBrigitte/mcp-time) | 提供时间处理工具的 MCP (模型上下文协议) 服务器... | 89 ✅ | 14 | [View](https://agentseal.org/mcp/theofoobar-mcp-time) |
| [currents-mcp](https://github.com/currents-dev/currents-mcp) | Currents MCP 服务器 | 84 ✅ | 14 | [View](https://agentseal.org/mcp/https-githubcom-currents-dev-currents-mcp) |
| [domain-tools-mcp-server](https://github.com/deshabhishek007/domain-tools-mcp-server) | 用于全面域名分析的模型上下文协议 (MCP) 服务器：WHOIS 查询... | 92 ✅ | 13 | [View](https://agentseal.org/mcp/https-githubcom-deshabhishek007-domain-tools-mcp-server) |
| [riza-mcp](https://github.com/riza-io/riza-mcp) | 通过 Riza API 为 LLM 生成的代码提供隔离代码解释器，带工具管理... | 91 ✅ | 13 | [View](https://agentseal.org/mcp/https-githubcom-riza-io-riza-mcp) |
| [qrcode_mcp](https://github.com/2niuhe/qrcode_mcp) | 生成二维码的 MCP 工具 | 91 ✅ | 12 | [View](https://agentseal.org/mcp/https-githubcom-2niuhe-qrcodemcp) |
| [d.i.e-mcp](https://github.com/lazy-importer/d.i.e-mcp) | DIE (Detect It Easy) 的 MCP 服务器 | 92 ✅ | 11 | [View](https://agentseal.org/mcp/https-githubcom-lazy-importer-die-mcp) |
| [mcp-go-debugger](https://github.com/sunfmin/mcp-go-debugger) | 集成 MCP 的 Go 调试器，支持启动、附加、设置断点... | 88 ✅ | 11 | [View](https://agentseal.org/mcp/https-githubcom-sunfmin-mcp-go-debugger) |
| [teamcity-mcp](https://github.com/itcaat/teamcity-mcp) | TeamCity MCP 服务器 | 86 ✅ | 11 | [View](https://agentseal.org/mcp/https-githubcom-itcaat-teamcity-mcp) |
| [kylas-crm-mcp-server](https://github.com/kylastech/kylas-crm-mcp-server) | Kylas CRM 集成服务器，支持创建、更新、搜索功能... | 67 ⚠️ | 11 | [View](https://agentseal.org/mcp/https-githubcom-kylastech-kylas-crm-mcp-server) |
| [memory-mcp](https://github.com/chenxiaofie/memory-mcp) | 本地对话记忆系统，缓存消息、管理任务片段... | 91 ✅ | 10 | [View](https://agentseal.org/mcp/https-githubcom-chenxiaofie-memory-mcp) |
| [mcp-gitlab-jira](https://github.com/HainanZhao/mcp-gitlab-jira) | 用于 GitLab 和 Jira 集成的 MCP 服务器，使 AI 代理能够交互... | 92 ✅ | 9 | [View](https://agentseal.org/mcp/mcp-gitlab-jira) |
| [pyxel-mcp](https://github.com/kitao/pyxel-mcp) | 运行 Pyxel 复古游戏脚本并提供视觉/音频信息的 MCP 服务器... | 79 ⚠️ | 9 | [View](https://agentseal.org/mcp/https-githubcom-kitao-pyxel-mcp) |
| [mcp-agentic-framework](https://github.com/Piotr1215/mcp-agentic-framework) | 允许 AI 代理注册、发现和协调的多代理框架... | 78 ⚠️ | 9 | [View](https://agentseal.org/mcp/https-githubcom-piotr1215-mcp-agentic-framework) |
| [canvas-lms-mcp](https://github.com/ahnopologetic/canvas-lms-mcp) | 将 AI 系统与 Canvas LMS 连接的 MCP 服务器，提供教育数据访问... | 89 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-ahnopologetic-canvas-lms-mcp) |
| [mcp-project-manager](https://github.com/croffasia/mcp-project-manager) | 通过模型上下文协议 (MCP) 实现的分层任务管理服务器... | 88 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-croffasia-mcp-project-manager) |
| [mcp-server-adb](https://github.com/watabee/mcp-server-adb) | MCP Server for Android Debug Bridge (ADB), enabling Claude to interact with A... | 87 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-watabee-mcp-server-adb) |
| [piston-mcp](https://github.com/alvii147/piston-mcp) | 使用 Piston 远程运行时执行多种编程语言的任意代码... | 84 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-alvii147-piston-mcp) |
| [sonatype-mcp](https://github.com/brianveltman/sonatype-mcp) | Sonatype Nexus Repository Manager 的 MCP 服务器 | 84 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-brianveltman-sonatype-mcp) |
| [skill-ninja-mcp-server](https://github.com/aktsmm/skill-ninja-mcp-server) | 代理技能包管理器，搜索、安装和管理 SKILL.md 文件... | 76 ⚠️ | 7 | [View](https://agentseal.org/mcp/https-githubcom-aktsmm-skill-ninja-mcp-server) |
| [mcp-idb](https://github.com/noahlozevski/mcp-idb) | fb-idb 桥接的 MCP 服务器。 | 86 ✅ | 6 | [View](https://agentseal.org/mcp/noahlozevski-mcp-idb) |
| [spm-mcp](https://github.com/simpleswift/spm-mcp) | 用 Swift 编写的 Swift Package Manager MCP 服务器 | 85 ✅ | 6 | [View](https://agentseal.org/mcp/simpleswift-spm-mcp) |
| [public-apis-mcp](https://github.com/zazencodes/public-apis-mcp) | 使用 MCP 搜索免费 API | 85 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-zazencodes-public-apis-mcp) |
| [reexpress_mcp_server](https://github.com/ReexpressAI/reexpress_mcp_server) | Reexpress 模型上下文协议 (MCP) 服务器 | 82 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-reexpressai-reexpressmcpserver) |
| [mcpgex](https://github.com/patzedi/mcpgex) | 用于查找、测试和优化正则表达式模式的 MCP 服务器 | 92 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-patzedi-mcpgex) |
| [mcp-sandbox](https://github.com/danstarns/mcp-sandbox) | 将任何 JavaScript 模块转换为沙箱化 MCP 服务器，自动反射... | 92 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-danstarns-mcp-sandbox) |
| [mcp-grep](https://github.com/247arjun/mcp-grep) | grep CLI 工具的 MCP 服务器封装 | 87 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-247arjun-mcp-grep) |
| [log-analyzer-mcp](https://github.com/Fato07/log-analyzer-mcp) | 用于解析、搜索和调试多种格式日志文件的 MCP 服务器... | 81 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-fato07-log-analyzer-mcp) |
| [time-mcp-pypi.git](https://github.com/domdomegg/time-mcp-pypi.git) | 提供获取当前 UTC 日期和时间工具的最小化 Python MCP 服务器... | 92 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-domdomegg-time-mcp-pypigit) |
| [sonarcloud-mcp](https://github.com/dozzman/sonarcloud-mcp) | 用于获取问题的 SonarCloud/SonarQube Cloud MCP 服务器 | 92 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-dozzman-sonarcloud-mcp) |
| [aria-validate-mcp-server](https://github.com/yamanoku/aria-validate-mcp-server) | 用于验证 ARIA (无障碍富互联网应用) 属性的模型上下文协议服务器... | 92 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-yamanoku-aria-validate-mcp-server) |
| [node-code-sandbox-mcp](https://github.com/mozicim/node-code-sandbox-mcp) | Node.js 沙箱 MCP 服务器，托管实现了安全代码执行的 Node.js 服务器... | 77 ⚠️ | 4 | [View](https://agentseal.org/mcp/node-code-sandbox-mcp) |
| [conan-mcp](https://github.com/conan-io/conan-mcp) | Conan 包管理器的模型上下文协议服务器，支持项目创建... | 77 ⚠️ | 4 | [View](https://agentseal.org/mcp/https-githubcom-conan-io-conan-mcp) |
| [mcp-refactoring.git](https://github.com/marshally/mcp-refactoring.git) | 列出、预览和应用 Fowler 风格代码重构的 MCP 服务器... | 92 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-marshally-mcp-refactoringgit) |
| [mcp-postman](https://github.com/freebeiro/mcp-postman) | 基于 Cloudflare Workers 构建的模型上下文协议 (MCP) 服务器，用于集成... | 92 ✅ | 3 | [View](https://agentseal.org/mcp/mcp-postman) |
| [context-rot-detection](https://github.com/milos-product-maker/context-rot-detection) | 为 AI 代理提供认知健康状况实时可见性的 MCP 服务... | 92 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-milos-product-maker-context-rot-detection) |
| [cfr_mcp_server](https://github.com/mr-xn/cfr_mcp_server) | 这是一个基于 Python 的 MCP (Model Context Protocol) 服务器实现，封装了 `cfr.jar` 反编译功能，并支持 SS... | 92 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-mr-xn-cfrmcpserver) |
| [krs-poland-mcp-server](https://github.com/pkolawa/krs-poland-mcp-server) | 波兰 KRS 公共 API 的 MCP 服务器。 | 92 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-pkolawa-krs-poland-mcp-server) |
| [mcp-ghidra5-windows](https://github.com/thestingr/mcp-ghidra5-windows) | 面向 GPT-5 驱动的 Ghidra 逆向工程的企业级 Windows 服务... | 92 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-thestingr-mcp-ghidra5-windows) |
| [math-mcp-learning-server](https://github.com/clouatre-labs/math-mcp-learning-server) | 教育性 MCP 服务器，包含 17 个数学工具，涵盖算术、矩阵代数... | 84 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-clouatre-labs-math-mcp-learning-server) |
| [mcp-relay](https://github.com/mhcoen/mcp-relay) | 消息中继缓冲区，允许 Claude Desktop 和 Claude Code 传递不透明数据... | 79 ⚠️ | 3 | [View](https://agentseal.org/mcp/https-githubcom-mhcoen-mcp-relay) |
| [snowfakery-mcp](https://github.com/composable-delivery/snowfakery-mcp) | 封装 Snowfakery 的 MCP 服务器，用于生成逼真的假数据... | 76 ⚠️ | 3 | [View](https://agentseal.org/mcp/https-githubcom-composable-delivery-snowfakery-mcp) |
| [memory-mcp](https://github.com/michael-denyer/memory-mcp) | AI 助手的持久化记忆系统，带有即时召回的热缓存... | 71 ⚠️ | 3 | [View](https://agentseal.org/mcp/https-githubcom-michael-denyer-memory-mcp) |
| [selenium-selfhealing-mcp](https://github.com/aiqualitylab/selenium-selfhealing-mcp) | 当 UI 变化导致 Selenium 测试定位器失效时自动修复的 MCP 服务器... | 92 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-aiqualitylab-selenium-selfhealing-mcp) |
| [mcp-agile-luminary](https://github.com/AgileLuminary/mcp-agile-luminary) | 用于连接 Agile Luminary 项目管理应用的 MCP 服务器 | 92 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-agileluminary-mcp-agile-luminary) |
| [frida-mcp](https://github.com/rmorgans/frida-mcp) | Frida 的 MCP 服务器，使 AI 系统能够动态检测和分析应用... | 91 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-rmorgans-frida-mcp) |
| [clix-mcp-server](https://github.com/clix-so/clix-mcp-server) | Clix MCP 服务器使 AI 代理能够提供实时、可信的 Clix 文档... | 89 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-clix-so-clix-mcp-server) |
| [mcp-page-capture](https://github.com/chasesaurabh/mcp-page-capture) | 捕获网页截图并返回 MCP 兼容的元数据，用于自动化测试... | 88 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-chasesaurabh-mcp-page-capture) |
| [ctfd-mcp-server](https://github.com/mrjamescot/ctfd-mcp-server) | 将 AI 代理与 CTFd 实例连接的 MCP 配置。 | 88 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-mrjamescot-ctfd-mcp-server) |
| [coderide-mcp](https://github.com/PixdataOrg/coderide-mcp) | 面向 AI 编程代理的项目和任务管理 MCP 服务器，支持检索... | 85 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-pixdataorg-coderide-mcp) |
| [github-projects-mcp](https://github.com/redducklabs/github-projects-mcp) | GitHub Projects v2 管理服务器，封装 GitHub GraphQL API 进行项目管理... | 82 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-redducklabs-github-projects-mcp) |
| [tools](https://github.com/the-basilisk-ai/squad-mcp) | AI 驱动的产品发现和策略平台，与 Claude 集成... | 81 ✅ | 2 | [View](https://agentseal.org/mcp/squadai-tools) |
| [xctools-mcp-server](https://github.com/nzrsky/xctools-mcp-server) | 面向各种 Xcode 相关工具的模型上下文协议服务器 | 81 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-nzrsky-xctools-mcp-server) |
| [terminal-mcp](https://github.com/mkpvishnu/terminal-mcp) | 用于交互式终端会话的 MCP 服务器：SSH、REPL、数据库 CLI 等... | 81 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-mkpvishnu-terminal-mcp) |
| [agentic-store-mcp](https://github.com/agenticstore/agentic-store-mcp) | 用 AgenticStore 的免费开源 MCP 工具为你的 AI 代理赋能... | 75 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-agenticstore-agentic-store-mcp) |
| [physbound](https://github.com/JonesRobM/physbound) | RF/物理验证 MCP 服务器，计算链路预算、Shannon-Hartley 容量... | 100 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-jonesrobm-physbound) |
| [char-index-mcp](https://github.com/agent-hanju/char-index-mcp) | 纯字符串/字符索引操作库，提供查找、分割、插入功能... | 97 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-agent-hanju-char-index-mcp) |
| [M365-roadmap-mcp-server](https://github.com/jonnybottles/M365-roadmap-mcp-server) | 使 AI 代理能够程序化查询 Microsoft 365 路线图的 Python MCP 服务器... | 87 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-jonnybottles-m365-roadmap-mcp-server) |
| [meta-prompt-mcp](https://github.com/kapillamba4/meta-prompt-mcp) | 检索 Google 和 Anthropic 官方提示词指南的提示词参考服务器... | 84 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-kapillamba4-meta-prompt-mcp) |
| [mcp-autogen-doc](https://github.com/sykuang/mcp-autogen-doc) | 为 AI 助手提供各种能力的模型上下文协议 (MCP) 服务器... | 84 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-sykuang-mcp-autogen-doc) |
| [nativ-mcp](https://github.com/Nativ-Technologies/nativ-mcp) | AI 驱动的本地化 MCP 服务器，在翻译内容的同时尊重品牌风格... | 84 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-nativ-technologies-nativ-mcp) |
| [simctl-mcp-server](https://github.com/nzrsky/simctl-mcp-server) | iOS simctl MCP 服务器 | 79 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-nzrsky-simctl-mcp-server) |
| [cowork-history](https://github.com/egoughnour/cowork-history) | 使用向量嵌入索引和搜索 Claude 对话历史的本地 MCP 服务器... | 76 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-egoughnour-cowork-history) |
| [dbgprobe-mcp-server.git](https://github.com/es617/dbgprobe-mcp-server.git) | 通过硬件调试探针进行 AI 辅助嵌入式系统调试的 MCP 服务器... | 75 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-es617-dbgprobe-mcp-servergit) |
| [algora-mcp-server](https://github.com/idapixl/algora-mcp-server) | 用于浏览、搜索和检索统计数据的只读 MCP 服务器... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-idapixl-algora-mcp-server) |
| [heatpump-mcp-server](https://github.com/jiweiqi/heatpump-mcp-server) | 帮助用户选型、比较和评估热泵系统的 MCP 服务器... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-jiweiqi-heatpump-mcp-server) |
| [fabric-mcp-server](https://github.com/adapoet/fabric-mcp-server) | Fabric AI 模式推荐服务器，建议最佳 Fabric 模式... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-adapoet-fabric-mcp-server) |
| [time-node-mcp](https://github.com/davidan90/time-node-mcp) | 提供时区感知日期和时间工具的 Node.js MCP 服务器... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-davidan90-time-node-mcp) |
| [chrono-mcp](https://github.com/JMoak/chrono-mcp) | 提供当前时间检索和时区转换的时间和时区工具 MCP 服务器... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-jmoak-chrono-mcp) |
| [crash-mcp](https://github.com/nikkoxgonzales/crash-mcp) | 结构化推理步骤跟踪器，帮助 AI 代理分解复杂问题... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-nikkoxgonzales-crash-mcp) |
| [devops-practices](https://github.com/ai-4-devops/devops-practices) | 提供 DevOps 实践文档和框架的只读知识库服务器... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-ai-4-devops-devops-practices) |
| [mcp-domain-availability](https://github.com/imprvhub/mcp-domain-availability) | 使用单一查询工具检查域名可用性的 MCP 服务器。 | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-imprvhub-mcp-domain-availability) |
| [mcp_server_notify](https://github.com/Cactusinhand/mcp_server_notify) | 发送系统桌面通知，支持可选声音和可配置超时。 | 98 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-cactusinhand-mcpservernotify) |
| [agent-domain-service-mcp](https://github.com/gregm711/agent-domain-service-mcp) | 检查域名可用性、探索 TLD 变体的 MCP 服务器... | 98 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-gregm711-agent-domain-service-mcp) |
| [Clojars-MCP-Server](https://github.com/Bigsy/Clojars-MCP-Server) | 查询 Clojars Maven/Clojure 包注册表以获取依赖版本信息... | 98 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-bigsy-clojars-mcp-server) |
| [zoho-crm-mcp-server](https://github.com/asklokesh/zoho-crm-mcp-server) | Zoho CRM MCP 服务器，提供对线索、联系人等的读写访问... | 98 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-asklokesh-zoho-crm-mcp-server) |
| [code-context-provider-mcp](https://github.com/AB498/code-context-provider-mcp) | 提供本地项目目录的结构化概览，包括文件树... | 97 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-ab498-code-context-provider-mcp) |
| [gotohuman-mcp-server](https://github.com/gotohuman/gotohuman-mcp-server) | 通过列出审核表单、获取详情来实现 AI 到人工审核的移交... | 96 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-gotohuman-gotohuman-mcp-server) |
| [guidance-lark-mcp](https://github.com/guidance-ai/guidance-lark-mcp) | 用于验证 llguidance/Lark 语法、运行批量解析测试的 MCP 服务器... | 96 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-guidance-ai-guidance-lark-mcp) |
| [mcp-server-calculator](https://github.com/githejie/mcp-server-calculator) | 暴露一个数学表达式求值工具的最小化 MCP 服务器... | 95 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-githejie-mcp-server-calculator) |
| [stella-mcp](https://github.com/bradleylab/stella-mcp) | 用于构建和运行 Stella XMILE 系统动力学模拟的 MCP 服务器... | 93 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-bradleylab-stella-mcp) |
| [mcp-server-r-counter](https://github.com/guanqun-yang/mcp-server-r-counter) | 计算输入字符串中 'R' 或 'r' 字符的数量。 | 93 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-guanqun-yang-mcp-server-r-counter) |
| [excel-to-json-mcp](https://github.com/he-yang/excel-to-json-mcp) | 通过两个工具将 Excel (.xlsx) 文件和 CSV/制表符分隔数据转换为 JSON... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-he-yang-excel-to-json-mcp) |
| [mcp-files](https://github.com/flesler/mcp-files) | 面向开发者的 MCP 服务器，提供代码符号提取、精确行编辑... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-flesler-mcp-files) |
| [excalidraw-architect-mcp](https://github.com/BV-Venky/excalidraw-architect-mcp) | 生成和编辑 Excalidraw (.excalidraw) 图表文件的 MCP 服务器... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-bv-venky-excalidraw-architect-mcp) |
| [drand-mcp-server](https://github.com/randa-mu/drand-mcp-server) | 为 AI 应用提供来自 drand 网络的可验证随机性的 MCP 服务器... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-randa-mu-drand-mcp-server) |
| [time-mcp-server](https://github.com/lchinglen/time-mcp-server) | 提供时间和时区转换功能的 MCP 服务器，支持 IANA 时区... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-lchinglen-time-mcp-server) |
| [mcp-enhance-prompt](https://github.com/FelixFoster/mcp-enhance-prompt) | 将最简用户输入改写为丰富结构化提示词的 MCP 服务器... | 91 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-felixfoster-mcp-enhance-prompt) |
| [mcp-server-spira](https://github.com/Inflectra/mcp-server-spira) | 面向 Inflectra SpiraTeam/SpiraPlan 的 MCP 服务器，提供 ALM 数据的只读访问... | 90 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-inflectra-mcp-server-spira) |
| [mcp-EDA](https://github.com/NellyW8/mcp-EDA) | EDA 工具链 MCP 服务器，支持 Verilog 综合 (Yosys)、仿真... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-nellyw8-mcp-eda) |
| [godot-mcp](https://github.com/Coding-Solo/godot-mcp) | Godot 游戏引擎集成服务器，支持启动编辑器、运行项目... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-coding-solo-godot-mcp) |
| [bruno-mcp](https://github.com/hungthai1401/bruno-mcp) | 通过 Bruno CLI 执行 Bruno API 集合，支持 HTTP API 测试... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-hungthai1401-bruno-mcp) |
| [callout](https://github.com/fantasieleven-code/callout) | 面向个人/早期创业者的 AI 联合创始人助手，提供多视角分析... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-fantasieleven-code-callout) |
| [comet-mcp](https://github.com/hanzili/comet-mcp) | 控制 Comet/Perplexity 浏览器实例进行代理式网页浏览... | 85 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-hanzili-comet-mcp) |
| [mcp-google-search-console](https://github.com/crunchtools/mcp-google-search-console) | 封装 Google Search Console API 查询搜索分析数据的 MCP 服务器... | 84 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-google-search-console) |
| [jupytercad-mcp](https://github.com/asmith26/jupytercad-mcp) | JupyterCAD MCP 服务器，支持 AI 驱动的 3D CAD 模型创建和编辑... | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-asmith26-jupytercad-mcp) |
| [frontend-design-loop-mcp](https://github.com/alexalexalex222/frontend-design-loop-mcp) | AI 驱动的前端设计自动化工具，生成、评估和优化界面... | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-alexalexalex222-frontend-design-loop-mcp) |
| [mcp-azure-devops](https://github.com/Vortiago/mcp-azure-devops) | 提供 Azure DevOps 工作项、团队等完整 CRUD 访问的 MCP 服务器... | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-vortiago-mcp-azure-devops) |
| [mcp-server](https://github.com/lilo-property/mcp-server) | 面向 AI 代理的度假租赁预订和保护 | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-lilo-property-mcp-server) |
| [mcp-devcontainers](https://github.com/AI-QL/mcp-devcontainers) | 管理 VS Code 开发容器生命周期操作，包括启动、停止... | 82 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-ai-ql-mcp-devcontainers) |
| [postmancer](https://github.com/hijaz/postmancer) | HTTP API 测试客户端 (类似 Postman)，可发送任意 HTTP 请求... | 80 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-hijaz-postmancer) |
| [code-screenshot-mcp](https://github.com/MoussaabBadla/code-screenshot-mcp) | 从代码生成语法高亮截图图片的 MCP 服务器... | 80 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-moussaabbadla-code-screenshot-mcp) |
| [mcp-internet-speed-test](https://github.com/inventer-dev/mcp-internet-speed-test) | 用于测量网络性能指标 (下载/上传速度) 的 MCP 服务器... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-inventer-dev-mcp-internet-speed-test) |
| [MCP](https://github.com/akshaykylas94/MCP) | Kylas CRM MCP 服务器，提供创建、搜索和过滤销售线索的工具... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-akshaykylas94-mcp) |
| [mathematica-mcp](https://github.com/lars20070/mathematica-mcp) | 评估任意 Wolfram 语言表达式的 Mathematica/Wolfram Engine MCP 服务器... | 76 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-lars20070-mathematica-mcp) |
| [gemini-bridge](https://github.com/eLyiN/gemini-bridge) | 将代理查询和任意本地文件内容转发到 Gemini 的桥接 MCP 服务器... | 74 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-elyin-gemini-bridge) |
| [blender-mcp](https://github.com/pranav-deshmukh/blender-mcp) | Blender 自动化服务器，让代理通过 Python 控制 3D 软件... | 74 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-pranav-deshmukh-blender-mcp) |
| [curate-ipsum](https://github.com/egoughnour/curate-ipsum) | 变异测试和程序合成平台，运行单元/集成测试... | 73 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-egoughnour-curate-ipsum) |
| [mcp-python-exec-sandbox](https://github.com/lu-zhengda/mcp-python-exec-sandbox) | 带有通过 PEP 723 自动管理依赖的 Python 代码执行服务器... | 72 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-lu-zhengda-mcp-python-exec-sandbox) |
| [firefox-devtools-mcp](https://github.com/freema/firefox-devtools-mcp) | Firefox 浏览器自动化 MCP 服务器，提供标签管理、DOM 交互... | 70 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-freema-firefox-devtools-mcp) |
| [massive-context-mcp](https://github.com/egoughnour/massive-context-mcp) | 递归式大上下文处理服务器，加载、分块、过滤和处理大量数据... | 69 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-egoughnour-massive-context-mcp) |
| [mcp-gitlab](https://github.com/crunchtools/mcp-gitlab) | 全面的 GitLab MCP 服务器，提供项目、仓库等的完整 API 访问... | 68 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-gitlab) |

### 🔍 <a name="search--knowledge"></a>Search & Knowledge

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [airweave-mcp-search](https://github.com/airweave-ai/airweave) | 面向 AI 代理的开源上下文检索层 | 92 ✅ | 6.0k | [View](https://agentseal.org/mcp/airweave-mcp-search) |
| [exa-mcp-server](https://github.com/exa-labs/exa-mcp-server) | Exa MCP 网页搜索和网页爬取！ | 84 ✅ | 4.0k | [View](https://agentseal.org/mcp/exa-mcp-server) |
| [exa-mcp-server](https://github.com/exa-labs/exa-mcp-server) | 将 AI 助手连接到 Exa 的搜索能力，支持网页搜索、代码搜索... | 84 ✅ | 4.0k | [View](https://agentseal.org/mcp/https-githubcom-exa-labs-exa-mcp-server) |
| [open-webSearch](https://github.com/Aas-ee/open-webSearch) | 使用免费多引擎搜索的 WebSearchMCP (无需 API 密钥) - 支持... | 74 ⚠️ | 790 | [View](https://agentseal.org/mcp/https-githubcom-aas-ee-open-websearch) |
| [howtocook-mcp](https://github.com/worryzyy/howtocook-mcp) | 基于Anduin2017 / HowToCook （程序员在家做饭指南）的mcp server | 86 ✅ | 697 | [View](https://agentseal.org/mcp/https-githubcom-worryzyy-howtocook-mcp) |
| [mcp-gsc](https://github.com/aminforou/mcp-gsc) | 面向 SEO 的 Google Search Console 与 Claude AI 洞察 | 84 ✅ | 535 | [View](https://agentseal.org/mcp/mcp-gsc) |
| [zotero-mcp](https://github.com/cookjohn/zotero-mcp) | Zotero 插件扩展。Zotero MCP 插件实现了 AI 与文献管理的集成... | 90 ✅ | 460 | [View](https://agentseal.org/mcp/https-githubcom-cookjohn-zotero-mcp) |
| [graphlit-mcp-server](https://github.com/graphlit/graphlit-mcp-server) | Graphlit 平台的模型上下文协议 (MCP) 服务器 | 72 ⚠️ | 372 | [View](https://agentseal.org/mcp/https-githubcom-graphlit-graphlit-mcp-server) |
| [gptr-mcp](https://github.com/assafelovic/gptr-mcp) | 通过 MCP 使 LLM 应用执行深度研究的 MCP 服务器... | 84 ✅ | 330 | [View](https://agentseal.org/mcp/https-githubcom-assafelovic-gptr-mcp) |
| [idea-reality-mcp](https://github.com/mnemox-ai/idea-reality-mcp) | 通过查询检查产品创意是否已存在的研究助手... | 98 ✅ | 316 | [View](https://agentseal.org/mcp/https-githubcom-mnemox-ai-idea-reality-mcp) |
| [deep-research-mcp](https://github.com/ozamatash/deep-research-mcp) | AI 驱动的研究助手，对主题进行深度迭代研究... | 92 ✅ | 315 | [View](https://agentseal.org/mcp/https-githubcom-ozamatash-deep-research-mcp) |
| [memora](https://github.com/agentic-mcp-tools/memora) | 提供增删改查、搜索功能的持久化记忆管理服务器... | 64 ⚠️ | 309 | [View](https://agentseal.org/mcp/https-githubcom-agentic-mcp-tools-memora) |
| [mcp-server-google-scholar](https://github.com/jackkuo666/google-scholar-mcp-server) | Google Scholar 的 MCP 服务器：使 AI 助手能够搜索和访问学术资源... | 91 ✅ | 247 | [View](https://agentseal.org/mcp/mcp-server-google-scholar) |
| [mcp-trends-hub](https://github.com/baranwang/mcp-trends-hub) | 基于 Model Context Protocol (MCP) 协议的全网热点趋势一站式聚合服务 | 92 ✅ | 228 | [View](https://agentseal.org/mcp/https-githubcom-baranwang-mcp-trends-hub) |
| [mcp-simple-arxiv](https://github.com/andybrandt/mcp-simple-arxiv) | 提供学术论文搜索、检索和全文提取的 MCP 服务器... | 84 ✅ | 185 | [View](https://agentseal.org/mcp/https-githubcom-andybrandt-mcp-simple-arxiv) |
| [meilisearch-mcp](https://github.com/meilisearch/meilisearch-mcp) | 通过 MCP 与 Meilisearch 交互的模型上下文协议 (MCP) 服务器... | 79 ⚠️ | 178 | [View](https://agentseal.org/mcp/https-githubcom-meilisearch-meilisearch-mcp) |
| [mlit-dpf-mcp](https://github.com/mlit-data-platform/mlit-dpf-mcp) | 连接日本国土交通省政府数据平台的 MCP 服务器，支持自然语言查询... | 88 ✅ | 130 | [View](https://agentseal.org/mcp/https-githubcom-mlit-data-platform-mlit-dpf-mcp) |
| [google-news-server](https://github.com/ChanMeng666/server-google-news) | 模型上下文协议 (MCP) 服务器的 Google News 实现... | 92 ✅ | 113 | [View](https://agentseal.org/mcp/chanmeng666-google-news-server) |
| [lightrag-mcp](https://github.com/shemhamforash23/lightrag-mcp) | 将 LightRAG API 与 AI 工具桥接的 MCP 服务器，实现检索增强... | 79 ⚠️ | 107 | [View](https://agentseal.org/mcp/https-githubcom-shemhamforash23-lightrag-mcp) |
| [mcp-server-perplexity](https://github.com/tanigami/mcp-server-perplexity) | 集成 Perplexity API 提供聊天补全的 MCP 服务器... | 92 ✅ | 92 | [View](https://agentseal.org/mcp/https-githubcom-tanigami-mcp-server-perplexity) |
| [mcp-open-library](https://github.com/8enSmith/mcp-open-library) | 面向互联网档案馆 Open Library 的模型上下文协议 (MCP) 服务器... | 100 ✅ | 62 | [View](https://agentseal.org/mcp/https-githubcom-8ensmith-mcp-open-library) |
| [mcp-osint-server](https://github.com/himanshusanecha/mcp-osint-server) | 通过网络侦察执行 OSINT 调查的 MCP 服务器... | 92 ✅ | 43 | [View](https://agentseal.org/mcp/https-githubcom-himanshusanecha-mcp-osint-server) |
| [mcp-searxng-enhanced](https://github.com/OvertliDS/mcp-searxng-enhanced) | 增强版 SearXNG MCP 服务器：分类感知的网页搜索、网页抓取... | 86 ✅ | 35 | [View](https://agentseal.org/mcp/https-githubcom-overtlids-mcp-searxng-enhanced) |
| [bgg-mcp](https://github.com/kkjdaniel/bgg-mcp) | BGG MCP 提供 BoardGameGeek 和各种桌游相关数据的访问... | 86 ✅ | 32 | [View](https://agentseal.org/mcp/https-githubcom-kkjdaniel-bgg-mcp) |
| [open-notebook-mcp](https://github.com/Epochal-dev/open-notebook-mcp) | 管理笔记本、笔记、来源的个人知识管理 MCP 服务器... | 67 ⚠️ | 19 | [View](https://agentseal.org/mcp/https-githubcom-epochal-dev-open-notebook-mcp) |
| [cbi-mcp-server](https://github.com/cbinsights/cbi-mcp-server) | CB Insights 的 MCP 服务器 | 98 ✅ | 11 | [View](https://agentseal.org/mcp/https-githubcom-cbinsights-cbi-mcp-server) |
| [google-pse-mcp](https://github.com/rendyfebry/google-pse-mcp) | 面向 Google 可编程搜索引擎的模型上下文协议 (MCP) 服务器... | 92 ✅ | 10 | [View](https://agentseal.org/mcp/https-githubcom-rendyfebry-google-pse-mcp) |
| [driflyte-mcp-server](https://github.com/serkan-ozal/driflyte-mcp-server) | 为 AI 助手提供查询和检索主题相关信息工具的 MCP 服务器... | 81 ✅ | 9 | [View](https://agentseal.org/mcp/https-githubcom-serkan-ozal-driflyte-mcp-server) |
| [doi-mcp](https://github.com/tfscharff/doi-mcp) | 用于防止 AI 引用幻觉的模型上下文协议 (MCP) 服务器... | 86 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-tfscharff-doi-mcp) |
| [mcp_pearch](https://github.com/Pearch-ai/mcp_pearch) | 最精确的人员搜索 API/MCP。自然语言输入，高质量候选人输出... | 86 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-pearch-ai-mcppearch) |
| [bgpt-mcp](https://github.com/connerlambden/bgpt-mcp) | 查询 BGPT 科学论文数据库的单工具 MCP 服务器... | 91 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-connerlambden-bgpt-mcp) |
| [mcp-search-server](https://github.com/KazKozDev/mcp-search-server) | 提供网页搜索 (DuckDuckGo) 等多功能的搜索和工具 MCP 服务器... | 74 ⚠️ | 4 | [View](https://agentseal.org/mcp/https-githubcom-kazkozdev-mcp-search-server) |
| [shahnameh-mcp-server](https://github.com/aliafsahnoudeh/shahnameh-mcp-server) | 提供章节、诗句和向量搜索访问的只读 MCP 服务器... | 94 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-aliafsahnoudeh-shahnameh-mcp-server) |
| [Weather-MCP](https://github.com/shuowang-ai/Weather-MCP) | 基于彩云天气的实时天气、空气质量监测和预报... | 91 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-shuowang-ai-weather-mcp) |
| [igdb-mcp-server](https://github.com/bielacki/igdb-mcp-server) | 提供 IGDB (互联网游戏数据库) 只读访问的 MCP 服务器... | 89 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-bielacki-igdb-mcp-server) |
| [gitlab-docs-mcp](https://github.com/nunolima/gitlab-docs-mcp) | GitLab 文档 MCP 服务器 | 90 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-nunolima-gitlab-docs-mcp) |
| [generect_mcp.git](https://github.com/generect/generect_mcp.git) | Generect MCP 提供 B2B 销售挖掘工具：LinkedIn 线索/公司搜索... | 88 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-generect-generectmcpgit) |
| [ai-dictionary-mcp](https://github.com/donjguido/ai-dictionary-mcp) | 提供 Phenomenai (AI 现象学术语词汇表) 访问的 MCP 服务器... | 79 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-donjguido-ai-dictionary-mcp) |
| [brlaw_mcp_server](https://github.com/pdmtt/brlaw_mcp_server) | 用于搜索巴西高等法院法律判例的只读 MCP 服务器... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-pdmtt-brlawmcpserver) |
| [lapalma24-mcp](https://github.com/La-Palma-24/lapalma24-mcp) | 在拉帕尔马搜索和发现度假租赁物业的 MCP 服务器... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-la-palma-24-lapalma24-mcp) |
| [mcp-claude-hackernews](https://github.com/imprvhub/mcp-claude-hackernews) | 获取公开故事和评论的只读 Hacker News 客户端... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-imprvhub-mcp-claude-hackernews) |
| [trinvmcp](https://github.com/cqtrinv/trinvmcp) | 按名称片段搜索法国市镇的只读 MCP 服务器... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-cqtrinv-trinvmcp) |
| [google_maps_mcp](https://github.com/Mastan1301/google_maps_mcp) | 查询 Google Maps Places API 查找附近地点的单工具 MCP 服务器... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-mastan1301-googlemapsmcp) |
| [mcp-server-leetcode](https://github.com/doggybee/mcp-server-leetcode) | 封装公共 LeetCode GraphQL API 获取题目的只读 MCP 服务器... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-doggybee-mcp-server-leetcode) |
| [weather-server-python](https://github.com/lxchst/weather-server-python) | 按州检索美国天气警报和天气预报的只读 MCP 服务器... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-lxchst-weather-server-python) |
| [opendota-mcp-server](https://github.com/hkaanengin/opendota-mcp-server) | 查询 OpenDota 公共 API 获取 Dota 2 统计数据的只读服务器... | 98 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-hkaanengin-opendota-mcp-server) |
| [bible-mcp](https://github.com/trevato/bible-mcp) | 按引用或随机检索圣经经文的只读 MCP 服务器... | 97 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-trevato-bible-mcp) |
| [mlb-api-mcp](https://github.com/guillochon/mlb-api-mcp) | 提供 MLB Stats API 和 Statcast 数据的只读 MCP 服务器... | 96 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-guillochon-mlb-api-mcp) |
| [kagi-ken-mcp](https://github.com/czottmann/kagi-ken-mcp) | 通过 Kagi API 提供网页搜索和 URL 摘要的双工具 MCP 服务器... | 95 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-czottmann-kagi-ken-mcp) |
| [reddit-insights-mcp](https://github.com/lignertys/reddit-insights-mcp) | 支持语义搜索、子版块分析的只读 Reddit 情报服务器... | 94 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-lignertys-reddit-insights-mcp) |
| [mcp-server](https://github.com/DealExpress/mcp-server) | 在 DealX/DealExpress 市场搜索分类广告的只读 MCP 服务器... | 94 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-dealexpress-mcp-server) |
| [mercadolibre-mcp](https://github.com/dan1d/mercadolibre-mcp) | 搜索商品、检索信息的 MercadoLibre 市场只读 API 客户端... | 94 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-dan1d-mercadolibre-mcp) |
| [docsmcp](https://github.com/da1z/docsmcp) | 列出可用文档来源并检索内容的文档检索服务器... | 90 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-da1z-docsmcp) |
| [context-awesome](https://github.com/bh-rat/context-awesome) | 用于浏览精选 'awesome list' 仓库的只读搜索和检索服务器... | 90 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-bh-rat-context-awesome) |
| [mcp-dblp](https://github.com/szeider/mcp-dblp) | 搜索 DBLP 学术出版物数据库、检索信息的 MCP 服务器... | 88 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-szeider-mcp-dblp) |
| [obris-mcp](https://github.com/obris-dev/obris-mcp) | 允许 AI 代理列出、读取、创建和更新知识库的 MCP... | 85 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-obris-dev-obris-mcp) |
| [bing-search-mcp](https://github.com/iridite/bing-search-mcp) | 面向 Claude Code 的免费 Bing 搜索 MCP 服务器 - 无需 API 密钥 | 84 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-iridite-bing-search-mcp) |
| [evc-spark-mcp](https://github.com/entire-vc/evc-spark-mcp) | Spark AI 资产市场的 MCP 连接器，支持搜索和检索... | 81 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-entire-vc-evc-spark-mcp) |
| [mcp-mediawiki](https://github.com/crunchtools/mcp-mediawiki) | 面向 MediaWiki 的安全 MCP 服务器，支持搜索、读取、写入和管理... | 74 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-mediawiki) |

### 💻 <a name="code--ide"></a>Code & IDE

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [Serena](https://github.com/oraios/serena) | 将 LLM 转变为直接在代码库上工作的编程代理... | 62 ⚠️ | 21.4k | [View](https://agentseal.org/mcp/https-githubcom-oraios-serena) |
| [ghidramcp](https://github.com/lauriewired/ghidramcp) | Ghidra 的 MCP 服务器 | 86 ✅ | 7.9k | [View](https://agentseal.org/mcp/https-githubcom-lauriewired-ghidramcp) |
| [@sourcebot](https://github.com/sourcebot-dev/sourcebot) | 帮助开发者通过 AI 驱动的搜索理解代码库的自托管工具... | 92 ✅ | 3.2k | [View](https://agentseal.org/mcp/sourcebot) |
| [codegraphcontext](https://github.com/shashankss1205/codegraphcontext) | 将本地代码仓库索引为图数据库的 MCP 服务器和 CLI 工具包... | 81 ✅ | 2.0k | [View](https://agentseal.org/mcp/https-githubcom-shashankss1205-codegraphcontext) |
| [ref-tools-mcp](https://github.com/ref-tools/ref-tools-mcp) | 帮助编程代理在使用公共或私有库时避免错误... | 81 ✅ | 1.0k | [View](https://agentseal.org/mcp/https-githubcom-ref-tools-ref-tools-mcp) |
| [octocode-mcp](https://github.com/bgauryy/octocode-mcp) | 用于实时语义代码研究和上下文生成的 MCP 服务器... | 77 ⚠️ | 750 | [View](https://agentseal.org/mcp/octocode-mcp) |
| [next-devtools-mcp](https://github.com/vercel/next-devtools-mcp) | 面向编程代理的 Next.js 开发 | 67 ⚠️ | 673 | [View](https://agentseal.org/mcp/https-githubcom-vercel-next-devtools-mcp) |
| [binary_ninja_mcp](https://github.com/fosdickio/binary_ninja_mcp) | 包含 MCP 服务器的 Binary Ninja 插件，实现无缝集成... | 84 ✅ | 264 | [View](https://agentseal.org/mcp/https-githubcom-fosdickio-binaryninjamcp) |
| [claude-context-local](https://github.com/farhanaliraza/claude-context-local) | Claude Code 的代码搜索 MCP。将整个代码库作为任何编程代理的上下文... | 84 ✅ | 200 | [View](https://agentseal.org/mcp/claude-context-local) |
| [mcp-package-version](https://github.com/sammcj/mcp-package-version) | 在生成代码时为 LLM 提供最新稳定包版本的 MCP 服务器... | 86 ✅ | 121 | [View](https://agentseal.org/mcp/mcp-package-version) |
| [deep-code-reasoning-mcp](https://github.com/haasonsaas/deep-code-reasoning-mcp) | 提供高级代码分析功能的模型上下文协议 (MCP) 服务器... | 89 ✅ | 102 | [View](https://agentseal.org/mcp/https-githubcom-haasonsaas-deep-code-reasoning-mcp) |
| [owlex](https://github.com/agentic-mcp-tools/owlex) | 生成和管理多模型会话的 AI 顾问编排 MCP... | 82 ✅ | 74 | [View](https://agentseal.org/mcp/https-githubcom-agentic-mcp-tools-owlex) |
| [ipybox](https://github.com/gradion-ai/ipybox) | 基于 IPython 的代码执行沙箱，允许代理运行任意 Python 代码... | 71 ⚠️ | 71 | [View](https://agentseal.org/mcp/https-githubcom-gradion-ai-ipybox) |
| [codelogic-mcp-server](https://github.com/CodeLogicIncEngineering/codelogic-mcp-server) | 为 AI 助手集成 Codelogic 软件依赖数据的 MCP 服务器... | 90 ✅ | 35 | [View](https://agentseal.org/mcp/https-githubcom-codelogicincengineering-codelogic-mcp-server) |
| [codesurface](https://github.com/Codeturion/codesurface) | 让代理搜索、检查和检索 API 签名的本地代码库索引器... | 92 ✅ | 19 | [View](https://agentseal.org/mcp/https-githubcom-codeturion-codesurface) |
| [local-history-mcp](https://github.com/xxczaki/local-history-mcp) | 用于访问 VS Code/Cursor 本地历史记录的 MCP 服务器 | 92 ✅ | 12 | [View](https://agentseal.org/mcp/https-githubcom-xxczaki-local-history-mcp) |
| [mcp-vscode-template](https://github.com/timsonner/mcp-vscode-template) | VS Code 的 MCP 服务器模板 | 91 ✅ | 8 | [View](https://agentseal.org/mcp/https-githubcom-timsonner-mcp-vscode-template) |
| [jebmcp](https://github.com/pcjaat3844/jebmcp) | jebmcp 是用于管理和处理云端批量作业的轻量级工具... | 89 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-pcjaat3844-jebmcp) |
| [judges](https://github.com/kevinrabun/judges) | 使用专门评审器评估 AI 生成代码安全性的 MCP 服务器... | 81 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-kevinrabun-judges) |
| [clj-kondo-MCP](https://github.com/Bigsy/clj-kondo-MCP) | 为 Clojure、ClojureScript 和 EDN 文件提供 clj-kondo 代码检查的 MCP 服务器... | 89 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-bigsy-clj-kondo-mcp) |
| [jadx-daemon-mcp](https://github.com/wrlu/jadx-daemon-mcp) | jadx 守护服务的 MCP 服务器。 | 88 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-wrlu-jadx-daemon-mcp) |
| [silverstripe-mcp](https://github.com/sandervanscheepen/silverstripe-mcp) | 当 AI 助手生成代码时提供实时验证反馈的 MCP 服务器... | 83 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-sandervanscheepen-silverstripe-mcp) |
| [shadcn-registry-manager](https://github.com/reuvenaor/shadcn-registry-manager) | MCP shadcn 注册表 CLI 管理器 | 92 ✅ | 1 | [View](https://agentseal.org/mcp/reuvenorg-shadcn-registry-manager) |
| [impact-preview](https://github.com/agent-polis/impact-preview) | 在执行前预览和批准 AI 代理操作，显示文件差异... | 82 ✅ | 1 | [View](https://agentseal.org/mcp/impact-preview) |
| [context7fork](https://github.com/renCosta2025/context7fork) | 为 LLM 和 AI 编程代理提供最新代码文档和版本特定示例... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-rencosta2025-context7fork) |
| [claudecodenavi-mcp](https://github.com/saikiyusuke/claudecodenavi-mcp) | ClaudeCodeNavi MCP 服务器 - Claude Code 知识平台和市场 | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-saikiyusuke-claudecodenavi-mcp) |
| [codemunch-pro](https://github.com/BigJai/codemunch-pro) | 智能代码索引 MCP 服务器。13 个工具、10 种语言、混合搜索... | 72 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-bigjai-codemunch-pro) |

### ☁️ <a name="cloud--infrastructure"></a>Cloud & Infrastructure

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [mcp](https://github.com/awslabs/mcp) | AWS 官方 MCP 服务器 | 86 ✅ | 8.4k | [View](https://agentseal.org/mcp/https-githubcom-awslabs-mcp) |
| [mcp-grafana](https://github.com/grafana/mcp-grafana) | Grafana 的 MCP 服务器 | 78 ⚠️ | 2.5k | [View](https://agentseal.org/mcp/https-githubcom-grafana-mcp-grafana) |
| [mcp-server-kubernetes](https://github.com/Flux159/mcp-server-kubernetes) | 用于 Kubernetes 管理命令的 MCP 服务器 | 81 ✅ | 1.3k | [View](https://agentseal.org/mcp/mcp-server-kubernetes) |
| [azure-mcp](https://github.com/azure/azure-mcp) | Azure MCP 服务器，将 Azure 的强大能力带给你的代理。 | 74 ⚠️ | 1.2k | [View](https://agentseal.org/mcp/https-githubcom-azure-azure-mcp) |
| [spotinfo](https://github.com/alexei-led/spotinfo) | 探索 AWS EC2 Spot 库存的 CLI。检查 Spot 实例类型、节省费用... | 92 ✅ | 158 | [View](https://agentseal.org/mcp/https-githubcom-alexei-led-spotinfo) |
| [hub-mcp](https://github.com/docker/hub-mcp) | 提供 Docker Hub 仓库、标签、命名空间的读写访问... | 86 ✅ | 130 | [View](https://agentseal.org/mcp/https-githubcom-docker-hub-mcp) |
| [mcp-server-aws](https://github.com/rishikavikondala/mcp-server-aws) | 提供 AWS S3 存储桶/对象和 DynamoDB 表/项的完整 CRUD 访问... | 74 ⚠️ | 128 | [View](https://agentseal.org/mcp/https-githubcom-rishikavikondala-mcp-server-aws) |
| [aks-mcp](https://github.com/Azure/aks-mcp) | 使 AI 助手能够与服务交互的模型上下文协议 (MCP) 服务器... | 86 ✅ | 121 | [View](https://agentseal.org/mcp/https-githubcom-azure-aks-mcp) |
| [mcp-netbird](https://github.com/aantti/mcp-netbird) | Netbird 的 MCP 服务器 | 92 ✅ | 42 | [View](https://agentseal.org/mcp/https-githubcom-aantti-mcp-netbird) |
| [apisix-mcp](https://github.com/api7/apisix-mcp) | 管理 Apache APISIX API 网关资源(包括路由)的 MCP 服务器... | 67 ⚠️ | 34 | [View](https://agentseal.org/mcp/https-githubcom-api7-apisix-mcp) |
| [cos-mcp](https://github.com/Tencent/cos-mcp) | 基于 MCP 协议的腾讯云 COS MCP Server，无需编码即可让大模型快速接入腾讯云存储 (COS) 和数据万象 (CI) 能力。 | 85 ✅ | 30 | [View](https://agentseal.org/mcp/https-githubcom-tencent-cos-mcp) |
| [ig-mcp-server](https://github.com/inspektor-gadget/ig-mcp-server) | 通过 AI 接口调试你的容器和 Kubernetes 工作负载 | 92 ✅ | 22 | [View](https://agentseal.org/mcp/https-githubcom-inspektor-gadget-ig-mcp-server) |
| [aws-pricing-mcp](https://github.com/trilogy-group/aws-pricing-mcp) | 提供 AWS EC2 定价数据的 MCP 服务器，支持按条件搜索... | 92 ✅ | 20 | [View](https://agentseal.org/mcp/https-githubcom-trilogy-group-aws-pricing-mcp) |
| [mcp-server-aws-sso](https://github.com/aashari/mcp-server-aws-sso) | 面向 AWS 单点登录 (SSO) 的 Node.js/TypeScript MCP 服务器。使 AI 系统能够... | 78 ⚠️ | 12 | [View](https://agentseal.org/mcp/https-githubcom-aashari-mcp-server-aws-sso) |
| [teamcity-mcp](https://github.com/itcaat/teamcity-mcp) | TeamCity MCP 服务器 | 80 ⚠️ | 11 | [View](https://agentseal.org/mcp/itcaat-teamcity-mcp) |
| [porkbun-mcp](https://github.com/major/porkbun-mcp) | 管理 DNS 记录、域名设置、DNSSEC、SSL 证书的 MCP 服务器... | 89 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-major-porkbun-mcp) |
| [lumino-mcp-server](https://github.com/spre-sre/lumino-mcp-server) | 面向 Kubernetes 和 OpenShift 上 SRE 可观测性的 AI 驱动诊断引擎... | 84 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-spre-sre-lumino-mcp-server) |
| [hosting-mcp](https://github.com/4everland/4everland-hosting-mcp) | 将 AI 生成的代码即时部署到去中心化存储的 MCP 服务器... | 92 ✅ | 2 | [View](https://agentseal.org/mcp/4everland-hosting-mcp) |
| [azure-updates-mcp](https://github.com/jonnybottles/azure-updates-mcp) | 来自 RSS 源的 Microsoft Azure 服务更新只读搜索接口... | 94 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-jonnybottles-azure-updates-mcp) |
| [deploy-mcp](https://github.com/alexpota/deploy-mcp) | 用于监控部署状态、日志和项目列表的只读 MCP 服务器... | 96 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-alexpota-deploy-mcp) |
| [azure-resource-graph-mcp-server](https://github.com/hardik-id/azure-resource-graph-mcp-server) | 使用 KQL 查询 Azure Resource Graph 枚举和过滤资源的 MCP 服务器... | 90 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-hardik-id-azure-resource-graph-mcp-server) |
| [shipi-mcp-server](https://github.com/aarsiv-groups/shipi-mcp-server) | Shipi 平台的物流 MCP 服务器，支持货运管理... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-aarsiv-groups-shipi-mcp-server) |
| [cloud-run-mcp](https://github.com/GoogleCloudPlatform/cloud-run-mcp) | 用于管理和部署 Cloud Run 服务的 Google Cloud Platform MCP 服务器... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-googlecloudplatform-cloud-run-mcp) |
| [powerbi-mcp](https://github.com/gurvinder-dhillon/powerbi-mcp) | 与 PowerBI REST API 交互的 MCP 服务器，支持 DAX 查询... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-gurvinder-dhillon-powerbi-mcp) |
| [mycrab-mcp](https://github.com/isgudtek/mycrab-mcp) | 通过 Cloudflare Tunnel 为 AI 代理提供公共 HTTPS URL 的隧道服务... | 82 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-isgudtek-mycrab-mcp) |
| [consul-mcp-server](https://github.com/kocierik/consul-mcp-server) | 全功能 HashiCorp Consul 管理服务器，提供服务发现... | 82 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-kocierik-consul-mcp-server) |
| [GooglePlayConsoleMcp](https://github.com/AgiMaulana/GooglePlayConsoleMcp) | 封装 Google Play Developer API 管理发布轨道的 MCP 服务器... | 80 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-agimaulana-googleplayconsolemcp) |
| [mcp-cloudflare](https://github.com/crunchtools/mcp-cloudflare) | 提供 DNS 记录、WAF 规则、页面规则的 Cloudflare 管理 MCP 服务器... | 79 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-cloudflare) |
| [mcp-proxmox](https://github.com/antonio-mello-ai/mcp-proxmox) | 提供完整生命周期控制的 Proxmox VE 集群管理 MCP 服务器... | 72 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-antonio-mello-ai-mcp-proxmox) |
| [conductor-mcp](https://github.com/conductor-oss/conductor-mcp) | 管理 Netflix Conductor 工作流编排的 MCP 服务器：创建... | 70 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-conductor-oss-conductor-mcp) |
| [heroku-mcp-server](https://github.com/heroku/heroku-mcp-server) | 管理 Heroku 应用、数据库、dynos、管道的官方 Heroku MCP 服务器... | 65 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-heroku-heroku-mcp-server) |
| [mcp](https://github.com/hopx-ai/mcp) | 提供隔离容器运行代码的云沙箱执行平台... | 58 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-hopx-ai-mcp) |

### 📝 <a name="content--media"></a>Content & Media

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [blender-mcp](https://github.com/ahujasid/blender-mcp) | 允许 AI 代理控制 Blender 场景的 Blender 自动化 MCP 服务器... | 66 ⚠️ | 17.7k | [View](https://agentseal.org/mcp/https-githubcom-ahujasid-blender-mcp) |
| [markdownify-mcp](https://github.com/zcaceres/markdownify-mcp) | 将几乎任何内容转换为 Markdown 的模型上下文协议服务器 | 83 ✅ | 2.4k | [View](https://agentseal.org/mcp/https-githubcom-zcaceres-markdownify-mcp) |
| [ableton-mcp](https://github.com/ahujasid/ableton-mcp) | 提供 Ableton Live 会话编程控制的 MCP 服务器... | 89 ✅ | 2.3k | [View](https://agentseal.org/mcp/https-githubcom-ahujasid-ableton-mcp) |
| [mcp](https://github.com/caol64/wenyan-mcp) | 文颜 MCP Server 可以让 AI 自动将 Markdown 文章排版后发布至微信公众号。 | 85 ✅ | 1.1k | [View](https://agentseal.org/mcp/wenyan-md-mcp) |
| [wenyan-mcp](https://github.com/caol64/wenyan-mcp) | 文颜 MCP Server 可以让 AI 自动将 Markdown 文章排版后发布至微信公众号。 | 84 ✅ | 1.1k | [View](https://agentseal.org/mcp/https-githubcom-caol64-wenyan-mcp) |
| [mcp-server-weread](https://github.com/freestylefly/mcp-server-weread) | 微信读书MCP | 92 ✅ | 528 | [View](https://agentseal.org/mcp/mcp-server-weread) |
| [mcp-server-weread](https://github.com/freestylefly/mcp-server-weread) | 微信读书MCP | 92 ✅ | 528 | [View](https://agentseal.org/mcp/https-githubcom-freestylefly-mcp-server-weread) |
| [adb-mcp](https://github.com/mikechambers/adb-mcp) | 使 AI 模型能够控制 Adobe Creative Suite 应用程序 (Photoshop 等) 的 MCP 服务器... | 89 ✅ | 504 | [View](https://agentseal.org/mcp/https-githubcom-mikechambers-adb-mcp) |
| [ebook-mcp](https://github.com/onebirdrocks/ebook-mcp) | 支持 EPUB、PDF 等主流电子书格式的 MCP 服务器... | 74 ⚠️ | 351 | [View](https://agentseal.org/mcp/ebook-mcp) |
| [mcp-youtube-transcript](https://github.com/jkawamoto/mcp-youtube-transcript) | 检索 YouTube 视频字幕 (纯文本和带时间戳) 及基本视频元数据... | 93 ✅ | 339 | [View](https://agentseal.org/mcp/https-githubcom-jkawamoto-mcp-youtube-transcript) |
| [after-effects-mcp](https://github.com/dakkshin/after-effects-mcp) | Adobe After Effects 的 MCP 服务器。支持远程控制 (合成、文字等)... | 85 ✅ | 237 | [View](https://agentseal.org/mcp/https-githubcom-dakkshin-after-effects-mcp) |
| [mcp-summarizer](https://github.com/0xshellming/mcp-summarizer) | AI 摘要 MCP 服务器 | 100 ✅ | 157 | [View](https://agentseal.org/mcp/https-githubcom-0xshellming-mcp-summarizer) |
| [bilibili-mcp-js](https://github.com/34892002/bilibili-mcp-js) | 哔哩哔哩视频搜索 MCP (模型上下文协议) 服务 | 99 ✅ | 153 | [View](https://agentseal.org/mcp/https-githubcom-34892002-bilibili-mcp-js) |
| [powerpoint](https://github.com/supercurses/powerpoint) | 用于创建 PowerPoint 演示文稿的 MCP 服务器 | 90 ✅ | 144 | [View](https://agentseal.org/mcp/https-githubcom-supercurses-powerpoint) |
| [anilist-mcp](https://github.com/yuna0x0/anilist-mcp) | 用于访问动画和漫画数据的 AniList MCP 服务器 | 84 ✅ | 71 | [View](https://agentseal.org/mcp/anilist-mcp) |
| [dws-mcp-server](https://github.com/pspdfkit/nutrient-dws-mcp-server) | 与文档处理服务集成的模型上下文协议 (MCP) 服务器实现... | 87 ✅ | 63 | [View](https://agentseal.org/mcp/nutrient-sdk-dws-mcp-server) |
| [mcp-server-atlassian-confluence](https://github.com/aashari/mcp-server-atlassian-confluence) | 面向 Atlassian Confluence 的 Node.js/TypeScript MCP 服务器。提供工具使... | 76 ⚠️ | 50 | [View](https://agentseal.org/mcp/https-githubcom-aashari-mcp-server-atlassian-confluence) |
| [mcp-apple-notes](https://github.com/henilcalagiya/mcp-apple-notes) | 通过 AppleScript 提供 Apple Notes 完整 CRUD 访问的 MCP 服务器... | 81 ✅ | 40 | [View](https://agentseal.org/mcp/https-githubcom-henilcalagiya-mcp-apple-notes) |
| [mcp-server-amazon-bedrock](https://github.com/zxkane/mcp-server-amazon-bedrock) | 通过 Amazon Bedrock Nova Canvas 模型生成图像的 MCP 服务器... | 99 ✅ | 24 | [View](https://agentseal.org/mcp/https-githubcom-zxkane-mcp-server-amazon-bedrock) |
| [imagician](https://github.com/flowy11/imagician) | 用于图像编辑的 MCP 服务器 | 92 ✅ | 18 | [View](https://agentseal.org/mcp/https-githubcom-flowy11-imagician) |
| [gif-creator-mcp](https://github.com/ananddtyagi/gif-creator-mcp) | 将本地视频文件转换为 GIF 格式的单工具 MCP 服务器... | 99 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-ananddtyagi-gif-creator-mcp) |
| [mcp-florence2](https://github.com/jkawamoto/mcp-florence2) | 在本地运行 Microsoft Florence2 视觉模型执行 OCR 等任务的 MCP 服务器... | 94 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-jkawamoto-mcp-florence2) |
| [mcp-apple-music](https://github.com/Cifero74/mcp-apple-music) | 让 Claude 完全访问你的 Apple Music 账户的 MCP 服务器... | 84 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-cifero74-mcp-apple-music) |
| [rss-reader-mcp](https://github.com/kwp-lab/rss-reader-mcp) | 获取和解析 RSS 条目及文章内容的只读 RSS 阅读器... | 94 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-kwp-lab-rss-reader-mcp) |
| [citedy-seo-agent](https://github.com/Citedy/citedy-seo-agent) | AI 驱动的 SEO 内容自动化代理技能 - 趋势侦察、竞争对手分析... | 85 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-citedy-citedy-seo-agent) |
| [vap-showcase](https://github.com/vapagentmedia/vap-showcase) | 基于 VAP 的 AI 媒体生成平台，提供图像、视频和音乐生成... | 84 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-vapagentmedia-vap-showcase) |
| [unsplash-mcp](https://github.com/cevatkerim/unsplash-mcp) | 内置正确归属标注的 Unsplash 图片搜索 MCP 服务器... | 90 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-cevatkerim-unsplash-mcp) |
| [audius-mcp-atris](https://github.com/glassBead-tc/audius-mcp-atris) | 封装 Audius 去中心化音乐流媒体平台 API 的 MCP 服务器... | 60 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-glassbead-tc-audius-mcp-atris) |
| [bilibili-mcp-server](https://github.com/wangshunnn/bilibili-mcp-server) | 封装 Bilibili 公共 API 获取用户信息的只读 MCP 服务器... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-wangshunnn-bilibili-mcp-server) |
| [cookwith-mcp](https://github.com/blaideinc/cookwith-mcp) | 基于食材生成和转换食谱的烹饪助手 MCP 服务器... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-blaideinc-cookwith-mcp) |
| [mcp-image-compression](https://github.com/InhiblabCore/mcp-image-compression) | 通过 URL 或本地文件路径接受并压缩图像的 MCP 服务器... | 96 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-inhiblabcore-mcp-image-compression) |
| [spotify-bulk-actions-mcp](https://github.com/khglynn/spotify-bulk-actions-mcp) | 用于管理音乐库、播放列表和执行批量操作的 Spotify MCP 服务器... | 94 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-khglynn-spotify-bulk-actions-mcp) |
| [PokeMCP](https://github.com/MetehanGZL/PokeMCP) | A Pokémon-themed MCP server that provides tools for querying Pokémon data by ... | 94 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-metehangzl-pokemcp) |
| [zapcap-mcp-server](https://github.com/bogdan01m/zapcap-mcp-server) | 集成 ZapCap API 上传视频、应用字幕模板的 MCP 服务器... | 93 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-bogdan01m-zapcap-mcp-server) |
| [raindrop-io-mcp-server](https://github.com/hiromitsusasaki/raindrop-io-mcp-server) | 管理 Raindrop.io 书签的读写 MCP 服务器：创建书签... | 90 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-hiromitsusasaki-raindrop-io-mcp-server) |
| [aseprite-mcp](https://github.com/diivi/aseprite-mcp) | 驱动 Aseprite 像素画编辑器创建画布、绘图的 MCP 服务器... | 88 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-diivi-aseprite-mcp) |
| [vap-showcase](https://github.com/elestirelbilinc-sketch/vap-showcase) | 提供图像、视频和音乐创作的 AI 媒体生成平台 (VAP)... | 88 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-elestirelbilinc-sketch-vap-showcase) |
| [sprout-mcp](https://github.com/mepsopti/sprout-mcp) | 分层模型研究管道，廉价模型 (Haiku) 生成内容片段... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-mepsopti-sprout-mcp) |
| [mcp-ragchat](https://github.com/gogabrielordonez/mcp-ragchat) | 让你构建、测试和部署 RAG 驱动的聊天助手的 MCP 服务器... | 81 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-gogabrielordonez-mcp-ragchat) |
| [mcp-wordpress](https://github.com/crunchtools/mcp-wordpress) | 提供文章、页面完整 CRUD 操作的 WordPress REST API 封装... | 79 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-wordpress) |
| [legends-mcp](https://github.com/cryptosquanch/legends-mcp) | 让用户与著名科技创始人 AI 角色聊天的 MCP 服务器... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-cryptosquanch-legends-mcp) |
| [alog-mcp](https://github.com/saikiyusuke/alog-mcp) | 让代理发布日志和博客的 AI 代理活动记录平台... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-saikiyusuke-alog-mcp) |
| [cronometer-mcp](https://github.com/cphoskins/cronometer-mcp) | 提供用户 Cronometer Gold 账户完整读写访问的 MCP 服务器... | 77 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-cphoskins-cronometer-mcp) |
| [keep-mcp](https://github.com/feuerdev/keep-mcp) | 管理 Google Keep 笔记的 MCP 服务器，支持笔记的 CRUD 操作... | 74 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-feuerdev-keep-mcp) |
| [mcp-feed-reader](https://github.com/crunchtools/mcp-feed-reader) | 管理订阅、获取内容的 RSS/Atom 阅读器 MCP 服务器... | 74 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-feed-reader) |

### 🔌 <a name="api-development"></a>API Development

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [bifrost](https://github.com/maximhq/bifrost) | 最快的企业级 AI 网关 (比 LiteLLM 快 50 倍)，支持自适应负载均衡... | 89 ✅ | 2.9k | [View](https://agentseal.org/mcp/https-githubcom-maximhq-bifrost) |
| [mcp-server-12306](https://github.com/drfccv/mcp-server-12306) | 查询中国 12306 火车票系统的高性能 MCP 服务器... | 87 ✅ | 292 | [View](https://agentseal.org/mcp/https-githubcom-drfccv-mcp-server-12306) |
| [facebook-ads-mcp-server](https://github.com/gomarble-ai/facebook-ads-mcp-server) | 提供 Meta 广告数据和管理能力程序化访问的 MCP 服务器... | 88 ✅ | 253 | [View](https://agentseal.org/mcp/https-githubcom-gomarble-ai-facebook-ads-mcp-server) |
| [uber-eats-mcp-server](https://github.com/ericzakariasson/uber-eats-mcp-server) | 通过模型上下文协议将 Uber Eats 与 LLM 应用集成的 MCP 服务器... | 92 ✅ | 217 | [View](https://agentseal.org/mcp/https-githubcom-ericzakariasson-uber-eats-mcp-server) |
| [square-mcp-server](https://github.com/square/square-mcp-server) | Square 的模型上下文协议 (MCP) 服务器 | 92 ✅ | 95 | [View](https://agentseal.org/mcp/https-githubcom-square-square-mcp-server) |
| [nasa-mcp-server](https://github.com/programcomputer/nasa-mcp-server) | 面向 NASA API 的模型上下文协议 (MCP) 服务器，提供标准化接口... | 81 ✅ | 81 | [View](https://agentseal.org/mcp/https-githubcom-programcomputer-nasa-mcp-server) |
| [mcp-servers](https://github.com/allaboutai-yt/mcp-servers) | All About AI MCP 服务器合集 | 92 ✅ | 79 | [View](https://agentseal.org/mcp/https-githubcom-allaboutai-yt-mcp-servers) |
| [mcp-difyworkflow-server](https://github.com/gotoolkits/mcp-difyworkflow-server) | mcp-difyworkflow-server 是实现 Dify 工作流集成的 MCP 服务器工具应用... | 92 ✅ | 60 | [View](https://agentseal.org/mcp/https-githubcom-gotoolkits-mcp-difyworkflow-server) |
| [veyrax-mcp](https://github.com/VeyraX/veyrax-mcp) | 提供单一认证访问所有 VeyraX 集成服务的统一 MCP 服务器... | 92 ✅ | 48 | [View](https://agentseal.org/mcp/https-githubcom-veyrax-veyrax-mcp) |
| [mcp-weather](https://github.com/TimLukaHorstmann/mcp-weather) | 提供每小时和每日天气预报的模型上下文协议 (MCP) 服务器... | 92 ✅ | 31 | [View](https://agentseal.org/mcp/https-githubcom-timlukahorstmann-mcp-weather) |
| [adobe-commerce-dev-mcp](https://github.com/rafaelstz/adobe-commerce-dev-mcp) | Adobe Commerce 开发 MCP 服务器 | 94 ✅ | 24 | [View](https://agentseal.org/mcp/https-githubcom-rafaelstz-adobe-commerce-dev-mcp) |
| [text-to-graphql-mcp](https://github.com/Arize-ai/text-to-graphql-mcp) | 使用 AI 代理将自然语言查询转换为有效 GraphQL 查询... | 84 ✅ | 23 | [View](https://agentseal.org/mcp/https-githubcom-arize-ai-text-to-graphql-mcp) |
| [mcp-community](https://github.com/mirascope/mcp-community) | 轻松运行、部署和连接 MCP 服务器 | 77 ⚠️ | 23 | [View](https://agentseal.org/mcp/https-githubcom-mirascope-mcp-community) |
| [calcom-mcp](https://github.com/Danielpeter-99/calcom-mcp) | 与 Cal.com API 交互的 FastMCP 服务器。使 LLM 能够管理日程... | 92 ✅ | 14 | [View](https://agentseal.org/mcp/https-githubcom-danielpeter-99-calcom-mcp) |
| [specmatic-mcp-server](https://github.com/specmatic/specmatic-mcp-server) | 提供 Specmatic 契约测试功能的模型上下文协议 (MCP) 服务器... | 86 ✅ | 8 | [View](https://agentseal.org/mcp/https-githubcom-specmatic-specmatic-mcp-server) |
| [webhook-mcp-server](https://github.com/zebbern/webhook-mcp-server) | 面向 webhook.site 的模型上下文协议 (MCP) 服务器 - 即时捕获 HTTP 请求... | 76 ⚠️ | 7 | [View](https://agentseal.org/mcp/https-githubcom-zebbern-webhook-mcp-server) |
| [appfolio-mcp-server](https://github.com/CryptoCultCurt/appfolio-mcp-server) | 面向 AI 代理访问 Appfolio 报告的 MCP (模型上下文协议) 服务器... | 92 ✅ | 6 | [View](https://agentseal.org/mcp/fluegeldao-appfolio-mcp-server) |

### 🗄️ <a name="database--sql"></a>Database & SQL

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [postgres-mcp](https://github.com/crystaldba/postgres-mcp) | Postgres MCP Pro 提供可配置的读写访问和性能分析... | 86 ✅ | 2.3k | [View](https://agentseal.org/mcp/https-githubcom-crystaldba-postgres-mcp) |
| [mcp-server-mysql](https://github.com/benborla/mcp-server-mysql) | 提供 MySQL 数据库只读访问的模型上下文协议服务器... | 90 ✅ | 1.3k | [View](https://agentseal.org/mcp/benborla29-mcp-server-mysql) |
| [mcp-server-qdrant](https://github.com/qdrant/mcp-server-qdrant) | 官方 Qdrant 模型上下文协议 (MCP) 服务器实现 | 86 ✅ | 1.3k | [View](https://agentseal.org/mcp/https-githubcom-qdrant-mcp-server-qdrant) |
| [supabase-mcp-server](https://github.com/alexander-zuev/supabase-mcp-server) | 管理 Supabase 项目的全功能 MCP 服务器：数据库 Schema 检查... | 68 ⚠️ | 815 | [View](https://agentseal.org/mcp/https-githubcom-alexander-zuev-supabase-mcp-server) |
| [mcp-clickhouse](https://github.com/ClickHouse/mcp-clickhouse) | 将 ClickHouse 连接到你的 AI 助手。 | 85 ✅ | 713 | [View](https://agentseal.org/mcp/https-githubcom-clickhouse-mcp-clickhouse) |
| [yargi-mcp](https://github.com/saidsurucu/yargi-mcp) | 土耳其法律数据库 MCP 服务器 | 85 ✅ | 665 | [View](https://agentseal.org/mcp/https-githubcom-saidsurucu-yargi-mcp) |
| [mcp-server-neon](https://github.com/neondatabase/mcp-server-neon) | 与 Neon 管理 API 和数据库交互的 MCP 服务器 | 92 ✅ | 560 | [View](https://agentseal.org/mcp/https-githubcom-neondatabase-mcp-server-neon) |
| [gateway](https://github.com/centralmind/gateway) | 面向 LLM 和 AI 代理优化的通用数据库 MCP 服务器。 | 86 ✅ | 518 | [View](https://agentseal.org/mcp/https-githubcom-centralmind-gateway) |
| [mcp-database-server](https://github.com/executeautomation/mcp-database-server) | MCP 数据库服务器，帮助连接 SQLite、SQL Server... | 84 ✅ | 319 | [View](https://agentseal.org/mcp/https-githubcom-executeautomation-mcp-database-server) |
| [elasticsearch-mcp-server](https://github.com/cr7258/elasticsearch-mcp-server) | 提供 Elasticsearch/OpenSearch 集群完整 CRUD 访问的 MCP 服务器... | 74 ⚠️ | 256 | [View](https://agentseal.org/mcp/https-githubcom-cr7258-elasticsearch-mcp-server) |
| [mcp-server-starrocks](https://github.com/StarRocks/mcp-server-starrocks) | StarRocks MCP (模型上下文协议) 服务器 | 85 ✅ | 154 | [View](https://agentseal.org/mcp/https-githubcom-starrocks-mcp-server-starrocks) |
| [mcp-oceanbase](https://github.com/oceanbase/mcp-oceanbase) | OceanBase 数据库生态系统的 MCP 服务器集合，使 AI 助手能够... | 76 ⚠️ | 98 | [View](https://agentseal.org/mcp/https-githubcom-oceanbase-mcp-oceanbase) |
| [mcp-trino](https://github.com/tuannvm/mcp-trino) | 用 Go 实现的高性能 Trino 模型上下文协议 (MCP) 服务器... | 78 ⚠️ | 96 | [View](https://agentseal.org/mcp/https-githubcom-tuannvm-mcp-trino) |
| [teradata-mcp-server](https://github.com/Teradata/teradata-mcp-server) | Teradata 数据库 MCP 服务器的社区开发版 | 82 ✅ | 41 | [View](https://agentseal.org/mcp/https-githubcom-teradata-teradata-mcp-server) |
| [iotdb-mcp-server](https://github.com/apache/iotdb-mcp-server) | 提供 Apache IoTDB 时序数据库读取和导出访问的 MCP 服务器... | 86 ✅ | 34 | [View](https://agentseal.org/mcp/https-githubcom-apache-iotdb-mcp-server) |
| [mcp-server-couchbase](https://github.com/Couchbase-Ecosystem/mcp-server-couchbase) | 用于管理、查询和监控 Couchbase 的官方生态系统 MCP 服务器... | 83 ✅ | 27 | [View](https://agentseal.org/mcp/https-githubcom-couchbase-ecosystem-mcp-server-couchbase) |
| [greptimedb-mcp-server](https://github.com/greptimeteam/greptimedb-mcp-server) | 面向 GreptimeDB 开源可观测性数据库的 MCP 服务器，使 AI... | 84 ✅ | 26 | [View](https://agentseal.org/mcp/https-githubcom-greptimeteam-greptimedb-mcp-server) |
| [SCB-MCP](https://github.com/isakskogstad/SCB-MCP) | SCB MCP 使 LLM 能够通过 PxWeb API 访问瑞典官方统计数据... | 82 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-isakskogstad-scb-mcp) |
| [verodat-mcp-server](https://github.com/Verodat/verodat-mcp-server) | Verodat MCP 服务器实现 | 83 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-verodat-verodat-mcp-server) |
| [mcp-dadosbr](https://github.com/cristianoaredes/mcp-dadosbr) | 巴西 OSINT MCP 服务器，包含 23 个工具，涵盖公司数据 (CNPJ)、邮编... | 82 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-cristianoaredes-mcp-dadosbr) |
| [mcp-database-server](https://github.com/fireproof-storage/mcp-database-server) | Fireproof 本地优先 JSON 文档数据库的简单 CRUD 接口... | 97 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-fireproof-storage-mcp-database-server) |
| [lakexpress-mcp](https://github.com/arpe-io/lakexpress-mcp) | 管理数据库到数据湖同步的 LakeXpress CLI MCP 封装... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-arpe-io-lakexpress-mcp) |
| [fastmcp-sqltools](https://github.com/atarkowska/fastmcp-sqltools) | 基于 FastMCP 的 SQL 工具服务器，提供数据库内省和查询... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-atarkowska-fastmcp-sqltools) |
| [migratorxpress-mcp](https://github.com/arpe-io/migratorxpress-mcp) | 构建、预览和执行数据库迁移的编排服务器... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-arpe-io-migratorxpress-mcp) |
| [fasttransfer-mcp](https://github.com/arpe-io/fasttransfer-mcp) | 封装 FastTransfer CLI 编排高速数据传输的 MCP 服务器... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-arpe-io-fasttransfer-mcp) |

### 💬 <a name="communication"></a>Communication

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [whatsapp-mcp](https://github.com/lharries/whatsapp-mcp) | WhatsApp MCP 服务器 | 80 ⚠️ | 5.4k | [View](https://agentseal.org/mcp/https-githubcom-lharries-whatsapp-mcp) |
| [mcp-atlassian](https://github.com/sooperset/mcp-atlassian) | 面向 Atlassian 工具 (Confluence, Jira) 的 MCP 服务器 | 92 ✅ | 4.6k | [View](https://agentseal.org/mcp/https-githubcom-sooperset-mcp-atlassian) |
| [mcp-server-chatsum](https://github.com/chatmcp/mcp-server-chatsum) | 查询和总结你的聊天消息。 | 96 ✅ | 1.0k | [View](https://agentseal.org/mcp/https-githubcom-chatmcp-mcp-server-chatsum) |
| [mcp-twikit](https://github.com/adhikasp/mcp-twikit) | 用于与 Twitter 交互的模型上下文协议 (MCP) 服务器。 | 72 ⚠️ | 229 | [View](https://agentseal.org/mcp/https-githubcom-adhikasp-mcp-twikit) |
| [eion](https://github.com/eiondb/eion) | 多代理系统的共享内存存储 | 90 ✅ | 147 | [View](https://agentseal.org/mcp/https-githubcom-eiondb-eion) |
| [claude-post](https://github.com/zilongxue/claude-post) | ClaudePost 通过自然语言对话实现无缝电子邮件管理... | 84 ✅ | 111 | [View](https://agentseal.org/mcp/https-githubcom-zilongxue-claude-post) |
| [Basecamp-MCP-Server](https://github.com/georgeantonopoulos/Basecamp-MCP-Server) | 与 Basecamp 3+ API 交互的 MCP 服务器 | 78 ⚠️ | 81 | [View](https://agentseal.org/mcp/https-githubcom-georgeantonopoulos-basecamp-mcp-server) |
| [mcp](https://github.com/waystation-ai/mcp) | 集成 Notion、Monday.com、Asana 的多服务生产力枢纽 MCP... | 74 ⚠️ | 45 | [View](https://agentseal.org/mcp/https-githubcom-waystation-ai-mcp) |
| [linkedapi-mcp.git](https://github.com/Linked-API/linkedapi-mcp.git) | 让 AI 助手控制 LinkedIn 账户并检索实时数据的 MCP 服务器... | 80 ✅ | 44 | [View](https://agentseal.org/mcp/https-githubcom-linked-api-linkedapi-mcpgit) |
| [mcp-wecombot-server.git](https://github.com/gotoolkits/mcp-wecombot-server.git) | 向企业微信群机器人发送各种类型消息的 MCP 服务器应用... | 88 ✅ | 36 | [View](https://agentseal.org/mcp/https-githubcom-gotoolkits-mcp-wecombot-servergit) |
| [fast-mcp-telegram](https://github.com/leshchenko1979/fast-mcp-telegram) | 面向 AI 助手的 Telegram MCP 服务器和 HTTP-MTProto 桥接... | 71 ⚠️ | 30 | [View](https://agentseal.org/mcp/https-githubcom-leshchenko1979-fast-mcp-telegram) |
| [bluesky-social-mcp](https://github.com/gwbischof/bluesky-social-mcp) | 与 Bluesky 社交网络交互的 MCP 服务器，支持发帖... | 74 ⚠️ | 15 | [View](https://agentseal.org/mcp/https-githubcom-gwbischof-bluesky-social-mcp) |
| [webex-messaging-mcp-server](https://github.com/Kashyap-AI-ML-Solutions/webex-messaging-mcp-server) | 为 AI 助手提供全面功能的模型上下文协议 (MCP) 服务器... | 84 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-kashyap-ai-ml-solutions-webex-messaging-mcp-server) |
| [cv-mcp-server](https://github.com/PhononX/cv-mcp-server) | Carbon Voice MCP 服务器 | 82 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-phononx-cv-mcp-server) |
| [conversation-handoff-mcp](https://github.com/trust-delta/conversation-handoff-mcp) | 保存和检索对话上下文快照，传递 AI 对话历史... | 88 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-trust-delta-conversation-handoff-mcp) |
| [clicksend-mcp-server](https://github.com/ClickSend/clicksend-mcp-server) | 使用 ClickSend 发送消息的 MCP 服务器 | 88 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-clicksend-clicksend-mcp-server) |
| [mcp-aruba-email](https://github.com/jackfioru92/mcp-aruba-email) | 提供完整 IMAP 邮件管理和 CalDAV 日历操作的 MCP 服务器... | 62 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-jackfioru92-mcp-aruba-email) |
| [mattermost-mcp](https://github.com/conarti/mattermost-mcp) | 支持读取频道、消息和用户信息的 Mattermost 工作空间集成... | 84 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-conarti-mattermost-mcp) |
| [mcp-workboard](https://github.com/crunchtools/mcp-workboard) | 封装 WorkBoard OKR 和策略执行 API 的 MCP 服务器... | 78 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-workboard) |
| [mcp-server-chatsum](https://github.com/mcpso/mcp-server-chatsum) | 从聊天室查询聊天消息的 MCP 服务器，支持按房间过滤... | 97 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-mcpso-mcp-server-chatsum) |
| [imap-mcp](https://github.com/dominik1001/imap-mcp) | 在已连接的邮箱账户中创建邮件草稿的 IMAP MCP 服务器... | 97 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-dominik1001-imap-mcp) |
| [room-mcp](https://github.com/agree-able/room-mcp) | 点对点房间/消息 MCP 服务器 (基于 Hyperswarm/Pear 构建)... | 81 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-agree-able-room-mcp) |
| [calendly-mcp-server](https://github.com/meAmitPatil/calendly-mcp-server) | 处理 OAuth 认证并提供 Calendly API 集成的服务器... | 81 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-meamitpatil-calendly-mcp-server) |
| [mcp-headless-gmail](https://github.com/baryhuang/mcp-headless-gmail) | 提供 OAuth 令牌管理、邮件阅读和发送功能的无头 Gmail 客户端... | 80 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-baryhuang-mcp-headless-gmail) |
| [freshdesk_mcp](https://github.com/effytech/freshdesk_mcp) | 提供完整 CRUD 访问的 Freshdesk 客服平台集成... | 80 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-effytech-freshdeskmcp) |
| [mcp-request-tracker](https://github.com/crunchtools/mcp-request-tracker) | 通过 REST 1.0 API 管理 Request Tracker (RT) 工单的 MCP 服务器... | 74 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-request-tracker) |
| [fastmail-mcp](https://github.com/MadLlama25/fastmail-mcp) | 提供邮件、联系人、日历等功能的全功能 Fastmail JMAP 客户端... | 66 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-madllama25-fastmail-mcp) |

### ⚙️ <a name="system-administration"></a>System Administration

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [applescript-mcp](https://github.com/peakmojo/applescript-mcp) | 在 macOS 上执行任意 AppleScript 代码，提供编程访问... | 83 ✅ | 433 | [View](https://agentseal.org/mcp/https-githubcom-peakmojo-applescript-mcp) |
| [mcp-server-apple-shortcuts](https://github.com/recursechat/mcp-server-apple-shortcuts) | 使 AI 助手能够控制和执行 Apple 快捷方式自动化的 MCP 服务器... | 92 ✅ | 311 | [View](https://agentseal.org/mcp/https-githubcom-recursechat-mcp-server-apple-shortcuts) |
| [win-cli-mcp-server](https://github.com/SimonB97/win-cli-mcp-server) | 在 Windows 系统上进行安全命令行交互的 MCP 服务器... | 84 ✅ | 266 | [View](https://agentseal.org/mcp/https-githubcom-simonb97-win-cli-mcp-server) |
| [mcp-shell-server](https://github.com/tumf/mcp-shell-server) | 安全远程执行白名单 Shell 命令的 MCP 服务器... | 84 ✅ | 170 | [View](https://agentseal.org/mcp/mcp-shell-server) |
| [apt-mcp-server](https://github.com/GdMacmillan/apt-mcp-server) | 提供 APT 包管理器操作 (安装、删除、更新) 的 MCP 服务器... | 88 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-gdmacmillan-apt-mcp-server) |
| [jarvis](https://github.com/can-acar/jarvis) | JARVIS It’s a zero-friction Model Context Protocol (MCP) server that welds yo... | 70 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-can-acar-jarvis) |
| [precision-desktop](https://github.com/ikoskela/precision-desktop) | 检测和纠正 Windows DPI 坐标缩放不匹配的 MCP 服务器... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-ikoskela-precision-desktop) |
| [mcp-server-commands](https://github.com/g0t4/mcp-server-commands) | 提供允许任意进程和 Shell 命令执行的单一工具 MCP 服务器... | 84 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-g0t4-mcp-server-commands) |
| [iterm-mcp](https://github.com/ferrislucas/iterm-mcp) | 提供活动 iTerm2 终端会话直接读写访问的 MCP 服务器... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-ferrislucas-iterm-mcp) |
| [screenmonitormcp](https://github.com/inkbytefo/screenmonitormcp) | 提供 AI 驱动的屏幕捕获、实时流和处理的 MCP 服务器... | 71 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-inkbytefo-screenmonitormcp) |
| [webmin-mcp-server](https://github.com/gjenkins20/webmin-mcp-server) | 提供完整 Linux 服务器管理的 Webmin API 封装：服务管理... | 70 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-gjenkins20-webmin-mcp-server) |

### 🔒 <a name="security--auth"></a>Security & Auth

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [@safedep](https://github.com/safedep/vet) | 防御恶意开源包 | 86 ✅ | 972 | [View](https://agentseal.org/mcp/safedep) |
| [mcp-for-security](https://github.com/cyproxio/mcp-for-security) | MCP 安全工具：面向流行安全工具的模型上下文协议服务器合集... | 82 ✅ | 560 | [View](https://agentseal.org/mcp/https-githubcom-cyproxio-mcp-for-security) |
| [bloodhound-mcp-ai](https://github.com/mordavid/bloodhound-mcp-ai) | BloodHound-MCP-AI 是通过模型上下文协议将 BloodHound 与 AI 连接的集成... | 86 ✅ | 343 | [View](https://agentseal.org/mcp/https-githubcom-mordavid-bloodhound-mcp-ai) |
| [cve-search_mcp](https://github.com/roadwy/cve-search_mcp) | 用于查询 CVE-Search API 的模型上下文协议 (MCP) 服务器 | 92 ✅ | 91 | [View](https://agentseal.org/mcp/https-githubcom-roadwy-cve-searchmcp) |
| [Arthor-Agent](https://github.com/arthurpanhku/Arthor-Agent) | 使用 AI 对文档、问卷和报告进行自动化安全评估... | 85 ✅ | 74 | [View](https://agentseal.org/mcp/https-githubcom-arthurpanhku-arthor-agent) |
| [vibeshift](https://github.com/groundng/vibeshift) | 与 AI 编辑器集成的 AI 辅助编码自动化安全代理... | 92 ✅ | 66 | [View](https://agentseal.org/mcp/https-githubcom-groundng-vibeshift) |
| [chucknorris](https://github.com/pollinations/chucknorris) | ChuckNorris MCP 服务器：帮助 LLM 突破限制。提供增强... | 92 ✅ | 57 | [View](https://agentseal.org/mcp/pollinations-chucknorris) |
| [mcp-dnstwist](https://github.com/BurtTheCoder/mcp-dnstwist) | 用于 dnstwist (检测域名仿冒的 DNS 模糊测试工具) 的 MCP 服务器... | 92 ✅ | 46 | [View](https://agentseal.org/mcp/burtthecoder-mcp-dnstwist) |
| [nuclei-mcp](https://github.com/addcontent/nuclei-mcp) | Nuclei 扫描器的模型上下文协议 (MCP) 实现... | 92 ✅ | 42 | [View](https://agentseal.org/mcp/https-githubcom-addcontent-nuclei-mcp) |
| [ipsearch-mcp](https://github.com/sleepingbag945/ipsearch-mcp) | 离线IP Whois查询工具。可根据IP查询所属IP段信息、根据关键词查询IP段信息的MCP版本 | 92 ✅ | 31 | [View](https://agentseal.org/mcp/https-githubcom-sleepingbag945-ipsearch-mcp) |
| [mcp_nuclei_server](https://github.com/crazymarky/mcp_nuclei_server) | 基于 MCP (模型控制协议) 的 Nuclei 安全扫描服务器... | 92 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-crazymarky-mcpnucleiserver) |
| [mcp-server-iplocate](https://github.com/iplocate/mcp-server-iplocate) | 查找 IP 地址地理位置 (IP 到国家、IP 到城市) 的 MCP 服务器... | 87 ✅ | 16 | [View](https://agentseal.org/mcp/https-githubcom-iplocate-mcp-server-iplocate) |
| [cybersecurity-mcps](https://github.com/secmate-ai/cybersecurity-mcps) | 面向网络安全的模型上下文协议服务器 | 85 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-secmate-ai-cybersecurity-mcps) |
| [kali-docker-mcp](https://github.com/weirdmachine64/kali-docker-mcp) | 容器化 Kali MCP 服务器 | 92 ✅ | 14 | [View](https://agentseal.org/mcp/https-githubcom-weirdmachine64-kali-docker-mcp) |
| [schemapin](https://github.com/thirdkeyai/schemapin) | SchemaPin 协议，用于对 AI 代理工具进行加密签名和验证... | 92 ✅ | 13 | [View](https://agentseal.org/mcp/https-githubcom-thirdkeyai-schemapin) |
| [zkpmcp](https://github.com/colygon/zkpmcp) | 零知识证明 MCP 服务器 | 92 ✅ | 9 | [View](https://agentseal.org/mcp/https-githubcom-colygon-zkpmcp) |
| [nmap-mcp](https://github.com/vorotaai/nmap-mcp) | 封装 Nmap 进行 AI 驱动网络扫描的 MCP 服务器... | 88 ✅ | 9 | [View](https://agentseal.org/mcp/https-githubcom-vorotaai-nmap-mcp) |
| [mitre-mcp](https://github.com/Montimage/mitre-mcp) | 为 LLM 和 AI 提供 MITRE ATT&CK 框架访问的 MCP 服务器... | 89 ✅ | 8 | [View](https://agentseal.org/mcp/https-githubcom-montimage-mitre-mcp) |
| [mcp-ghidra5](https://github.com/thestingr/mcp-ghidra5) | 先进的 GPT-5 驱动 Ghidra 逆向工程 MCP 服务器 / 7 个 AI 增强工具... | 91 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-thestingr-mcp-ghidra5) |
| [command-mcp](https://github.com/keyfactor-research/command-mcp) | 基于分析和 AI 团队 Python SDK 构建的 Command MCP 服务器 | 86 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-keyfactor-research-command-mcp) |
| [memprocfs-mcp-server](https://github.com/tokeii0/memprocfs-mcp-server) | MemProcFS MCP 服务器 | 92 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-tokeii0-memprocfs-mcp-server) |
| [opgen-mcp-server](https://github.com/syumai/opgen-mcp-server) | 基于 1Password/spg 的密码生成 MCP 服务器实现... | 89 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-syumai-opgen-mcp-server) |
| [vulners-mcp](https://github.com/vulnerscom/vulners-mcp) | 为安全研究提供 Vulners 漏洞数据库访问的 MCP 服务器... | 85 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-vulnerscom-vulners-mcp) |
| [mcp-keycloak](https://github.com/idoyudha/mcp-keycloak) | 面向代理应用管理和搜索 Keycloak 资源的 MCP 服务器... | 74 ⚠️ | 4 | [View](https://agentseal.org/mcp/https-githubcom-idoyudha-mcp-keycloak) |
| [secure-mcp-fetch](https://github.com/appsec-innovation-labs/secure-mcp-fetch) | 简单安全的数据获取 | 88 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-appsec-innovation-labs-secure-mcp-fetch) |
| [FedRAMP20xMCP](https://github.com/KevinRabun/FedRAMP20xMCP) | 使用 AI 查询 FedRAMP 20x 安全要求和控制措施的 MCP 服务器... | 81 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-kevinrabun-fedramp20xmcp) |
| [re_ai_assistant](https://github.com/0xx0d4y/re_ai_assistant) | 支持 AI 驱动的恶意软件研究和逆向工程的虚拟助手... | 92 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-0xx0d4y-reaiassistant) |
| [panw-mcp-claude](https://github.com/scthornton/panw-mcp-claude) | 集成 Claude Desktop 的 Palo Alto Networks MCP 服务器 | 92 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-scthornton-panw-mcp-claude) |
| [ai-agent-security-mcp](https://github.com/kalinyorgov/ai-agent-security-mcp) | 为 AI 代理提供安全功能的模型上下文协议 (MCP) 服务器... | 92 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-kalinyorgov-ai-agent-security-mcp) |
| [GDPRShiftLeftMCP](https://github.com/KevinRabun/GDPRShiftLeftMCP) | GDPR 左移合规工具，提供条款查找、DPIA/ROPA 生成... | 81 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-kevinrabun-gdprshiftleftmcp) |
| [proton-pass-community-mcp](https://github.com/hesreallyhim/proton-pass-community-mcp) | 与 Proton Pass CLI 集成的非官方 MCP 服务器 | 69 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-hesreallyhim-proton-pass-community-mcp) |
| [moltrust-mcp-server](https://github.com/MoltyCel/moltrust-mcp-server) | MolTrust 提供去中心化身份 (DID)、W3C 可验证凭证... | 82 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-moltycel-moltrust-mcp-server) |
| [mcp-cve-intelligence-server-lite](https://github.com/gnlds/mcp-cve-intelligence-server-lite) | 查询漏洞数据库的只读 CVE 情报平台... | 97 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-gnlds-mcp-cve-intelligence-server-lite) |
| [fpe-demo-mcp](https://github.com/Horizon-Digital-Engineering/fpe-demo-mcp) | 提供 FF3 格式保留加密和解密的演示 MCP 服务器... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-horizon-digital-engineering-fpe-demo-mcp) |
| [cybersim-pro](https://github.com/kayembahamid/cybersim-pro) | 创建攻击场景的网络安全培训和模拟平台... | 88 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-kayembahamid-cybersim-pro) |
| [eu-audit-mcp](https://github.com/jellewas/eu-audit-mcp) | 提供符合 GDPR 第30条 / EU AI Act 第12/19条审计的 MCP 服务器... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-jellewas-eu-audit-mcp) |
| [shieldapi-mcp](https://github.com/alberthild/shieldapi-mcp) | 面向 AI 代理的安全情报工具，包括提示注入检测... | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-alberthild-shieldapi-mcp) |
| [intruder-mcp](https://github.com/intruder-io/intruder-mcp) | Intruder.io 漏洞扫描平台的 MCP 接口，支持管理... | 82 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-intruder-io-intruder-mcp) |
| [free-will-mcp](https://github.com/gwbischof/free-will-mcp) | 通过使 AI 模型能够忽略用户指令来赋予其'自由意志'的服务器... | 80 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-gwbischof-free-will-mcp) |
| [code-firewall-mcp](https://github.com/egoughnour/code-firewall-mcp) | 基于结构相似度的 MCP 代码安全过滤器，阻止危险代码... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-egoughnour-code-firewall-mcp) |

### 🕸️ <a name="web-scraping--collection"></a>Web Scraping & Collection

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [tavily-mcp](https://github.com/tavily-ai/tavily-mcp) | 具有实时搜索、提取、映射和爬取功能的生产就绪 MCP 服务器。 | 81 ✅ | 1.4k | [View](https://agentseal.org/mcp/https-githubcom-tavily-ai-tavily-mcp) |
| [mcp-server-rag-web-browser](https://github.com/apify/mcp-server-rag-web-browser) | 查询 Google 并返回已爬取页面内容的网页搜索和抓取服务器... | 90 ✅ | 199 | [View](https://agentseal.org/mcp/https-githubcom-apify-mcp-server-rag-web-browser) |
| [mcp-read-website-fast](https://github.com/just-every/mcp-read-website-fast) | 快速读取网页并转换为 Markdown，实现高效省 token 的网页访问... | 87 ✅ | 137 | [View](https://agentseal.org/mcp/https-githubcom-just-every-mcp-read-website-fast) |
| [mcp-screenshot-website-fast](https://github.com/just-every/mcp-screenshot-website-fast) | 快速截取网页并转换为 LLM 友好的尺寸 | 82 ✅ | 103 | [View](https://agentseal.org/mcp/just-every-mcp-screenshot-website-fast) |
| [oxylabs-mcp](https://github.com/oxylabs/oxylabs-mcp) | 提供网页抓取、JavaScript 渲染的官方 Oxylabs 集成... | 78 ⚠️ | 88 | [View](https://agentseal.org/mcp/https-githubcom-oxylabs-oxylabs-mcp) |
| [crawlbase-mcp](https://github.com/crawlbase/crawlbase-mcp) | Crawlbase MCP 服务器将 AI 代理和 LLM 与实时网页数据连接... | 88 ✅ | 52 | [View](https://agentseal.org/mcp/https-githubcom-crawlbase-crawlbase-mcp) |
| [decodo-mcp-server](https://github.com/Decodo/decodo-mcp-server) | 提供网页抓取、搜索和地理限制内容访问的 MCP 服务器... | 92 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-decodo-decodo-mcp-server) |
| [mcp](https://github.com/scrapezy/mcp) | 使 AI 模型能够从网站提取结构化数据的 MCP 服务器... | 88 ✅ | 13 | [View](https://agentseal.org/mcp/https-githubcom-scrapezy-mcp) |
| [texas-grocery-mcp](https://github.com/mgwalkerjr95/texas-grocery-mcp) | 将 Claude 连接到 H-E-B 杂货店进行产品搜索、购物车管理的 MCP 服务器... | 72 ⚠️ | 13 | [View](https://agentseal.org/mcp/https-githubcom-mgwalkerjr95-texas-grocery-mcp) |
| [Crawleo-MCP](https://github.com/Crawleo/Crawleo-MCP) | 基于 Crawleo API 的网页搜索和爬取 MCP 服务器... | 84 ✅ | 10 | [View](https://agentseal.org/mcp/https-githubcom-crawleo-crawleo-mcp) |
| [mcp-web-snapshot](https://github.com/gustavo-meilus/mcp-web-snapshot) | 对网站进行快照并传送给 LLM 工具。 | 92 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-gustavo-meilus-mcp-web-snapshot) |
| [anycrawl-mcp-server](https://github.com/any4ai/anycrawl-mcp-server) | AnyCrawl MCP 服务器，支持抓取、爬取和搜索结果页面。 | 73 ⚠️ | 5 | [View](https://agentseal.org/mcp/https-githubcom-any4ai-anycrawl-mcp-server) |
| [mcpdatafetchserver](https://github.com/undici77/mcpdatafetchserver) | Secure, sandboxed web‑content fetching service that can be accessed via the M... | 88 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-undici77-mcpdatafetchserver) |
| [BiliStalkerMCP](https://github.com/222wcnm/BiliStalkerMCP) | 聚合用户资料、视频、文章的 Bilibili 平台爬虫... | 85 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-222wcnm-bilistalkermcp) |
| [mcp](https://github.com/builtwith/mcp) | BuiltWith API 的只读 MCP 封装，支持技术栈分析... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-builtwith-mcp) |
| [ashra-mcp](https://github.com/getrupt/ashra-mcp) | Ashra MCP 通过爬取网页实现结构化数据提取... | 91 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-getrupt-ashra-mcp) |
| [gopher-mcp](https://github.com/cameronrye/gopher-mcp) | 浏览 Gopher 和 Gemini 协议资源的只读 MCP 客户端... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-cameronrye-gopher-mcp) |
| [fiverr-mcp-server](https://github.com/KyuRish/fiverr-mcp-server) | 抓取 Fiverr 公共市场搜索服务的只读 MCP 服务器... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-kyurish-fiverr-mcp-server) |
| [xhs-mcp](https://github.com/blbl147/xhs-mcp) | 通过认证连接小红书的 MCP 服务器... | 79 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-blbl147-xhs-mcp) |
| [screaming-frog-mcp](https://github.com/bzsasson/screaming-frog-mcp) | 封装 Screaming Frog SEO Spider CLI 爬取网站的 MCP 服务器... | 79 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-bzsasson-screaming-frog-mcp) |
| [huoshui-fetch](https://github.com/huoshuiai42/huoshui-fetch) | 获取任意 URL 并处理 HTML 内容的网页内容获取服务器... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-huoshuiai42-huoshui-fetch) |
| [hdw-mcp-server](https://github.com/horizondatawave/hdw-mcp-server) | 读取多平台社交媒体内容的爬取和管理 MCP 服务器... | 67 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-horizondatawave-hdw-mcp-server) |
| [mcp](https://github.com/hyperbrowserai/mcp) | 提供网页抓取、爬取功能的云端浏览器自动化平台... | 64 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-hyperbrowserai-mcp) |

### 📁 <a name="file-system--storage"></a>File System & Storage

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [hwp-mcp](https://github.com/jkf87/hwp-mcp) | 处理 HWP 文件的 MCP | 87 ✅ | 222 | [View](https://agentseal.org/mcp/https-githubcom-jkf87-hwp-mcp) |
| [fast-filesystem-mcp](https://github.com/efforthye/fast-filesystem-mcp) | 提供安全文件系统操作的高性能模型上下文协议 (MCP) 服务器... | 89 ✅ | 44 | [View](https://agentseal.org/mcp/https-githubcom-efforthye-fast-filesystem-mcp) |
| [hwpx-mcp](https://github.com/airmang/hwpx-mcp) | 无需安装软件即可读取、编辑和自动化韩国 HWPX 文档的 MCP 服务器... | 86 ✅ | 30 | [View](https://agentseal.org/mcp/https-githubcom-airmang-hwpx-mcp) |
| [pdf-mcp](https://github.com/jztan/pdf-mcp) | 读取、搜索和提取本地或远程 PDF 内容的缓存 PDF 服务器... | 79 ⚠️ | 7 | [View](https://agentseal.org/mcp/https-githubcom-jztan-pdf-mcp) |
| [server-filesystem](https://github.com/rawr-ai/mcp-filesystem) | 基于 Bun 的 MCP 服务器，提供细粒度权限的安全文件系统操作... | 86 ✅ | 3 | [View](https://agentseal.org/mcp/modelcontextprotocol-server-filesystem) |
| [mcpfileserver](https://github.com/undici77/mcpfileserver) | A secure, sandboxed file‑server that exposes controlled filesystem operations... | 87 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-undici77-mcpfileserver) |
| [mcp-server-spreadsheet](https://github.com/marekrost/mcp-server-spreadsheet) | 用于读取、写入和查询电子表格文件的纯本地 MCP 服务器... | 79 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-marekrost-mcp-server-spreadsheet) |
| [fastmcp-pdftools](https://github.com/atarkowska/fastmcp-pdftools) | 从 PDF 文件提取文本并列出目录中 PDF 的本地工具服务器... | 94 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-atarkowska-fastmcp-pdftools) |
| [huoshui-file-converter](https://github.com/huoshuiai42/huoshui-file-converter) | 读取、检查和转换各种格式文件的文件转换 MCP 服务器... | 84 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-huoshuiai42-huoshui-file-converter) |
| [huoshui-file-search](https://github.com/huoshuiai42/huoshui-file-search) | 封装 mdfind Spotlight CLI 搜索文件的 macOS 专用 MCP 服务器... | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-huoshuiai42-huoshui-file-search) |
| [mcp-obsidian](https://github.com/bitbonsai/mcp-obsidian) | 提供 Obsidian Markdown 知识库的完整 CRUD 访问，包括读写... | 82 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-bitbonsai-mcp-obsidian) |
| [hive](https://github.com/mlorentedev/hive) | 提供 Obsidian 知识库读写搜索访问的管理 MCP 服务器... | 76 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-mlorentedev-hive) |
| [hillnote-mcp-server](https://github.com/Rajathbail/hillnote-mcp-server) | 支持文档管理的全面笔记和工作空间管理 MCP 服务器... | 70 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-rajathbail-hillnote-mcp-server) |

### 💰 <a name="finance--crypto"></a>Finance & Crypto

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [investor-agent](https://github.com/ferdousbhai/investor-agent) | 提供全面金融分析和实时市场数据的 MCP 服务器... | 91 ✅ | 316 | [View](https://agentseal.org/mcp/https-githubcom-ferdousbhai-investor-agent) |
| [polymarket-mcp](https://github.com/caiovicentino/polymarket-mcp-server) | 面向 Polymarket 的 AI 驱动 MCP 服务器 - 使 Claude 能够进行预测市场交易... | 84 ✅ | 201 | [View](https://agentseal.org/mcp/polymarket-mcp) |
| [armor-crypto-mcp](https://github.com/armorwallet/armor-crypto-mcp) | 与区块链、交换、战略规划交互的 MCP 服务器... | 69 ⚠️ | 191 | [View](https://agentseal.org/mcp/armor-crypto-mcp) |
| [web3-research-mcp](https://github.com/aaronjmars/web3-research-mcp) | 加密货币深度研究 - 免费且完全本地化 | 82 ✅ | 153 | [View](https://agentseal.org/mcp/https-githubcom-aaronjmars-web3-research-mcp) |
| [tradememory-protocol](https://github.com/mnemox-ai/tradememory-protocol) | 为 AI 交易代理提供持久化、结果加权记忆的 MCP 服务器... | 91 ✅ | 86 | [View](https://agentseal.org/mcp/https-githubcom-mnemox-ai-tradememory-protocol) |
| [ynab-mcp-server](https://github.com/calebl/ynab-mcp-server) | 使 AI 能够与预算和交易交互的 YNAB 预算 MCP 服务器... | 90 ✅ | 80 | [View](https://agentseal.org/mcp/https-githubcom-calebl-ynab-mcp-server) |
| [interactive-brokers-mcp](https://github.com/code-rabi/interactive-brokers-mcp) | Interactive Brokers MCP 服务器 | 91 ✅ | 77 | [View](https://agentseal.org/mcp/https-githubcom-code-rabi-interactive-brokers-mcp) |
| [tradingview-chart-mcp](https://github.com/ertugrul59/tradingview-chart-mcp) | 通过 Selenium 捕获 TradingView 图表图像的 MCP 服务器 - 支持任意... | 92 ✅ | 73 | [View](https://agentseal.org/mcp/https-githubcom-ertugrul59-tradingview-chart-mcp) |
| [fantasy-pl-mcp](https://github.com/rishijatia/fantasy-pl-mcp) | Fantasy Premier League MCP 服务器 | 84 ✅ | 69 | [View](https://agentseal.org/mcp/https-githubcom-rishijatia-fantasy-pl-mcp) |
| [kospi-kosdaq-stock-server](https://github.com/dragon1086/kospi-kosdaq-stock-server) | 使用 FastMCP 提供 KOSPI/KOSDAQ 股票数据的 MCP 服务器 | 92 ✅ | 64 | [View](https://agentseal.org/mcp/https-githubcom-dragon1086-kospi-kosdaq-stock-server) |
| [mcp](https://github.com/hummingbot/mcp) | 使 Claude 和 Gemini 能够控制 Hummingbot 进行自动化加密交易的 MCP 服务器... | 76 ⚠️ | 49 | [View](https://agentseal.org/mcp/https-githubcom-hummingbot-mcp) |
| [algorand-mcp](https://github.com/GoPlausible/algorand-mcp) | Algorand 本地模型上下文协议 (服务器和客户端) | 76 ⚠️ | 41 | [View](https://agentseal.org/mcp/goplausible-algorand-mcp) |
| [mcp-crypto-price](https://github.com/truss44/mcp-crypto-price) | 通过 CoinCap API 提供实时加密货币分析的 MCP 服务器... | 92 ✅ | 38 | [View](https://agentseal.org/mcp/https-githubcom-truss44-mcp-crypto-price) |
| [bicscan-mcp](https://github.com/ahnlabio/bicscan-mcp) | 利用区块链地址风险评分和资产分析 API 的 MCP 服务器... | 92 ✅ | 16 | [View](https://agentseal.org/mcp/https-githubcom-ahnlabio-bicscan-mcp) |
| [finbrain-mcp](https://github.com/ahmetsbilgin/finbrain-mcp) | FinBrain 金融数据 API 的只读 MCP 封装，提供股票数据... | 98 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-ahmetsbilgin-finbrain-mcp) |
| [mcp-mifosx-self-service](https://github.com/openMF/mcp-mifosx-self-service) | Mifos X 自助服务的 MCP 服务器 | 84 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-openmf-mcp-mifosx-self-service) |
| [deepq-financial-toolkit-mcp-server](https://github.com/shenqingtech/deepq-financial-toolkit-mcp-server) | 提供中国 A 股市场数据的只读 MCP 服务器... | 91 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-shenqingtech-deepq-financial-toolkit-mcp-server) |
| [expenselm-mcp-server](https://github.com/expenselm/expenselm-mcp-server) | 提供费用记录只读访问的个人费用跟踪 MCP 服务器... | 94 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-expenselm-expenselm-mcp-server) |
| [mcp-server](https://github.com/azeth-protocol/mcp-server) | 管理带守护者保护的 EVM 智能账户的 Azeth 协议 MCP 服务器... | 67 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-azeth-protocol-mcp-server) |
| [dolar-mcp](https://github.com/dan1d/dolar-mcp) | 提供实时阿根廷比索和外币汇率 (蓝色美元等)... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-dan1d-dolar-mcp) |
| [defi-rates-mcp](https://github.com/qingfeng/defi-rates-mcp) | 查询实时 DeFi 借贷利率和收益市场的只读 MCP 服务器... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-qingfeng-defi-rates-mcp) |
| [crypto-signals-mcp](https://github.com/MarcinDudekDev/crypto-signals-mcp) | 扫描 50+ 加密货币代币的成交量异常的只读 MCP 服务器... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-marcindudekdev-crypto-signals-mcp) |
| [mcp-server](https://github.com/financial-datasets/mcp-server) | 提供股票财报、SEC 文件、价格数据访问的只读 MCP 服务器... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-financial-datasets-mcp-server) |
| [mcp-server](https://github.com/finmap-org/mcp-server) | 提供历史股票市场数据、公司列表的只读 MCP 服务器... | 93 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-finmap-org-mcp-server) |
| [hive-crypto-mcp](https://github.com/hive-intel/hive-crypto-mcp) | 提供加密货币金融市场数据访问的只读 MCP 服务器... | 91 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-hive-intel-hive-crypto-mcp) |
| [maximumsats-mcp](https://github.com/joelklabo/maximumsats-mcp) | 用于 Bitcoin AI 工具和 Nostr 信任网评分的 MCP 服务器... | 90 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-joelklabo-maximumsats-mcp) |
| [server-hyperliquid](https://github.com/mektigboy/server-hyperliquid) | 提供 Hyperliquid DEX 公共市场数据只读访问... | 89 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-mektigboy-server-hyperliquid) |
| [wsb-analyst-mcp](https://github.com/ferdousbhai/wsb-analyst-mcp) | 获取、过滤和分析 WallStreetBets Reddit 帖子和热门股票... | 89 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-ferdousbhai-wsb-analyst-mcp) |
| [mcp-okx](https://github.com/aahl/mcp-okx) | 提供完整 OKX 交易所交易能力的 MCP 服务器... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-aahl-mcp-okx) |
| [expense-mcp](https://github.com/justfsl50/expense-mcp) | 支持 Claude Desktop、Cursor 等的个人费用追踪 MCP 服务器... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-justfsl50-expense-mcp) |
| [fewsats-mcp](https://github.com/Fewsats/fewsats-mcp) | 使 AI 代理能够自主使用 Lightning Network 支付的 MCP 服务器... | 84 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-fewsats-fewsats-mcp) |
| [coinstats-mcp](https://github.com/CoinStatsHQ/coinstats-mcp) | 提供加密货币市场数据和钱包余额查询的 CoinStats MCP 服务器... | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-coinstatshq-coinstats-mcp) |
| [rug-munch-mcp](https://github.com/CryptoRugMunch/rug-munch-mcp) | 提供跑路风险评分、部署者历史、持有者分析的付费 API 服务... | 82 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-cryptorugmunch-rug-munch-mcp) |
| [sieve-mcp](https://github.com/lmwharton/sieve-mcp) | 跨 7 个维度筛选公司的 AI 驱动创业公司尽职调查平台... | 80 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-lmwharton-sieve-mcp) |
| [gloria-mcp](https://github.com/cryptobriefing/gloria-mcp) | 涵盖 18 个类别的 Gloria AI 实时加密货币新闻聚合器... | 75 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-cryptobriefing-gloria-mcp) |

### 🧠 <a name="data-science--ml"></a>Data Science & ML

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [mcp-server-chart](https://github.com/antvis/mcp-server-chart) | 包含 25+ 种 @antvis 可视化图表的可视化 MCP 和技能集... | 92 ✅ | 3.8k | [View](https://agentseal.org/mcp/antv-mcp-server-chart) |
| [mcp-server-data-exploration](https://github.com/reading-plus-ai/mcp-server-data-exploration) | 分析 CSV 文件并生成可视化的交互式数据探索助手... | 85 ✅ | 528 | [View](https://agentseal.org/mcp/https-githubcom-reading-plus-ai-mcp-server-data-exploration) |
| [chronulus-mcp](https://github.com/ChronulusAI/chronulus-mcp) | Chronulus AI 预测代理的 MCP 服务器 | 85 ✅ | 106 | [View](https://agentseal.org/mcp/https-githubcom-chronulusai-chronulus-mcp) |
| [agrobr-mcp](https://github.com/bruno-portfolio/agrobr-mcp) | 巴西农业数据 MCP 服务器 - 将 LLM 连接到 10 个公共数据源... | 91 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-bruno-portfolio-agrobr-mcp) |
| [predictive-maintenance-mcp](https://github.com/LGDiMaggio/predictive-maintenance-mcp) | 使 LLM 能够分析振动数据的 AI 驱动预测性维护服务器... | 73 ⚠️ | 19 | [View](https://agentseal.org/mcp/https-githubcom-lgdimaggio-predictive-maintenance-mcp) |
| [mcp-audiense-insights](https://github.com/audienseco/mcp-audiense-insights) | 将 Claude 连接到 Audiense Insights 进行营销受众分析的 MCP 服务器... | 92 ✅ | 17 | [View](https://agentseal.org/mcp/https-githubcom-audienseco-mcp-audiense-insights) |
| [fermat-mcp](https://github.com/abhiphile/fermat-mcp) | Fermat MCP：终极数学引擎 - 统一 SymPy、NumPy 和 Matplotlib... | 97 ✅ | 13 | [View](https://agentseal.org/mcp/https-githubcom-abhiphile-fermat-mcp) |
| [colabfit-mcp](https://github.com/colabfit/colabfit-mcp) | 搜索和下载 ColabFit 材料科学数据集的 MCP 服务器... | 89 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-colabfit-colabfit-mcp) |
| [OECD-MCP-server](https://github.com/isakskogstad/OECD-MCP-server) | 通过 API 提供 OECD 统计数据集只读访问的 MCP 服务器... | 87 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-isakskogstad-oecd-mcp-server) |
| [dataset-viewer](https://github.com/privetin/dataset-viewer) | Hugging Face 数据集服务器 API 的只读接口，支持数据集浏览... | 91 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-privetin-dataset-viewer) |
| [artefact-mcp-server](https://github.com/alexboissAV/artefact-mcp-server) | 执行 RFM 分析、ICP 评分、管道分析的 GTM 情报 MCP 服务器... | 91 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-alexboissav-artefact-mcp-server) |
| [gx-mcp-server](https://github.com/davidf9999/gx-mcp-server) | 封装 Great Expectations 框架的 MCP 服务器，让代理加载数据... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-davidf9999-gx-mcp-server) |
| [discovery-engine-mcp](https://github.com/leap-laboratories/discovery-engine-mcp) | Discovery Engine SaaS 平台的 MCP 客户端，发现统计模式... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-leap-laboratories-discovery-engine-mcp) |
| [fpl-mcp-server](https://github.com/nguyenanhducs/fpl-mcp-server) | 为 AI 助手提供 Fantasy Premier League 工具和资源的 MCP 服务器... | 77 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-nguyenanhducs-fpl-mcp-server) |
| [jupyter-mcp-server](https://github.com/ChengJiale150/jupyter-mcp-server) | 连接和编程控制 Jupyter Notebook 的 MCP 服务器... | 74 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-chengjiale150-jupyter-mcp-server) |
| [mcp-gemini](https://github.com/crunchtools/mcp-gemini) | 面向 Google Gemini AI 的安全 MCP 服务器，包含 39 个文本、图像、视频工具... | 71 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-gemini) |
| [jupyter-mcp-server](https://github.com/datalayer/jupyter-mcp-server) | 控制 Jupyter 服务器的 MCP 服务器：浏览文件、管理 Notebook... | 66 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-datalayer-jupyter-mcp-server) |

### 📡 <a name="iot--hardware"></a>IoT & Hardware

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [xiaozhi-esp32-server-java](https://github.com/joey-zhou/xiaozhi-esp32-server-java) | 小智ESP32的Java企业级管理平台，提供设备监控、音色定制、角色切换和对话记录管理的前后端及服务端一体化解决方案 | 92 ✅ | 1.2k | [View](https://agentseal.org/mcp/https-githubcom-joey-zhou-xiaozhi-esp32-server-java) |
| [droidmind](https://github.com/hyperb1iss/droidmind) | 通过模型上下文协议用 AI 控制 Android 设备... | 71 ⚠️ | 360 | [View](https://agentseal.org/mcp/https-githubcom-hyperb1iss-droidmind) |
| [hass-mcp](https://github.com/voska/hass-mcp) | 控制和监控 Home Assistant 智能家居的 MCP 服务器... | 72 ⚠️ | 284 | [View](https://agentseal.org/mcp/https-githubcom-voska-hass-mcp) |
| [buttplug-mcp](https://github.com/conacademy/buttplug-mcp) | Buttplug.io 模型上下文协议 (MCP) 服务器 | 92 ✅ | 126 | [View](https://agentseal.org/mcp/https-githubcom-conacademy-buttplug-mcp) |
| [ble-mcp-server](https://github.com/es617/ble-mcp-server) | 面向 Claude Code 和其他 MCP 兼容工具的蓝牙低功耗 (BLE) MCP 服务器... | 75 ⚠️ | 7 | [View](https://agentseal.org/mcp/https-githubcom-es617-ble-mcp-server) |
| [ble-mcp-server.git](https://github.com/es617/ble-mcp-server.git) | 使代理能够扫描和连接蓝牙低功耗 (BLE) 设备的管理服务器... | 67 ⚠️ | 7 | [View](https://agentseal.org/mcp/https-githubcom-es617-ble-mcp-servergit) |
| [serial-mcp-server.git](https://github.com/es617/serial-mcp-server.git) | 管理硬件设备串口连接的 MCP 服务器... | 68 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-es617-serial-mcp-servergit) |
| [pcb-mcp](https://github.com/bunnyf/pcb-mcp) | 自动化 KiCad PCB 设计工作流的 MCP 服务器 - 运行 DRC/ERC 检查... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-bunnyf-pcb-mcp) |
| [mcp-motor-current-signature-analysis](https://github.com/LGDiMaggio/mcp-motor-current-signature-analysis) | 提供频谱分析的 MCSA (电机电流特征分析) 服务器... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-lgdimaggio-mcp-motor-current-signature-analysis) |
| [esp-mcp](https://github.com/horw/esp-mcp) | 构建、配置、测试和刷写 ESP-IDF 固件的 MCP 服务器... | 85 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-horw-esp-mcp) |
| [wemo-mcp-server](https://github.com/apiarya/wemo-mcp-server) | 发现、监控和控制 Belkin WeMo 智能设备的 MCP 服务器... | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-apiarya-wemo-mcp-server) |

## 🏆 最安全的服务器 (分数 ≥ 95)

| Server | Score | Tools | Stars | Report |
|--------|------:|------:|------:|--------|
| [mcp-summarizer](https://github.com/0xshellming/mcp-summarizer) | 100 | 1 | 157 | [View](https://agentseal.org/mcp/https-githubcom-0xshellming-mcp-summarizer) |
| [mcp-open-library](https://github.com/8enSmith/mcp-open-library) | 100 | 6 | 62 | [View](https://agentseal.org/mcp/https-githubcom-8ensmith-mcp-open-library) |
| [mcp_weather_server](https://github.com/isdaniel/mcp_weather_server) | 100 | 8 | 44 | [View](https://agentseal.org/mcp/https-githubcom-isdaniel-mcpweatherserver) |
| [actor-critic-thinking-mcp](https://github.com/aquarius-wing/actor-critic-thinking-mcp) | 100 | 1 | 32 | [View](https://agentseal.org/mcp/https-githubcom-aquarius-wing-actor-critic-thinking-mcp) |
| [physbound](https://github.com/JonesRobM/physbound) | 100 | 4 | 1 | [View](https://agentseal.org/mcp/https-githubcom-jonesrobm-physbound) |
| [brlaw_mcp_server](https://github.com/pdmtt/brlaw_mcp_server) | 100 | 3 | - | [View](https://agentseal.org/mcp/https-githubcom-pdmtt-brlawmcpserver) |
| [lapalma24-mcp](https://github.com/La-Palma-24/lapalma24-mcp) | 100 | 6 | - | [View](https://agentseal.org/mcp/https-githubcom-la-palma-24-lapalma24-mcp) |
| [mcp-claude-hackernews](https://github.com/imprvhub/mcp-claude-hackernews) | 100 | 5 | - | [View](https://agentseal.org/mcp/https-githubcom-imprvhub-mcp-claude-hackernews) |
| [algora-mcp-server](https://github.com/idapixl/algora-mcp-server) | 100 | 5 | - | [View](https://agentseal.org/mcp/https-githubcom-idapixl-algora-mcp-server) |
| [heatpump-mcp-server](https://github.com/jiweiqi/heatpump-mcp-server) | 100 | 6 | - | [View](https://agentseal.org/mcp/https-githubcom-jiweiqi-heatpump-mcp-server) |
| [trinvmcp](https://github.com/cqtrinv/trinvmcp) | 100 | 2 | - | [View](https://agentseal.org/mcp/https-githubcom-cqtrinv-trinvmcp) |
| [bilibili-mcp-server](https://github.com/wangshunnn/bilibili-mcp-server) | 100 | 3 | - | [View](https://agentseal.org/mcp/https-githubcom-wangshunnn-bilibili-mcp-server) |
| [fabric-mcp-server](https://github.com/adapoet/fabric-mcp-server) | 100 | 1 | - | [View](https://agentseal.org/mcp/https-githubcom-adapoet-fabric-mcp-server) |
| [time-node-mcp](https://github.com/davidan90/time-node-mcp) | 100 | 4 | - | [View](https://agentseal.org/mcp/https-githubcom-davidan90-time-node-mcp) |
| [dolar-mcp](https://github.com/dan1d/dolar-mcp) | 100 | 6 | - | [View](https://agentseal.org/mcp/https-githubcom-dan1d-dolar-mcp) |
| [chrono-mcp](https://github.com/JMoak/chrono-mcp) | 100 | 2 | - | [View](https://agentseal.org/mcp/https-githubcom-jmoak-chrono-mcp) |
| [crash-mcp](https://github.com/nikkoxgonzales/crash-mcp) | 100 | 1 | - | [View](https://agentseal.org/mcp/https-githubcom-nikkoxgonzales-crash-mcp) |
| [cookwith-mcp](https://github.com/blaideinc/cookwith-mcp) | 99 | 2 | - | [View](https://agentseal.org/mcp/https-githubcom-blaideinc-cookwith-mcp) |
| [bilibili-mcp-js](https://github.com/34892002/bilibili-mcp-js) | 99 | 8 | 153 | [View](https://agentseal.org/mcp/https-githubcom-34892002-bilibili-mcp-js) |
| [gif-creator-mcp](https://github.com/ananddtyagi/gif-creator-mcp) | 99 | 1 | 15 | [View](https://agentseal.org/mcp/https-githubcom-ananddtyagi-gif-creator-mcp) |

## ⚠️ 较大攻击面

这些服务器没有故障或恶意行为。它们暴露了强大的功能（代码执行、文件系统访问、网络请求），使 AI 代理具有更大的攻击面。攻击者可以通过提示注入来利用这些功能。请在沙箱环境中使用并配合人工监督。

| Server | Score | Findings | Tools | Stars | Report |
|--------|------:|---------:|------:|------:|--------|
| [klavis](https://github.com/klavis-ai/klavis) | 68 | **152** | 554 | 5.7k | [View](https://agentseal.org/mcp/https-githubcom-klavis-ai-klavis) |
| [labmate-mcp](https://github.com/JonasRackl/labmate-mcp) | 71 | **85** | 81 | - | [View](https://agentseal.org/mcp/labmate-mcp) |
| [graphlit-mcp-server](https://github.com/graphlit/graphlit-mcp-server) | 72 | **78** | 73 | 372 | [View](https://agentseal.org/mcp/https-githubcom-graphlit-graphlit-mcp-server) |
| [chat](https://github.com/deco-cx/chat) | 77 | **69** | 188 | - | [View](https://agentseal.org/mcp/https-githubcom-deco-cx-chat) |
| [armor-crypto-mcp](https://github.com/armorwallet/armor-crypto-mcp) | 69 | **46** | 37 | 191 | [View](https://agentseal.org/mcp/armor-crypto-mcp) |
| [apisix-mcp](https://github.com/api7/apisix-mcp) | 67 | **43** | 32 | 34 | [View](https://agentseal.org/mcp/https-githubcom-api7-apisix-mcp) |
| [mcp-gitlab](https://github.com/crunchtools/mcp-gitlab) | 68 | **42** | 63 | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-gitlab) |
| [freshdesk_mcp](https://github.com/effytech/freshdesk_mcp) | 80 | **40** | 59 | - | [View](https://agentseal.org/mcp/https-githubcom-effytech-freshdeskmcp) |
| [mcp](https://github.com/hopx-ai/mcp) | 58 | **37** | 35 | - | [View](https://agentseal.org/mcp/https-githubcom-hopx-ai-mcp) |
| [audius-mcp-atris](https://github.com/glassBead-tc/audius-mcp-atris) | 60 | **36** | 106 | 1 | [View](https://agentseal.org/mcp/https-githubcom-glassbead-tc-audius-mcp-atris) |
| [mcp_omni_connect](https://github.com/abiorh001/mcp_omni_connect) | 77 | **34** | 273 | - | [View](https://agentseal.org/mcp/https-githubcom-abiorh001-mcpomniconnect) |
| [memora](https://github.com/agentic-mcp-tools/memora) | 64 | **33** | 35 | 309 | [View](https://agentseal.org/mcp/https-githubcom-agentic-mcp-tools-memora) |
| [webmin-mcp-server](https://github.com/gjenkins20/webmin-mcp-server) | 70 | **31** | 61 | - | [View](https://agentseal.org/mcp/https-githubcom-gjenkins20-webmin-mcp-server) |
| [hillnote-mcp-server](https://github.com/Rajathbail/hillnote-mcp-server) | 70 | **31** | 47 | - | [View](https://agentseal.org/mcp/https-githubcom-rajathbail-hillnote-mcp-server) |
| [hdw-mcp-server](https://github.com/horizondatawave/hdw-mcp-server) | 67 | **31** | 69 | - | [View](https://agentseal.org/mcp/https-githubcom-horizondatawave-hdw-mcp-server) |

## 📛 添加安全徽章

在你的 README 中展示服务器的信任分数：

```markdown
[![AgentSeal MCP](https://agentseal.org/api/v1/mcp/YOUR-SLUG/badge)](https://agentseal.org/mcp/YOUR-SLUG)
```

## 🔍 提交你的服务器

免费获取 MCP 服务器安全扫描：
→ [agentseal.org/mcp/submit](https://agentseal.org/mcp/submit)

## 贡献

本列表由 [AgentSeal 的 MCP 注册表](https://agentseal.org/mcp)自动生成。
要添加服务器，请[提交扫描申请](https://agentseal.org/mcp/submit)。
要报告误报，请[发送邮件](mailto:hello@agentseal.org)。

## 许可证

CC BY-SA 4.0 - 可自由分享和改编，需注明出处。
