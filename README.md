# 🛡️ MCP Server Security Registry

> **800 MCP servers** scanned and analyzed for AI agent security risks.
> Scores reflect how safely an AI agent can use each server, not the code quality of the server itself.
> Updated daily. Powered by [AgentSeal](https://agentseal.org).

**English** · [中文](README.zh.md) · [日本語](README.ja.md) · [한국어](README.ko.md)

## Quick Stats

| Metric | Count |
|--------|-------|
| Total servers scanned | **800** |
| ✅ Safe (score >= 80) | **631** |
| ⚠️ Review (score 50-79) | **169** |
| Total security findings | **6237** |
| Last updated | March 14, 2026 |

## How We Score

Every server is tested through **9 security analyzers**:

- **Schema Analysis** - validates tool parameter types and constraints
- **Static Pattern Detection** - finds command injection, SSRF, path traversal patterns
- **Prompt Injection Scanning** - detects hidden instructions in tool descriptions
- **Toxic Flow Mapping** - identifies dangerous tool chains
- **Unicode Detection** - catches invisible character attacks
- **Deep Autopsy** - active probing with 45+ MCP-specific attack patterns
- **Annotations & Instructions** - checks for behavior-modifying metadata
- **Resource Analysis** - evaluates exposed resources and templates
- **LLM Classification** - Claude-powered semantic analysis of tool intent

**Trust Score:** 0-100 measures how safely an AI agent can use this server.
A lower score does NOT mean the server has bugs or is malicious. It means an AI agent using it has a larger attack surface that adversaries could exploit through prompt injection or tool poisoning.

- **Safe (>= 80):** Low attack surface. Agent can use these with minimal risk.
- **Review (50-79):** Significant capabilities that expand the attack surface. Use with appropriate guardrails.
- **Risky (20-49):** Large attack surface. Requires strict sandboxing and human oversight.
- **Dangerous (< 20):** Critical security concerns. Not recommended for automated use.

## Legend

| Symbol | Meaning |
|--------|---------|
| ✅ | Safe - low attack surface for AI agents |
| ⚠️ | Review - broader capabilities, use with guardrails |
| 🟠 | Risky - large attack surface, needs sandboxing |
| 🔴 | Dangerous - not recommended for automated use |

## Categories

- [🛠️ Developer Tools](#developer-tools) (290)
- [🔍 Search & Knowledge](#search--knowledge) (63)
- [💻 Code & IDE](#code--ide) (31)
- [☁️ Cloud & Infrastructure](#cloud--infrastructure) (35)
- [📝 Content & Media](#content--media) (51)
- [🔌 API Development](#api-development) (22)
- [🗄️ Database & SQL](#database--sql) (29)
- [💬 Communication](#communication) (34)
- [⚙️ System Administration](#system-administration) (13)
- [🔒 Security & Auth](#security--auth) (48)
- [🕸️ Web Scraping & Collection](#web-scraping--collection) (27)
- [📁 File System & Storage](#file-system--storage) (16)
- [💰 Finance & Crypto](#finance--crypto) (40)
- [🧠 Data Science & ML](#data-science--ml) (22)
- [📡 IoT & Hardware](#iot--hardware) (13)

### 🛠️ <a name="developer-tools"></a>Developer Tools

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [markitdown](https://github.com/microsoft/markitdown) | Python tool for converting files and office documents to Markdown. | 88 ✅ | 90.7k | [View](https://agentseal.org/mcp/https-githubcom-microsoft-markitdown) |
| [chrome-devtools-mcp](https://github.com/chromedevtools/chrome-devtools-mcp) | Chrome DevTools for coding agents | 73 ⚠️ | 28.8k | [View](https://agentseal.org/mcp/chrome-devtools-mcp) |
| [Playwright](https://github.com/microsoft/playwright-mcp) | Automates browser interactions for Large Language Models (LLMs) using Playwri... | 62 ⚠️ | 28.7k | [View](https://agentseal.org/mcp/https-githubcom-microsoft-playwright-mcp) |
| [GitHub](https://github.com/github/github-mcp-server) | Enables advanced automation and interaction capabilities with GitHub APIs for... | 70 ⚠️ | 27.8k | [View](https://agentseal.org/mcp/https-githubcom-github-github-mcp-server) |
| [claude-flow](https://github.com/ruvnet/claude-flow) | Enterprise AI orchestration platform for deploying multi-agent swarms with se... | 86 ✅ | 20.9k | [View](https://agentseal.org/mcp/https-githubcom-ruvnet-claude-flow) |
| [beads](https://github.com/steveyegge/beads) | Beads - A memory upgrade for your coding agent | 86 ✅ | 18.9k | [View](https://agentseal.org/mcp/https-githubcom-steveyegge-beads) |
| [n8n-mcp](https://github.com/czlonkowski/n8n-mcp) | MCP server providing AI assistants comprehensive access to n8n's 1,084+ workf... | 92 ✅ | 15.1k | [View](https://agentseal.org/mcp/n8n-mcp) |
| [archon](https://github.com/coleam00/archon) | Beta release of Archon OS - the knowledge and task management backbone for AI... | 92 ✅ | 13.8k | [View](https://agentseal.org/mcp/https-githubcom-coleam00-archon) |
| [mcp-go](https://github.com/mark3labs/mcp-go) | A Go implementation of the Model Context Protocol (MCP), enabling seamless in... | 89 ✅ | 8.3k | [View](https://agentseal.org/mcp/https-githubcom-mark3labs-mcp-go) |
| [git-mcp](https://github.com/idosal/git-mcp) | Put an end to code hallucinations! GitMCP is a free, open-source, remote MCP ... | 78 ⚠️ | 7.8k | [View](https://agentseal.org/mcp/git-mcp) |
| [browser-tools-mcp](https://github.com/agentdeskai/browser-tools-mcp) | Monitor browser logs directly from Cursor and other MCP compatible IDEs. | 91 ✅ | 7.1k | [View](https://agentseal.org/mcp/https-githubcom-agentdeskai-browser-tools-mcp) |
| [cursor-talk-to-figma-mcp](https://github.com/sonnylazuardi/cursor-talk-to-figma-mcp) | MCP integration enabling AI agents like Cursor and Claude Code to read and mo... | 88 ✅ | 6.5k | [View](https://agentseal.org/mcp/https-githubcom-sonnylazuardi-cursor-talk-to-figma-mcp) |
| [cursor-talk-to-figma-mcp](https://github.com/grab/cursor-talk-to-figma-mcp) | TalkToFigma: MCP integration between AI Agent (Cursor, Claude Code) and Figma... | 88 ✅ | 6.5k | [View](https://agentseal.org/mcp/https-githubcom-grab-cursor-talk-to-figma-mcp) |
| [ida-pro-mcp](https://github.com/mrexodia/ida-pro-mcp) | AI-powered reverse engineering assistant that bridges IDA Pro with language m... | 88 ✅ | 6.3k | [View](https://agentseal.org/mcp/ida-pro-mcp) |
| [mcp](https://github.com/browsermcp/mcp) | Browser MCP is a Model Context Provider (MCP) server that allows AI applicati... | 86 ✅ | 6.0k | [View](https://agentseal.org/mcp/browsermcp-mcp) |
| [desktopcommandermcp](https://github.com/wonderwhy-er/desktopcommandermcp) | This is MCP server for Claude that gives it terminal control, file system sea... | 63 ⚠️ | 5.7k | [View](https://agentseal.org/mcp/https-githubcom-wonderwhy-er-desktopcommandermcp) |
| [klavis](https://github.com/klavis-ai/klavis) | Klavis AI (YC X25):  MCP integration platforms that let AI agents use tools r... | 68 ⚠️ | 5.7k | [View](https://agentseal.org/mcp/https-githubcom-klavis-ai-klavis) |
| [praisonai](https://github.com/mervinpraison/praisonai) | PraisonAI 🦞 - Your 24/7 AI employee team. Automate and solve complex challeng... | 78 ⚠️ | 5.7k | [View](https://agentseal.org/mcp/https-githubcom-mervinpraison-praisonai) |
| [playwright-mcp-server](https://github.com/executeautomation/mcp-playwright) | Playwright Model Context Protocol Server - Tool to automate Browsers and APIs... | 73 ⚠️ | 5.3k | [View](https://agentseal.org/mcp/executeautomation-playwright-mcp-server) |
| [magic](https://github.com/21st-dev/magic-mcp) | It's like v0 but in your Cursor/WindSurf/Cline. 21st dev Magic MCP server for... | 82 ✅ | 4.4k | [View](https://agentseal.org/mcp/21st-dev-magic) |
| [osaurus](https://github.com/osaurus-ai/osaurus) | Own your AI. The native macOS harness for AI agents -- any model, persistent ... | 79 ⚠️ | 4.1k | [View](https://agentseal.org/mcp/osaurus-ai-osaurus) |
| [context-mode](https://github.com/mksglu/context-mode) | MCP is the protocol for tool access. We're the virtualization layer for context. | 78 ⚠️ | 3.7k | [View](https://agentseal.org/mcp/https-githubcom-mksglu-context-mode) |
| [mcp-feedback-enhanced](https://github.com/minidoracat/mcp-feedback-enhanced) | Enhanced MCP server for interactive user feedback and command execution in AI... | 91 ✅ | 3.6k | [View](https://agentseal.org/mcp/https-githubcom-minidoracat-mcp-feedback-enhanced) |
| [archestra](https://github.com/archestra-ai/archestra) | Enterprise AI Platform with guardrails, MCP registry, gateway & orchestrator | 92 ✅ | 3.5k | [View](https://agentseal.org/mcp/https-githubcom-archestra-ai-archestra) |
| [refact-chat-js](https://github.com/smallcloudai/refact) | AI Agent that handles engineering tasks end-to-end: integrates with developer... | 92 ✅ | 3.5k | [View](https://agentseal.org/mcp/refact-chat-js) |
| [apple-mcp](https://github.com/dhravya/apple-mcp) | Apple-native MCP server integrating Mac apps like Messages, Notes, Contacts, ... | 81 ✅ | 3.0k | [View](https://agentseal.org/mcp/apple-mcp) |
| [shadcn-ui-mcp-server](https://github.com/jpisnice/shadcn-ui-mcp-server) | A mcp server to allow LLMS gain context about shadcn ui component structure,u... | 83 ✅ | 2.7k | [View](https://agentseal.org/mcp/jpisnice-shadcn-ui-mcp-server) |
| [godot-mcp](https://github.com/Coding-Solo/godot-mcp) | A Godot game engine integration server that allows launching the editor, runn... | 86 ✅ | 2.3k | [View](https://agentseal.org/mcp/https-githubcom-coding-solo-godot-mcp) |
| [mcp-cli](https://github.com/chrishayuk/mcp-cli) | Command-line interface for interacting with Model Context Protocol servers, e... | 92 ✅ | 1.9k | [View](https://agentseal.org/mcp/https-githubcom-chrishayuk-mcp-cli) |
| [ios-simulator-mcp](https://github.com/joshuayoes/ios-simulator-mcp) | MCP server for interacting with the iOS simulator | 91 ✅ | 1.7k | [View](https://agentseal.org/mcp/https-githubcom-joshuayoes-ios-simulator-mcp) |
| [codemcp](https://github.com/ezyang/codemcp) | MCP server enabling Claude Desktop to function as a pair programming assistan... | 72 ⚠️ | 1.6k | [View](https://agentseal.org/mcp/https-githubcom-ezyang-codemcp) |
| [mcptools](https://github.com/f/mcptools) | A command-line interface for discovering, calling, and managing MCP servers w... | 92 ✅ | 1.5k | [View](https://agentseal.org/mcp/https-githubcom-f-mcptools) |
| [mcp-installer](https://github.com/anaisbetts/mcp-installer) | An MCP server that installs other MCP servers for you | 89 ✅ | 1.5k | [View](https://agentseal.org/mcp/anaisbetts-mcp-installer) |
| [notebooklm-mcp](https://github.com/pleaseprompto/notebooklm-mcp) | MCP server for NotebookLM - Let your AI agents (Claude Code, Codex) research ... | 73 ⚠️ | 1.4k | [View](https://agentseal.org/mcp/https-githubcom-pleaseprompto-notebooklm-mcp) |
| [agent-toolkit](https://github.com/stripe/agent-toolkit) | Stripe Agent Toolkit integrates Stripe APIs with LLMs and agent frameworks th... | 92 ✅ | 1.4k | [View](https://agentseal.org/mcp/https-githubcom-stripe-agent-toolkit) |
| [chunkhound](https://github.com/ofriw/chunkhound) | An MCP server providing semantic code search and analysis. ChunkHound researc... | 83 ✅ | 1.1k | [View](https://agentseal.org/mcp/https-githubcom-ofriw-chunkhound) |
| [coderunner](https://github.com/instavm/coderunner) | A local sandbox for your AI agents | 80 ⚠️ | 801 | [View](https://agentseal.org/mcp/https-githubcom-instavm-coderunner) |
| [vibetest-use](https://github.com/browser-use/vibetest-use) | Vibetest MCP - automated QA testing using Browser-Use agents | 87 ✅ | 772 | [View](https://agentseal.org/mcp/https-githubcom-browser-use-vibetest-use) |
| [driftdetect-mcp](https://github.com/dadbodgeoff/drift) | Codebase intelligence for AI. Detects patterns & conventions + remembers deci... | 85 ✅ | 760 | [View](https://agentseal.org/mcp/driftdetect-mcp) |
| [just-prompt](https://github.com/disler/just-prompt) | just-prompt is an MCP server that provides a unified interface to top LLM pro... | 89 ✅ | 719 | [View](https://agentseal.org/mcp/https-githubcom-disler-just-prompt) |
| [blueprint-mcp](https://github.com/arcadeai/blueprint-mcp) | Diagram generation for understanding codebases and system architecture using ... | 92 ✅ | 585 | [View](https://agentseal.org/mcp/https-githubcom-arcadeai-blueprint-mcp) |
| [dbt-mcp](https://github.com/dbt-labs/dbt-mcp) | An MCP server providing tools for AI agents to interact with dbt projects, in... | 85 ✅ | 507 | [View](https://agentseal.org/mcp/https-githubcom-dbt-labs-dbt-mcp) |
| [n8n-workflow-builder](https://github.com/makafeli/n8n-workflow-builder) | AI assistant integration for n8n workflow automation through Model Context Pr... | 87 ✅ | 501 | [View](https://agentseal.org/mcp/https-githubcom-makafeli-n8n-workflow-builder) |
| [web-agent-protocol](https://github.com/ota-tech-ai/web-agent-protocol) | 🌐Web Agent Protocol (WAP) - Record and replay user interactions in the browse... | 92 ✅ | 493 | [View](https://agentseal.org/mcp/https-githubcom-ota-tech-ai-web-agent-protocol) |
| [airtable-mcp-server](https://github.com/domdomegg/airtable-mcp-server) | 🗂️🤖 Airtable Model Context Protocol Server, for allowing AI systems to intera... | 81 ✅ | 430 | [View](https://agentseal.org/mcp/https-githubcom-domdomegg-airtable-mcp-server) |
| [kicad-mcp](https://github.com/lamaalrajih/kicad-mcp) | Model Context Protocol server for KiCad on Mac, Windows, and Linux | 92 ✅ | 401 | [View](https://agentseal.org/mcp/https-githubcom-lamaalrajih-kicad-mcp) |
| [lingti-bot](https://github.com/ruilisi/lingti-bot) | 🐕⚡「极简至上 效率为王 秒级接入 一链即用」的 AI Bot | 75 ⚠️ | 368 | [View](https://agentseal.org/mcp/https-githubcom-ruilisi-lingti-bot) |
| [revit-mcp](https://github.com/revit-mcp/revit-mcp) | AI-powered MCP server enabling Claude and other AI clients to interact with R... | 78 ⚠️ | 362 | [View](https://agentseal.org/mcp/https-githubcom-revit-mcp-revit-mcp) |
| [chat](https://github.com/deco-cx/chat) | Open-source control plane for AI agents. Connect tools, hire agents, organize... | 77 ⚠️ | 350 | [View](https://agentseal.org/mcp/https-githubcom-deco-cx-chat) |
| [MemoryMesh](https://github.com/CheMiguel23/MemoryMesh) | A knowledge graph server that uses the Model Context Protocol (MCP) to provid... | 81 ✅ | 335 | [View](https://agentseal.org/mcp/https-githubcom-chemiguel23-memorymesh) |
| [paws-on-mcp](https://github.com/hemanth/paws-on-mcp) | A comprehensive Model Context Protocol (MCP) server implementing the latest s... | 86 ✅ | 331 | [View](https://agentseal.org/mcp/https-githubcom-hemanth-paws-on-mcp) |
| [moling](https://github.com/gojue/moling) | MoLing is a computer-use and browser-use based MCP server. It is a locally de... | 78 ⚠️ | 330 | [View](https://agentseal.org/mcp/https-githubcom-gojue-moling) |
| [mcp-claude-code](https://github.com/sdglbl/mcp-claude-code) | MCP server implementing Claude Code capabilities for code analysis, file modi... | 63 ⚠️ | 298 | [View](https://agentseal.org/mcp/https-githubcom-sdglbl-mcp-claude-code) |
| [consult7](https://github.com/szeider/consult7) | MCP server to consult a language model with large context size | 85 ✅ | 291 | [View](https://agentseal.org/mcp/https-githubcom-szeider-consult7) |
| [chrome-devtools-mcp](https://github.com/benjaminr/chrome-devtools-mcp) | An MCP Server for Chrome DevTools, following the Chrome DevTools Protocol. In... | 74 ⚠️ | 289 | [View](https://agentseal.org/mcp/https-githubcom-benjaminr-chrome-devtools-mcp) |
| [FileScopeMCP](https://github.com/admica/FileScopeMCP) | Analyzes your codebase identifying important files based on dependency relati... | 82 ✅ | 283 | [View](https://agentseal.org/mcp/https-githubcom-admica-filescopemcp) |
| [MCP-Server-Playwright](https://github.com/Automata-Labs-team/MCP-Server-Playwright) | A Playwright-based browser automation MCP server that provides full remote co... | 74 ⚠️ | 283 | [View](https://agentseal.org/mcp/https-githubcom-automata-labs-team-mcp-server-playwright) |
| [mcp-reasoner](https://github.com/jacck/mcp-reasoner) | A systematic reasoning MCP server implementation for Claude Desktop with beam... | 92 ✅ | 277 | [View](https://agentseal.org/mcp/https-githubcom-jacck-mcp-reasoner) |
| [lucid](https://github.com/get-lucid/lucid) | An intelligence layer grounding autonomous agents in verified, real-time know... | 92 ✅ | 260 | [View](https://agentseal.org/mcp/https-githubcom-get-lucid-lucid) |
| [weather-mcp-server](https://github.com/tuankiri/weather-mcp-server) | An MCP server enabling AI assistants to retrieve real-time weather data for a... | 92 ✅ | 239 | [View](https://agentseal.org/mcp/https-githubcom-tuankiri-weather-mcp-server) |
| [claude_code-gemini-mcp](https://github.com/raiansar/claude_code-gemini-mcp) | Connect Claude Code with Google's Gemini AI for code reviews, questions, and ... | 86 ✅ | 239 | [View](https://agentseal.org/mcp/https-githubcom-raiansar-claudecode-gemini-mcp) |
| [frida-mcp](https://github.com/dnakov/frida-mcp) | MCP stdio server for frida | 91 ✅ | 237 | [View](https://agentseal.org/mcp/https-githubcom-dnakov-frida-mcp) |
| [tmux-mcp](https://github.com/nickgnd/tmux-mcp) | A MCP server for our beloved terminal multiplexer tmux. | 83 ✅ | 235 | [View](https://agentseal.org/mcp/tmux-mcp) |
| [tmux-mcp](https://github.com/nickgnd/tmux-mcp) | A MCP server for our beloved terminal multiplexer tmux. | 83 ✅ | 235 | [View](https://agentseal.org/mcp/https-githubcom-nickgnd-tmux-mcp) |
| [mcp_omni_connect](https://github.com/abiorh001/mcp_omni_connect) | Production-ready Python framework for building autonomous AI agents with plug... | 77 ⚠️ | 232 | [View](https://agentseal.org/mcp/https-githubcom-abiorh001-mcpomniconnect) |
| [overseer](https://github.com/dmmulroy/overseer) | CLI & Codemode MCP server for agent task management | 92 ✅ | 222 | [View](https://agentseal.org/mcp/https-githubcom-dmmulroy-overseer) |
| [image-gen-server](https://github.com/fengin/image-gen-server) | MCP server for Cursor IDE that generates images from text descriptions using ... | 92 ✅ | 219 | [View](https://agentseal.org/mcp/https-githubcom-fengin-image-gen-server) |
| [mcp-taskmanager](https://github.com/kazuph/mcp-taskmanager) | An MCP server that enables Claude to manage and execute tasks in a queue-base... | 91 ✅ | 212 | [View](https://agentseal.org/mcp/kazuph-mcp-taskmanager) |
| [opik-mcp](https://github.com/comet-ml/opik-mcp) | Model Context Protocol (MCP) implementation for Opik enabling seamless IDE in... | 92 ✅ | 199 | [View](https://agentseal.org/mcp/https-githubcom-comet-ml-opik-mcp) |
| [mcp](https://github.com/sveltejs/mcp) | Official Svelte MCP server enabling AI agents to interact with Svelte project... | 89 ✅ | 193 | [View](https://agentseal.org/mcp/https-githubcom-sveltejs-mcp) |
| [facebook-ads-library-mcp](https://github.com/trypeggy/facebook-ads-library-mcp) | MCP server for searching and analyzing Facebook's public ads library. Get ins... | 90 ✅ | 192 | [View](https://agentseal.org/mcp/https-githubcom-trypeggy-facebook-ads-library-mcp) |
| [@rocketshipai](https://github.com/rocketship-ai/rocketship) | Open-source QA testing framework that enables coding agents to write and run ... | 92 ✅ | 182 | [View](https://agentseal.org/mcp/rocketshipai) |
| [anki-mcp-server](https://github.com/scorzeth/anki-mcp-server) | An MCP server that integrates with the local Anki flashcard application, enab... | 98 ✅ | 178 | [View](https://agentseal.org/mcp/https-githubcom-scorzeth-anki-mcp-server) |
| [playwright-plus-python-mcp](https://github.com/blackwhite084/playwright-plus-python-mcp) | MCP server for Playwright browser automation. Navigate websites, interact wit... | 82 ✅ | 174 | [View](https://agentseal.org/mcp/https-githubcom-blackwhite084-playwright-plus-python-mcp) |
| [mcp-doc](https://github.com/meterlong/mcp-doc) | A powerful Word document processing service based on FastMCP, enabling AI ass... | 89 ✅ | 173 | [View](https://agentseal.org/mcp/https-githubcom-meterlong-mcp-doc) |
| [your-memory](https://github.com/jonathan-politzki/your-memory) | Persistent AI memory layer that adds intelligent context to applications with... | 74 ⚠️ | 170 | [View](https://agentseal.org/mcp/https-githubcom-jonathan-politzki-your-memory) |
| [llmctx](https://github.com/khromov/llmctx) | MCP endpoint providing Svelte 5 and SvelteKit developer documentation for AI ... | 92 ✅ | 160 | [View](https://agentseal.org/mcp/https-githubcom-khromov-llmctx) |
| [mcp-server-langfuse](https://github.com/langfuse/mcp-server-langfuse) | Model Context Protocol (MCP) Server for Langfuse Prompt Management. This serv... | 92 ✅ | 158 | [View](https://agentseal.org/mcp/https-githubcom-langfuse-mcp-server-langfuse) |
| [mcp-server-calculator](https://github.com/githejie/mcp-server-calculator) | A minimal MCP server that exposes one tool for evaluating mathematical expres... | 95 ✅ | 147 | [View](https://agentseal.org/mcp/https-githubcom-githejie-mcp-server-calculator) |
| [seline](https://github.com/tercumantanumut/seline) | Desktop app that runs AI agents on your machine, connecting them to messaging... | 91 ✅ | 146 | [View](https://agentseal.org/mcp/https-githubcom-tercumantanumut-seline) |
| [claude-prompts-mcp](https://github.com/minipuft/claude-prompts-mcp) | MCP workflow server for composable prompt templates with validation, reasonin... | 92 ✅ | 141 | [View](https://agentseal.org/mcp/https-githubcom-minipuft-claude-prompts-mcp) |
| [erickwendel-contributions-mcp](https://github.com/erickwendel/erickwendel-contributions-mcp) | A Model Context Protocol (MCP) server that provides tools to query Erick Wend... | 92 ✅ | 136 | [View](https://agentseal.org/mcp/https-githubcom-erickwendel-erickwendel-contributions-mcp) |
| [comet-mcp](https://github.com/hanzili/comet-mcp) | Controls a Comet/Perplexity browser instance to perform agentic web browsing,... | 85 ✅ | 131 | [View](https://agentseal.org/mcp/https-githubcom-hanzili-comet-mcp) |
| [mcp-server](https://github.com/browserstack/mcp-server) | BrowserStack's Official MCP Server | 69 ⚠️ | 130 | [View](https://agentseal.org/mcp/https-githubcom-browserstack-mcp-server) |
| [mcp-server-atlassian-bitbucket](https://github.com/aashari/mcp-server-atlassian-bitbucket) | Node.js/TypeScript MCP server for Atlassian Bitbucket. Enables AI systems (LL... | 74 ⚠️ | 127 | [View](https://agentseal.org/mcp/https-githubcom-aashari-mcp-server-atlassian-bitbucket) |
| [pluggedin-mcp-proxy](https://github.com/VeriTeknik/pluggedin-mcp-proxy) | Plugged.in MCP Server manages all your other MCPs in one MCP. | 81 ✅ | 124 | [View](https://agentseal.org/mcp/https-githubcom-veriteknik-pluggedin-mcp-proxy) |
| [mcp-gdb](https://github.com/signal-slot/mcp-gdb) | An MCP server providing GDB debugging functionality for AI assistants, enabli... | 86 ✅ | 110 | [View](https://agentseal.org/mcp/https-githubcom-signal-slot-mcp-gdb) |
| [sourcerer-mcp](https://github.com/st3v3nmw/sourcerer-mcp) | MCP for semantic code search & navigation that reduces token waste | 86 ✅ | 108 | [View](https://agentseal.org/mcp/https-githubcom-st3v3nmw-sourcerer-mcp) |
| [lapras-mcp-server](https://github.com/lapras-inc/lapras-mcp-server) | lapras.com 公式MCP Server | 89 ✅ | 100 | [View](https://agentseal.org/mcp/https-githubcom-lapras-inc-lapras-mcp-server) |
| [terminal-controller-mcp](https://github.com/gongrzhe/terminal-controller-mcp) | A Model Context Protocol (MCP) server that enables secure terminal command ex... | 80 ⚠️ | 99 | [View](https://agentseal.org/mcp/https-githubcom-gongrzhe-terminal-controller-mcp) |
| [agentup](https://github.com/reddotrocket/agentup) | Configuration-driven framework for building portable, scalable, and secure AI... | 92 ✅ | 97 | [View](https://agentseal.org/mcp/https-githubcom-reddotrocket-agentup) |
| [fabric-rti-mcp](https://github.com/Microsoft/fabric-rti-mcp) | MCP server for Microsoft Fabric Real-Time Intelligence enabling AI agents to ... | 75 ⚠️ | 97 | [View](https://agentseal.org/mcp/https-githubcom-microsoft-fabric-rti-mcp) |
| [json-mcp-server](https://github.com/gongrzhe/json-mcp-server) | JSON handling and processing mcp server | 88 ✅ | 89 | [View](https://agentseal.org/mcp/https-githubcom-gongrzhe-json-mcp-server) |
| [blender-mcp](https://github.com/pranav-deshmukh/blender-mcp) | A Blender automation server that lets agents control the 3D software via Pyth... | 74 ⚠️ | 89 | [View](https://agentseal.org/mcp/https-githubcom-pranav-deshmukh-blender-mcp) |
| [mcp-excel-server](https://github.com/yzfly/mcp-excel-server) | MCP server for comprehensive Excel file management, data analysis, and visual... | 80 ⚠️ | 84 | [View](https://agentseal.org/mcp/https-githubcom-yzfly-mcp-excel-server) |
| [gemini-bridge](https://github.com/eLyiN/gemini-bridge) | A bridge MCP server that forwards agent queries and arbitrary local file cont... | 74 ⚠️ | 84 | [View](https://agentseal.org/mcp/https-githubcom-elyin-gemini-bridge) |
| [unreal-mcp](https://github.com/runreal/unreal-mcp) | MCP server for Unreal Engine that uses Unreal Python Remote Execution | 71 ⚠️ | 82 | [View](https://agentseal.org/mcp/runreal-unreal-mcp) |
| [mcp-azure-devops](https://github.com/Vortiago/mcp-azure-devops) | An MCP server that provides full CRUD access to Azure DevOps work items, team... | 83 ✅ | 80 | [View](https://agentseal.org/mcp/https-githubcom-vortiago-mcp-azure-devops) |
| [mcp-server-circleci](https://github.com/CircleCI-Public/mcp-server-circleci) | A specialized server implementation for the Model Context Protocol (MCP) desi... | 80 ✅ | 80 | [View](https://agentseal.org/mcp/https-githubcom-circleci-public-mcp-server-circleci) |
| [mcp-server-openai](https://github.com/pierrebrunelle/mcp-server-openai) | Query OpenAI models directly from Claude using MCP protocol. | 92 ✅ | 79 | [View](https://agentseal.org/mcp/mcp-server-openai) |
| [multi-ai-advisor-mcp](https://github.com/yuchenssr/multi-ai-advisor-mcp) | council of models for decision | 92 ✅ | 78 | [View](https://agentseal.org/mcp/https-githubcom-yuchenssr-multi-ai-advisor-mcp) |
| [roundtable](https://github.com/askbudi/roundtable) | Local MCP server that coordinates multiple AI coding assistants (Claude, Gemi... | 81 ✅ | 78 | [View](https://agentseal.org/mcp/https-githubcom-askbudi-roundtable) |
| [unifai-sdk-js](https://github.com/unifai-network/unifai-sdk-js) | unifai-sdk-js is the Javascript/Typescript SDK for Unifai, an AI native platf... | 86 ✅ | 75 | [View](https://agentseal.org/mcp/https-githubcom-unifai-network-unifai-sdk-js) |
| [excalidraw-architect-mcp](https://github.com/BV-Venky/excalidraw-architect-mcp) | An MCP server that generates and edits Excalidraw (.excalidraw) diagram files... | 92 ✅ | 71 | [View](https://agentseal.org/mcp/https-githubcom-bv-venky-excalidraw-architect-mcp) |
| [energyplus-mcp](https://github.com/lbnl-eta/energyplus-mcp) | The first open-source Model Context Protocol server enabling AI assistants an... | 90 ✅ | 69 | [View](https://agentseal.org/mcp/https-githubcom-lbnl-eta-energyplus-mcp) |
| [alibabacloud-devops-mcp-server](https://github.com/aliyun/alibabacloud-devops-mcp-server) | Yunxiao MCP Server provides AI assistants with the ability to interact with t... | 87 ✅ | 69 | [View](https://agentseal.org/mcp/https-githubcom-aliyun-alibabacloud-devops-mcp-server) |
| [clarity-mcp-server](https://github.com/microsoft/clarity-mcp-server) | A Model Context Protocol (MCP) server for Microsoft Clarity | 84 ✅ | 68 | [View](https://agentseal.org/mcp/microsoft-clarity-mcp-server) |
| [firefox-devtools-mcp](https://github.com/freema/firefox-devtools-mcp) | A Firefox browser automation MCP server providing tab management, DOM interac... | 70 ⚠️ | 68 | [View](https://agentseal.org/mcp/https-githubcom-freema-firefox-devtools-mcp) |
| [crash-mcp](https://github.com/nikkoxgonzales/crash-mcp) | A structured reasoning-step tracker that helps AI agents break down complex p... | 100 ✅ | 67 | [View](https://agentseal.org/mcp/https-githubcom-nikkoxgonzales-crash-mcp) |
| [deepseek-thinker-mcp](https://github.com/ruixingshi/deepseek-thinker-mcp) | A MCP server providing access to Deepseek's reasoning process via OpenAI API ... | 92 ✅ | 67 | [View](https://agentseal.org/mcp/https-githubcom-ruixingshi-deepseek-thinker-mcp) |
| [mcp-EDA](https://github.com/NellyW8/mcp-EDA) | An EDA toolchain MCP server that enables Verilog synthesis (Yosys), simulatio... | 87 ✅ | 67 | [View](https://agentseal.org/mcp/https-githubcom-nellyw8-mcp-eda) |
| [xiaozhi-autoglm-mcp](https://github.com/xinnan-tech/xiaozhi-autoglm-mcp) | MCP server for Android device automation and mobile agent control via AI, int... | 92 ✅ | 64 | [View](https://agentseal.org/mcp/https-githubcom-xinnan-tech-xiaozhi-autoglm-mcp) |
| [mcp-miro](https://github.com/k-jarzyna/mcp-miro) | Miro integration for Model Context Protocol | 84 ✅ | 62 | [View](https://agentseal.org/mcp/https-githubcom-k-jarzyna-mcp-miro) |
| [mcp-server-atlassian-jira](https://github.com/aashari/mcp-server-atlassian-jira) | Node.js/TypeScript MCP server for Atlassian Jira. Equips AI systems (LLMs) wi... | 80 ⚠️ | 60 | [View](https://agentseal.org/mcp/https-githubcom-aashari-mcp-server-atlassian-jira) |
| [sugar](https://github.com/cdnsteve/sugar) | Autonomous task execution layer for AI coding agents. Manages queues, runs 24... | 90 ✅ | 59 | [View](https://agentseal.org/mcp/https-githubcom-cdnsteve-sugar) |
| [mcp-design-system-extractor](https://github.com/freema/mcp-design-system-extractor) | MCP server that extracts component information from Storybook design systems,... | 84 ✅ | 57 | [View](https://agentseal.org/mcp/https-githubcom-freema-mcp-design-system-extractor) |
| [gdb-mcp](https://github.com/smadi0x86/gdb-mcp) | Multi-debugger MCP server providing debugging functionality for GDB and LLDB ... | 86 ✅ | 56 | [View](https://agentseal.org/mcp/https-githubcom-smadi0x86-gdb-mcp) |
| [a2a_adk_mcp](https://github.com/rubenszimbres/a2a_adk_mcp) | Security-focused multi-agent data processing pipeline using Google's Agent De... | 86 ✅ | 55 | [View](https://agentseal.org/mcp/https-githubcom-rubenszimbres-a2aadkmcp) |
| [mcp-server-apple-reminders](https://github.com/fradser/mcp-server-apple-reminders) | MCP server providing native macOS integration with Apple Reminders and Calend... | 91 ✅ | 53 | [View](https://agentseal.org/mcp/mcp-server-apple-reminders) |
| [gotohuman-mcp-server](https://github.com/gotohuman/gotohuman-mcp-server) | Facilitates AI-to-human review handoffs by listing review forms, fetching the... | 96 ✅ | 52 | [View](https://agentseal.org/mcp/https-githubcom-gotohuman-gotohuman-mcp-server) |
| [whois-mcp](https://github.com/bharathvaj-ganesan/whois-mcp) | MCP Server for whois lookups. | 92 ✅ | 52 | [View](https://agentseal.org/mcp/https-githubcom-bharathvaj-ganesan-whois-mcp) |
| [webpage-screenshot-mcp](https://github.com/ananddtyagi/webpage-screenshot-mcp) | MCP server that captures screenshots of webpages using Puppeteer, enabling AI... | 87 ✅ | 52 | [View](https://agentseal.org/mcp/https-githubcom-ananddtyagi-webpage-screenshot-mcp) |
| [mcp_server_notify](https://github.com/Cactusinhand/mcp_server_notify) | Sends system desktop notifications with optional sound and configurable timeout. | 98 ✅ | 50 | [View](https://agentseal.org/mcp/https-githubcom-cactusinhand-mcpservernotify) |
| [iphone-mcp](https://github.com/blitzdotdev/iphone-mcp) | The MCP Server the lets AI use an iPhone | 86 ✅ | 50 | [View](https://agentseal.org/mcp/blitzdev-iphone-mcp) |
| [random-number-mcp](https://github.com/zazencodes/random-number-mcp) | Production-ready MCP server that provides LLMs with essential random generati... | 90 ✅ | 47 | [View](https://agentseal.org/mcp/https-githubcom-zazencodes-random-number-mcp) |
| [shadowgit-mcp](https://github.com/blade47/shadowgit-mcp) | A Model Context Protocol (MCP) server that provides AI assistants with secure... | 85 ✅ | 46 | [View](https://agentseal.org/mcp/https-githubcom-blade47-shadowgit-mcp) |
| [xray](https://github.com/srijanshukla18/xray) | XRAY MCP provides progressive code intelligence and navigation capabilities f... | 82 ✅ | 46 | [View](https://agentseal.org/mcp/https-githubcom-srijanshukla18-xray) |
| [frida-game-hacking-mcp](https://github.com/0xhackerfren/frida-game-hacking-mcp) | A MCP implementation of Frida that seeks to emulate Cheat Engine functionally... | 71 ⚠️ | 46 | [View](https://agentseal.org/mcp/https-githubcom-0xhackerfren-frida-game-hacking-mcp) |
| [mcp_weather_server](https://github.com/isdaniel/mcp_weather_server) | A read-only MCP server providing current and forecast weather, air quality da... | 100 ✅ | 44 | [View](https://agentseal.org/mcp/https-githubcom-isdaniel-mcpweatherserver) |
| [mcp-server-taskwarrior](https://github.com/awwaiid/mcp-server-taskwarrior) | A Taskwarrior MCP server that allows agents to list, add, and complete tasks ... | 91 ✅ | 44 | [View](https://agentseal.org/mcp/https-githubcom-awwaiid-mcp-server-taskwarrior) |
| [code-screenshot-mcp](https://github.com/MoussaabBadla/code-screenshot-mcp) | An MCP server that generates syntax-highlighted screenshot images of code fro... | 80 ✅ | 44 | [View](https://agentseal.org/mcp/https-githubcom-moussaabbadla-code-screenshot-mcp) |
| [mcp-server-ipinfo](https://github.com/briandconnelly/mcp-server-ipinfo) | MCP server providing IP geolocation and network information via ipinfo.io API... | 90 ✅ | 42 | [View](https://agentseal.org/mcp/https-githubcom-briandconnelly-mcp-server-ipinfo) |
| [mobile-dev-mcp-server](https://github.com/jsuarezruiz/mobile-dev-mcp-server) | This is a MCP designed to manage and interact with mobile devices and simulat... | 83 ✅ | 42 | [View](https://agentseal.org/mcp/https-githubcom-jsuarezruiz-mobile-dev-mcp-server) |
| [powertools-mcp](https://github.com/aws-powertools/powertools-mcp) | Powertools for AWS's official MCP Server | 88 ✅ | 41 | [View](https://agentseal.org/mcp/https-githubcom-aws-powertools-powertools-mcp) |
| [dynamic-shell-server](https://github.com/codelion/dynamic-shell-server) | Dynamic Shell Command MCP Server | 86 ✅ | 41 | [View](https://agentseal.org/mcp/https-githubcom-codelion-dynamic-shell-server) |
| [unreal-api-mcp](https://github.com/Codeturion/unreal-api-mcp) | A read-only reference server that lets agents search and retrieve Unreal Engi... | 93 ✅ | 40 | [View](https://agentseal.org/mcp/https-githubcom-codeturion-unreal-api-mcp) |
| [test-coverage-mcp](https://github.com/goldbergyoni/test-coverage-mcp) | Context engineering: Make your agents aware of how they affect 🧪 test coverag... | 89 ✅ | 40 | [View](https://agentseal.org/mcp/https-githubcom-goldbergyoni-test-coverage-mcp) |
| [unity-api-mcp](https://github.com/Codeturion/unity-api-mcp) | MCP server providing instant, accurate Unity API lookups to prevent AI halluc... | 83 ✅ | 40 | [View](https://agentseal.org/mcp/https-githubcom-codeturion-unity-api-mcp) |
| [mcp-domain-availability](https://github.com/imprvhub/mcp-domain-availability) | An MCP server that checks domain name availability using a single query tool. | 99 ✅ | 39 | [View](https://agentseal.org/mcp/https-githubcom-imprvhub-mcp-domain-availability) |
| [mcp-tasks](https://github.com/flesler/mcp-tasks) | A comprehensive and efficient MCP server for task management with multi-forma... | 91 ✅ | 39 | [View](https://agentseal.org/mcp/https-githubcom-flesler-mcp-tasks) |
| [anki-mcp](https://github.com/nietus/anki-mcp) | An Anki flashcard management server that allows creating, updating, and revie... | 75 ⚠️ | 39 | [View](https://agentseal.org/mcp/https-githubcom-nietus-anki-mcp) |
| [bruno-mcp](https://github.com/hungthai1401/bruno-mcp) | Executes Bruno API collections via the Bruno CLI, allowing HTTP API testing w... | 86 ✅ | 37 | [View](https://agentseal.org/mcp/https-githubcom-hungthai1401-bruno-mcp) |
| [mcp](https://github.com/screenshotone/mcp) | A simple implementation of an MCP server for the ScreenshotOne API | 88 ✅ | 35 | [View](https://agentseal.org/mcp/https-githubcom-screenshotone-mcp) |
| [package-registry-mcp](https://github.com/artmann/package-registry-mcp) | MCP server for searching and getting up-to-date information about NPM, Cargo,... | 86 ✅ | 35 | [View](https://agentseal.org/mcp/package-registry-mcp) |
| [kilntainers](https://github.com/kiln-ai/kilntainers) | MCP server to give every agent an ephemeral Linux sandboxes for executing she... | 85 ✅ | 34 | [View](https://agentseal.org/mcp/https-githubcom-kiln-ai-kilntainers) |
| [actor-critic-thinking-mcp](https://github.com/aquarius-wing/actor-critic-thinking-mcp) | A dual-perspective thinking analysis server based on Model Context Protocol (... | 100 ✅ | 32 | [View](https://agentseal.org/mcp/https-githubcom-aquarius-wing-actor-critic-thinking-mcp) |
| [maven-mcp-server](https://github.com/Bigsy/maven-mcp-server) | An MCP (Model Context Protocol) server that provides tools for checking Maven... | 92 ✅ | 31 | [View](https://agentseal.org/mcp/https-githubcom-bigsy-maven-mcp-server) |
| [postmancer](https://github.com/hijaz/postmancer) | An HTTP API testing client (Postman-style) that can send arbitrary HTTP reque... | 80 ✅ | 30 | [View](https://agentseal.org/mcp/https-githubcom-hijaz-postmancer) |
| [PiloTY](https://github.com/yiwenlu66/PiloTY) | PiloTY: AI pilot for PTY operations via MCP - enables AI agents to control in... | 74 ⚠️ | 30 | [View](https://agentseal.org/mcp/https-githubcom-yiwenlu66-piloty) |
| [splunk-mcp-server2](https://github.com/splunk/splunk-mcp-server2) | Unofficial. Splunk MCP server. Implemented in Python and TypeScript/JS. Runs ... | 86 ✅ | 29 | [View](https://agentseal.org/mcp/https-githubcom-splunk-splunk-mcp-server2) |
| [playwright-mcp](https://github.com/ashish-bansal/playwright-mcp) | MCP server that gives AI assistants visual access to a Playwright-controlled ... | 82 ✅ | 29 | [View](https://agentseal.org/mcp/https-githubcom-ashish-bansal-playwright-mcp) |
| [flyonui-mcp](https://github.com/themeselection/flyonui-mcp) | MCP server for building production-ready UI blocks, components, and landing p... | 87 ✅ | 28 | [View](https://agentseal.org/mcp/https-githubcom-themeselection-flyonui-mcp) |
| [mcpcap](https://github.com/mcpcap/mcpcap) | Modular Python MCP server for analyzing network packet captures with speciali... | 75 ⚠️ | 28 | [View](https://agentseal.org/mcp/https-githubcom-mcpcap-mcpcap) |
| [mcp-simple-timeserver](https://github.com/andybrandt/mcp-simple-timeserver) | A time and date utility MCP server providing local time, UTC via NTP, timezon... | 92 ✅ | 27 | [View](https://agentseal.org/mcp/https-githubcom-andybrandt-mcp-simple-timeserver) |
| [gemini-cli-orchestrator](https://github.com/dnnyngyen/gemini-cli-orchestrator) | An MCP server that allows Claude Code orchestrate Gemini for analysis and con... | 91 ✅ | 25 | [View](https://agentseal.org/mcp/https-githubcom-dnnyngyen-gemini-cli-orchestrator) |
| [ScreenshotMCP](https://github.com/upnorthmedia/ScreenshotMCP) | A Model Context Protocol MCP server for capturing website screenshots with fu... | 88 ✅ | 25 | [View](https://agentseal.org/mcp/https-githubcom-upnorthmedia-screenshotmcp) |
| [mcp-task-orchestrator](https://github.com/EchoingVesper/mcp-task-orchestrator) | A Model Context Protocol server that provides task orchestration capabilities... | 88 ✅ | 24 | [View](https://agentseal.org/mcp/https-githubcom-echoingvesper-mcp-task-orchestrator) |
| [code-memory](https://github.com/kapillamba4/code-memory) | Local semantic code search for your codebase with vector embeddings. Zero tel... | 72 ⚠️ | 24 | [View](https://agentseal.org/mcp/https-githubcom-kapillamba4-code-memory) |
| [anti-bullshit-mcp-server](https://github.com/bmorphism/anti-bullshit-mcp-server) | MCP server for analyzing claims, validating sources, and detecting manipulati... | 92 ✅ | 23 | [View](https://agentseal.org/mcp/https-githubcom-bmorphism-anti-bullshit-mcp-server) |
| [mcp-enhance-prompt](https://github.com/FelixFoster/mcp-enhance-prompt) | An MCP server that rewrites minimal user input into enriched, structured prom... | 91 ✅ | 23 | [View](https://agentseal.org/mcp/https-githubcom-felixfoster-mcp-enhance-prompt) |
| [blowback-context](https://github.com/esnark/blowback) | MCP server for frontend development environments that integrates with AI tool... | 87 ✅ | 22 | [View](https://agentseal.org/mcp/blowback-context) |
| [code-context-provider-mcp](https://github.com/AB498/code-context-provider-mcp) | Provides a structural overview of a local project directory, including file t... | 97 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-ab498-code-context-provider-mcp) |
| [stealth-browser-mcp](https://github.com/newbeb/stealth-browser-mcp) | MCP Server that enables stealth browser access through Playwright, bypassing ... | 92 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-newbeb-stealth-browser-mcp) |
| [create-mcp-ts](https://github.com/stephencme/create-mcp-ts) | Create a new MCP server in TypeScript, batteries included. | 91 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-stephencme-create-mcp-ts) |
| [mcpretentious](https://github.com/oetiker/mcpretentious) | A powerful Model Context Protocol (MCP) server that puppeteers iTerm2 terminals. | 88 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-oetiker-mcpretentious) |
| [securitycopilotmcpserver](https://github.com/jguimera/securitycopilotmcpserver) | MCP Server that integrates with Security Copilot, Sentinel and other tools (i... | 82 ✅ | 20 | [View](https://agentseal.org/mcp/https-githubcom-jguimera-securitycopilotmcpserver) |
| [fabric-mcp-server](https://github.com/adapoet/fabric-mcp-server) | A Fabric AI pattern recommendation server that suggests the best Fabric patte... | 100 ✅ | 19 | [View](https://agentseal.org/mcp/https-githubcom-adapoet-fabric-mcp-server) |
| [termlink](https://github.com/chu2bard/termlink) | MCP server for shell and terminal operations | 91 ✅ | 19 | [View](https://agentseal.org/mcp/https-githubcom-chu2bard-termlink) |
| [hyperbolic-mcp](https://github.com/HyperbolicLabs/hyperbolic-mcp) | MCP server enabling Claude to interact with Hyperbolic's GPU cloud for viewin... | 86 ✅ | 19 | [View](https://agentseal.org/mcp/https-githubcom-hyperboliclabs-hyperbolic-mcp) |
| [sleep-mcp](https://github.com/garoth/sleep-mcp) | An MCP server providing a sleep/wait tool for adding delays between operation... | 92 ✅ | 18 | [View](https://agentseal.org/mcp/https-githubcom-garoth-sleep-mcp) |
| [anki-connect-mcp](https://github.com/spacholski1225/anki-connect-mcp) | A custom Model Context Protocol (MCP) implementation for Anki Web, enabling s... | 80 ⚠️ | 18 | [View](https://agentseal.org/mcp/https-githubcom-spacholski1225-anki-connect-mcp) |
| [jupytercad-mcp](https://github.com/asmith26/jupytercad-mcp) | A JupyterCAD MCP server that enables AI-driven creation and editing of 3D CAD... | 83 ✅ | 17 | [View](https://agentseal.org/mcp/https-githubcom-asmith26-jupytercad-mcp) |
| [alertmanager-mcp-server](https://github.com/ntk148v/alertmanager-mcp-server) | A Model Context Protocol (MCP) server that enables AI assistants to integreat... | 87 ✅ | 16 | [View](https://agentseal.org/mcp/https-githubcom-ntk148v-alertmanager-mcp-server) |
| [mcp_server_pcileech](https://github.com/evan7198/mcp_server_pcileech) | A simple MCP server for using pcileech to read or write another pc's memory | 85 ✅ | 16 | [View](https://agentseal.org/mcp/https-githubcom-evan7198-mcpserverpcileech) |
| [Autogen_MCP](https://github.com/DynamicEndpoints/Autogen_MCP) | An MCP server that enables creation, configuration, and execution of Microsof... | 76 ⚠️ | 16 | [View](https://agentseal.org/mcp/https-githubcom-dynamicendpoints-autogenmcp) |
| [npm-search-mcp-server](https://github.com/btwiuse/npm-search-mcp-server) | MCP server for searching npm packages | 92 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-btwiuse-npm-search-mcp-server) |
| [android-mcp-server](https://github.com/jiantao88/android-mcp-server) | Android MCP Server implementation | 87 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-jiantao88-android-mcp-server) |
| [networksdb-mcp](https://github.com/mordavid/networksdb-mcp) | Fast MCP integration for NetworksDB API - Query IP addresses, organizations, ... | 86 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-mordavid-networksdb-mcp) |
| [context-crystallizer](https://github.com/hubertciebiada/context-crystallizer) | Transform large repositories into crystallized, AI-consumable knowledge bases... | 82 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-hubertciebiada-context-crystallizer) |
| [agentops-mcp](https://github.com/AgentOps-AI/agentops-mcp) | An MCP server for querying AgentOps agent telemetry — authorizing via API key... | 96 ✅ | 14 | [View](https://agentseal.org/mcp/https-githubcom-agentops-ai-agentops-mcp) |
| [hooks_mcp](https://github.com/scosman/hooks_mcp) | MCP server that exposes project-specific development tools (tests, linters, e... | 92 ✅ | 14 | [View](https://agentseal.org/mcp/https-githubcom-scosman-hooksmcp) |
| [argus-mcp](https://github.com/lokafinnsw/argus-mcp) | AI code review MCP server with Zero-Trust approach. Multi-model support, cach... | 92 ✅ | 14 | [View](https://agentseal.org/mcp/https-githubcom-lokafinnsw-argus-mcp) |
| [mcp-time](https://github.com/TheoBrigitte/mcp-time) | MCP (Model Context Protocol) server which provides utilities to work with tim... | 89 ✅ | 14 | [View](https://agentseal.org/mcp/theofoobar-mcp-time) |
| [currents-mcp](https://github.com/currents-dev/currents-mcp) | Currents MCP Server | 84 ✅ | 14 | [View](https://agentseal.org/mcp/https-githubcom-currents-dev-currents-mcp) |
| [domain-tools-mcp-server](https://github.com/deshabhishek007/domain-tools-mcp-server) | A Model Context Protocol (MCP) server for comprehensive domain analysis: WHOI... | 92 ✅ | 13 | [View](https://agentseal.org/mcp/https-githubcom-deshabhishek007-domain-tools-mcp-server) |
| [riza-mcp](https://github.com/riza-io/riza-mcp) | Isolated code interpreter for LLM-generated code via Riza API, with tool mana... | 91 ✅ | 13 | [View](https://agentseal.org/mcp/https-githubcom-riza-io-riza-mcp) |
| [qrcode_mcp](https://github.com/2niuhe/qrcode_mcp) | mcp tool to generate qrcode | 91 ✅ | 12 | [View](https://agentseal.org/mcp/https-githubcom-2niuhe-qrcodemcp) |
| [mcp-internet-speed-test](https://github.com/inventer-dev/mcp-internet-speed-test) | An MCP server for measuring network performance metrics (download/upload spee... | 78 ⚠️ | 12 | [View](https://agentseal.org/mcp/https-githubcom-inventer-dev-mcp-internet-speed-test) |
| [d.i.e-mcp](https://github.com/lazy-importer/d.i.e-mcp) | This is a  MCP server for DIE (Detect It Easy ) | 92 ✅ | 11 | [View](https://agentseal.org/mcp/https-githubcom-lazy-importer-die-mcp) |
| [mcp-go-debugger](https://github.com/sunfmin/mcp-go-debugger) | A Go debugger integrated with MCP that lets you launch, attach, set breakpoin... | 88 ✅ | 11 | [View](https://agentseal.org/mcp/https-githubcom-sunfmin-mcp-go-debugger) |
| [teamcity-mcp](https://github.com/itcaat/teamcity-mcp) | Teamcity MCP Server | 86 ✅ | 11 | [View](https://agentseal.org/mcp/https-githubcom-itcaat-teamcity-mcp) |
| [kylas-crm-mcp-server](https://github.com/kylastech/kylas-crm-mcp-server) | A CRM integration server for Kylas that enables creating, updating, searching... | 67 ⚠️ | 11 | [View](https://agentseal.org/mcp/https-githubcom-kylastech-kylas-crm-mcp-server) |
| [mcp-files](https://github.com/flesler/mcp-files) | A developer-focused MCP server providing code symbol extraction, precise line... | 92 ✅ | 10 | [View](https://agentseal.org/mcp/https-githubcom-flesler-mcp-files) |
| [memory-mcp](https://github.com/chenxiaofie/memory-mcp) | A local conversational memory system that caches messages, manages task episo... | 91 ✅ | 10 | [View](https://agentseal.org/mcp/https-githubcom-chenxiaofie-memory-mcp) |
| [mcp-gitlab-jira](https://github.com/HainanZhao/mcp-gitlab-jira) | MCP server for GitLab and Jira integration, enabling AI agents to interact wi... | 92 ✅ | 9 | [View](https://agentseal.org/mcp/mcp-gitlab-jira) |
| [omni-dev-fusion](https://github.com/tao3k/omni-dev-fusion) | High-performance AI operating system kernel that bridges human intent and mac... | 91 ✅ | 9 | [View](https://agentseal.org/mcp/https-githubcom-tao3k-omni-dev-fusion) |
| [mcp-domaintools](https://github.com/patrickdappollonio/mcp-domaintools) | MCP server providing DNS lookups, WHOIS queries, connectivity testing, TLS ce... | 88 ✅ | 9 | [View](https://agentseal.org/mcp/https-githubcom-patrickdappollonio-mcp-domaintools) |
| [pyxel-mcp](https://github.com/kitao/pyxel-mcp) | An MCP server that runs Pyxel retro game scripts and provides visual/audio in... | 79 ⚠️ | 9 | [View](https://agentseal.org/mcp/https-githubcom-kitao-pyxel-mcp) |
| [mcp-agentic-framework](https://github.com/Piotr1215/mcp-agentic-framework) | A multi-agent coordination framework that allows AI agents to register, disco... | 78 ⚠️ | 9 | [View](https://agentseal.org/mcp/https-githubcom-piotr1215-mcp-agentic-framework) |
| [handmirrormcp](https://github.com/rkttu/handmirrormcp) | MCP server for inspecting .NET assemblies and NuGet packages to provide AI co... | 89 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-rkttu-handmirrormcp) |
| [canvas-lms-mcp](https://github.com/ahnopologetic/canvas-lms-mcp) | An MCP server that bridges AI systems with Canvas LMS, providing access to ed... | 89 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-ahnopologetic-canvas-lms-mcp) |
| [mcp-project-manager](https://github.com/croffasia/mcp-project-manager) | 🚀 Hierarchical task management server via Model Context   Protocol (MCP). Cre... | 88 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-croffasia-mcp-project-manager) |
| [mcp-server-adb](https://github.com/watabee/mcp-server-adb) | MCP Server for Android Debug Bridge (ADB), enabling Claude to interact with A... | 87 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-watabee-mcp-server-adb) |
| [piston-mcp](https://github.com/alvii147/piston-mcp) | Executes arbitrary code in multiple programming languages using the Piston re... | 84 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-alvii147-piston-mcp) |
| [sonatype-mcp](https://github.com/brianveltman/sonatype-mcp) | MCP server for Sonatype Nexus Repository Manager | 84 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-brianveltman-sonatype-mcp) |
| [skill-ninja-mcp-server](https://github.com/aktsmm/skill-ninja-mcp-server) | An agent skill package manager that searches, installs, and manages SKILL.md ... | 76 ⚠️ | 7 | [View](https://agentseal.org/mcp/https-githubcom-aktsmm-skill-ninja-mcp-server) |
| [excel-to-json-mcp](https://github.com/he-yang/excel-to-json-mcp) | Converts Excel (.xlsx) files and CSV/tab-separated data to JSON via two tools... | 92 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-he-yang-excel-to-json-mcp) |
| [mcp-idb](https://github.com/noahlozevski/mcp-idb) | MCP server for fb-idb bridge. | 86 ✅ | 6 | [View](https://agentseal.org/mcp/noahlozevski-mcp-idb) |
| [spm-mcp](https://github.com/simpleswift/spm-mcp) | Swift Package Manager MCP Server written in Swift | 85 ✅ | 6 | [View](https://agentseal.org/mcp/simpleswift-spm-mcp) |
| [public-apis-mcp](https://github.com/zazencodes/public-apis-mcp) | Search for free APIs using MCP | 85 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-zazencodes-public-apis-mcp) |
| [mcp-devcontainers](https://github.com/AI-QL/mcp-devcontainers) | Manages VS Code devcontainer lifecycle operations including starting, stoppin... | 82 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-ai-ql-mcp-devcontainers) |
| [reexpress_mcp_server](https://github.com/ReexpressAI/reexpress_mcp_server) | Reexpress Model-Context-Protocol (MCP) Server | 82 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-reexpressai-reexpressmcpserver) |
| [Clojars-MCP-Server](https://github.com/Bigsy/Clojars-MCP-Server) | Queries the Clojars Maven/Clojure package registry to retrieve dependency ver... | 98 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-bigsy-clojars-mcp-server) |
| [mcp-sandbox](https://github.com/danstarns/mcp-sandbox) | Turn any JavaScript module into a sandboxed MCP server with automatic reflect... | 92 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-danstarns-mcp-sandbox) |
| [mcpgex](https://github.com/patzedi/mcpgex) | MCP server for finding, testing and refining regex patterns | 92 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-patzedi-mcpgex) |
| [mcp-grep](https://github.com/247arjun/mcp-grep) | An MCP Server wrapper around the grep CLI tool | 87 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-247arjun-mcp-grep) |
| [log-analyzer-mcp](https://github.com/Fato07/log-analyzer-mcp) | An MCP server for parsing, searching, and debugging log files across formats ... | 81 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-fato07-log-analyzer-mcp) |
| [sonarcloud-mcp](https://github.com/dozzman/sonarcloud-mcp) | sonarcloud/sonarqube cloud MCP server for fetching issues | 92 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-dozzman-sonarcloud-mcp) |
| [aria-validate-mcp-server](https://github.com/yamanoku/aria-validate-mcp-server) | Model context protocol server for validating ARIA (Accessible Rich Internet A... | 92 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-yamanoku-aria-validate-mcp-server) |
| [time-mcp-pypi.git](https://github.com/domdomegg/time-mcp-pypi.git) | Minimal Python MCP server that provides a tool to get the current UTC date an... | 92 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-domdomegg-time-mcp-pypigit) |
| [node-code-sandbox-mcp](https://github.com/mozicim/node-code-sandbox-mcp) | # 🐢🚀 Node.js Sandbox MCP ServerThis repository hosts a Node.js server that im... | 77 ⚠️ | 4 | [View](https://agentseal.org/mcp/node-code-sandbox-mcp) |
| [conan-mcp](https://github.com/conan-io/conan-mcp) | Model Context Protocol server for Conan package manager, enabling project cre... | 77 ⚠️ | 4 | [View](https://agentseal.org/mcp/https-githubcom-conan-io-conan-mcp) |
| [heatpump-mcp-server](https://github.com/jiweiqi/heatpump-mcp-server) | An MCP server that helps users size, compare, and evaluate heat pump systems ... | 100 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-jiweiqi-heatpump-mcp-server) |
| [mcp-refactoring.git](https://github.com/marshally/mcp-refactoring.git) | An MCP server that lists, previews, and applies Fowler-style code refactoring... | 92 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-marshally-mcp-refactoringgit) |
| [mcp-ghidra5-windows](https://github.com/thestingr/mcp-ghidra5-windows) | 🏢 Enterprise Windows Service for GPT-5 Powered Ghidra Reverse Engineering / P... | 92 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-thestingr-mcp-ghidra5-windows) |
| [cfr_mcp_server](https://github.com/mr-xn/cfr_mcp_server) | 这是一个基于 Python 的 MCP (Model Context Protocol) 服务器实现，封装了 `cfr.jar` 反编译功能，并支持 SS... | 92 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-mr-xn-cfrmcpserver) |
| [context-rot-detection](https://github.com/milos-product-maker/context-rot-detection) | MCP service that gives AI agents real-time visibility into their cognitive he... | 92 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-milos-product-maker-context-rot-detection) |
| [mermaid-validator-mcp](https://github.com/lf112/mermaid-validator-mcp) | Validates Mermaid diagram syntax and returns diagram type or detailed error m... | 92 ✅ | 3 | [View](https://agentseal.org/mcp/mermaid-validator-mcp) |
| [krs-poland-mcp-server](https://github.com/pkolawa/krs-poland-mcp-server) | The MCP server for KRS Poland public API. | 92 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-pkolawa-krs-poland-mcp-server) |
| [mcp-postman](https://github.com/freebeiro/mcp-postman) | A Model Context Protocol (MCP) server built with Cloudflare Workers for integ... | 92 ✅ | 3 | [View](https://agentseal.org/mcp/mcp-postman) |
| [fulcra-context-mcp](https://github.com/fulcradynamics/fulcra-context-mcp) | An MCP server providing access to Fulcra Context data through the Fulcra API,... | 89 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-fulcradynamics-fulcra-context-mcp) |
| [mcp](https://github.com/openfort-xyz/mcp) | Open-source MCP server that gives AI assistants 42 tools for managing wallet ... | 87 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-openfort-xyz-mcp) |
| [math-mcp-learning-server](https://github.com/clouatre-labs/math-mcp-learning-server) | Educational MCP server with 17 math tools covering arithmetic, matrix algebra... | 84 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-clouatre-labs-math-mcp-learning-server) |
| [mcp-browser-server](https://github.com/wladastic/mcp-browser-server) | Browser automation MCP server using Playwright, enabling AI assistants to int... | 80 ⚠️ | 3 | [View](https://agentseal.org/mcp/https-githubcom-wladastic-mcp-browser-server) |
| [mcp-relay](https://github.com/mhcoen/mcp-relay) | A message relay buffer that allows Claude Desktop and Claude Code to pass opa... | 79 ⚠️ | 3 | [View](https://agentseal.org/mcp/https-githubcom-mhcoen-mcp-relay) |
| [snowfakery-mcp](https://github.com/composable-delivery/snowfakery-mcp) | An MCP server wrapping Snowfakery, a tool for generating realistic fake data ... | 76 ⚠️ | 3 | [View](https://agentseal.org/mcp/https-githubcom-composable-delivery-snowfakery-mcp) |
| [memory-mcp](https://github.com/michael-denyer/memory-mcp) | Persistent memory system for AI assistants with a hot cache for instant recal... | 71 ⚠️ | 3 | [View](https://agentseal.org/mcp/https-githubcom-michael-denyer-memory-mcp) |
| [time-node-mcp](https://github.com/davidan90/time-node-mcp) | A Node.js MCP server that provides timezone-aware date and time utilities: re... | 100 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-davidan90-time-node-mcp) |
| [mcp-agile-luminary](https://github.com/AgileLuminary/mcp-agile-luminary) | An MCP server for connecting with Agile Luminary Project Management Application | 92 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-agileluminary-mcp-agile-luminary) |
| [selenium-selfhealing-mcp](https://github.com/aiqualitylab/selenium-selfhealing-mcp) | An MCP server that automatically fixes broken Selenium test locators when UI ... | 92 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-aiqualitylab-selenium-selfhealing-mcp) |
| [frida-mcp](https://github.com/rmorgans/frida-mcp) | An MCP server for Frida that enables AI systems to dynamically instrument and... | 91 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-rmorgans-frida-mcp) |
| [clix-mcp-server](https://github.com/clix-so/clix-mcp-server) | Clix MCP Server enables AI agents to provide real-time, trusted Clix document... | 89 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-clix-so-clix-mcp-server) |
| [mcp-page-capture](https://github.com/chasesaurabh/mcp-page-capture) | Capture web page screenshots and return MCP-compatible metadata for automated... | 88 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-chasesaurabh-mcp-page-capture) |
| [ctfd-mcp-server](https://github.com/mrjamescot/ctfd-mcp-server) | MCP configuration to link AI agents with a CTFd instance. | 88 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-mrjamescot-ctfd-mcp-server) |
| [ghidramcp](https://github.com/pr0cf5/ghidramcp) | MCP server enabling LLMs to autonomously reverse engineer and analyze binarie... | 86 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-pr0cf5-ghidramcp) |
| [coderide-mcp](https://github.com/PixdataOrg/coderide-mcp) | A project and task management MCP server for AI coding agents, enabling retri... | 85 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-pixdataorg-coderide-mcp) |
| [frontend-design-loop-mcp](https://github.com/alexalexalex222/frontend-design-loop-mcp) | An AI-driven frontend design automation tool that generates, evaluates, and o... | 83 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-alexalexalex222-frontend-design-loop-mcp) |
| [github-projects-mcp](https://github.com/redducklabs/github-projects-mcp) | A GitHub Projects v2 management server that wraps the GitHub GraphQL API to l... | 82 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-redducklabs-github-projects-mcp) |
| [tools](https://github.com/the-basilisk-ai/squad-mcp) | AI-powered product discovery and strategy platform that integrates with Claud... | 81 ✅ | 2 | [View](https://agentseal.org/mcp/squadai-tools) |
| [terminal-mcp](https://github.com/mkpvishnu/terminal-mcp) | MCP server for interactive terminal sessions: SSH, REPLs, database CLIs, and ... | 81 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-mkpvishnu-terminal-mcp) |
| [xctools-mcp-server](https://github.com/nzrsky/xctools-mcp-server) | A Model Context Protocol server for different Xcode related tools | 81 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-nzrsky-xctools-mcp-server) |
| [agentic-store-mcp](https://github.com/agenticstore/agentic-store-mcp) | Give Your AI Agents Superpowers with Free, Open-Source MCP Tools by AgenticSt... | 75 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-agenticstore-agentic-store-mcp) |
| [physbound](https://github.com/JonesRobM/physbound) | An RF/physics validation MCP server that computes link budgets, Shannon-Hartl... | 100 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-jonesrobm-physbound) |
| [algora-mcp-server](https://github.com/idapixl/algora-mcp-server) | A read-only MCP server for browsing, searching, and retrieving statistics abo... | 100 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-idapixl-algora-mcp-server) |
| [agent-domain-service-mcp](https://github.com/gregm711/agent-domain-service-mcp) | An MCP server that checks domain name availability, explores TLD variations, ... | 98 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-gregm711-agent-domain-service-mcp) |
| [char-index-mcp](https://github.com/agent-hanju/char-index-mcp) | A pure string/character index manipulation library providing find, split, ins... | 97 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-agent-hanju-char-index-mcp) |
| [zmanim-mcp-server.git](https://github.com/ariroffe72/zmanim-mcp-server.git) | MCP server for calculating Jewish prayer times (zmanim) worldwide using NOAA-... | 90 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-ariroffe72-zmanim-mcp-servergit) |
| [M365-roadmap-mcp-server](https://github.com/jonnybottles/M365-roadmap-mcp-server) | Python MCP server enabling AI agents to programmatically query the Microsoft ... | 87 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-jonnybottles-m365-roadmap-mcp-server) |
| [IIIF_MCP](https://github.com/code4history/IIIF_MCP) | MCP server for IIIF (International Image Interoperability Framework) integrat... | 86 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-code4history-iiifmcp) |
| [meta-prompt-mcp](https://github.com/kapillamba4/meta-prompt-mcp) | A prompting reference server that retrieves Google's and Anthropic's official... | 84 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-kapillamba4-meta-prompt-mcp) |
| [mcp-autogen-doc](https://github.com/sykuang/mcp-autogen-doc) | A Model Context Protocol (MCP) server that provides AI assistants with the ab... | 84 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-sykuang-mcp-autogen-doc) |
| [nativ-mcp](https://github.com/Nativ-Technologies/nativ-mcp) | AI-powered localization MCP server that translates content while respecting b... | 84 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-nativ-technologies-nativ-mcp) |
| [simctl-mcp-server](https://github.com/nzrsky/simctl-mcp-server) | iOS simctl MCP server | 79 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-nzrsky-simctl-mcp-server) |
| [cowork-history](https://github.com/egoughnour/cowork-history) | A local MCP server that indexes and searches Claude conversation history usin... | 76 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-egoughnour-cowork-history) |
| [dbgprobe-mcp-server.git](https://github.com/es617/dbgprobe-mcp-server.git) | An MCP server for AI-assisted embedded systems debugging via hardware debug p... | 75 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-es617-dbgprobe-mcp-servergit) |
| [chrono-mcp](https://github.com/JMoak/chrono-mcp) | A time and timezone utility MCP server providing current time retrieval and d... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-jmoak-chrono-mcp) |
| [devops-practices](https://github.com/ai-4-devops/devops-practices) | A read-only knowledge base server that serves DevOps practice documents and f... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-ai-4-devops-devops-practices) |
| [zoho-crm-mcp-server](https://github.com/asklokesh/zoho-crm-mcp-server) | A Zoho CRM MCP server that provides read and write access to leads, contacts,... | 98 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-asklokesh-zoho-crm-mcp-server) |
| [guidance-lark-mcp](https://github.com/guidance-ai/guidance-lark-mcp) | An MCP server for validating llguidance/Lark grammars, running batch parse te... | 96 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-guidance-ai-guidance-lark-mcp) |
| [stella-mcp](https://github.com/bradleylab/stella-mcp) | An MCP server for building and running Stella XMILE system dynamics simulatio... | 93 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-bradleylab-stella-mcp) |
| [mcp-server-r-counter](https://github.com/guanqun-yang/mcp-server-r-counter) | Counts the number of 'R' or 'r' characters in an input string. | 93 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-guanqun-yang-mcp-server-r-counter) |
| [mcp-test](https://github.com/bharath-krishna/mcp-test) | A simple MCP server with an echo tool for testing purposes. Returns back any ... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-bharath-krishna-mcp-test) |
| [time-mcp-server](https://github.com/lchinglen/time-mcp-server) | MCP server providing time and timezone conversion capabilities with IANA time... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-lchinglen-time-mcp-server) |
| [nft-log-analyzer](https://github.com/mashish/nft-log-analyzer) | AI-powered log analysis MCP server — 100% local via Ollama, auto-files GitHub... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-mashish-nft-log-analyzer) |
| [drand-mcp-server](https://github.com/randa-mu/drand-mcp-server) | MCP server providing verifiable randomness from the drand network for AI appl... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-randa-mu-drand-mcp-server) |
| [sutra](https://github.com/4rgon4ut/sutra) | An MCP server providing structured prompting templates, thinking models, and ... | 91 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-4rgon4ut-sutra) |
| [mcp-server-spira](https://github.com/Inflectra/mcp-server-spira) | MCP server for Inflectra SpiraTeam/SpiraPlan that provides read access to ALM... | 90 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-inflectra-mcp-server-spira) |
| [callout](https://github.com/fantasieleven-code/callout) | An AI co-founder assistant for solo/early-stage builders that provides multi-... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-fantasieleven-code-callout) |
| [esg-mcp-servers](https://github.com/freminder/esg-mcp-servers) | Open-source MCP servers for ESG data with 31 tools for metric extraction, PDF... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-freminder-esg-mcp-servers) |
| [pgyer-mcp-server](https://github.com/PGYER/pgyer-mcp-server) | PGYER 平台的 MCP Server，支持上传、查询 App 等 | 86 ✅ | - | [View](https://agentseal.org/mcp/pgyer-mcp-server) |
| [mcp-google-search-console](https://github.com/crunchtools/mcp-google-search-console) | MCP server that wraps the Google Search Console API to query search analytics... | 84 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-google-search-console) |
| [mcp-server](https://github.com/lilo-property/mcp-server) | Vacation rental booking and protection for AI agents | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-lilo-property-mcp-server) |
| [MCP](https://github.com/akshaykylas94/MCP) | A Kylas CRM MCP server providing tools to create, search, and filter sales le... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-akshaykylas94-mcp) |
| [mathematica-mcp](https://github.com/lars20070/mathematica-mcp) | A Mathematica/Wolfram Engine MCP server that evaluates arbitrary Wolfram Lang... | 76 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-lars20070-mathematica-mcp) |
| [tokennuke](https://github.com/BigJai/tokennuke) | Nuke your token usage. Code indexing MCP server: 15 tools, 10 languages, O(1)... | 76 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-bigjai-tokennuke) |
| [curate-ipsum](https://github.com/egoughnour/curate-ipsum) | A mutation-testing and program-synthesis platform that runs unit/integration/... | 73 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-egoughnour-curate-ipsum) |
| [ZenLink-MCP](https://github.com/JayQuan-McCleary/ZenLink-MCP) | Browser automation bridge for Zen Browser and Firefox, providing programmatic... | 73 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-jayquan-mccleary-zenlink-mcp) |
| [mcp-python-exec-sandbox](https://github.com/lu-zhengda/mcp-python-exec-sandbox) | A Python code execution server with automatic dependency management via PEP 7... | 72 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-lu-zhengda-mcp-python-exec-sandbox) |
| [massive-context-mcp](https://github.com/egoughnour/massive-context-mcp) | A recursive large-context processing server that loads, chunks, filters, and ... | 69 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-egoughnour-massive-context-mcp) |
| [mcp-gitlab](https://github.com/crunchtools/mcp-gitlab) | A comprehensive GitLab MCP server providing full API access for project, repo... | 68 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-gitlab) |

### 🔍 <a name="search--knowledge"></a>Search & Knowledge

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [airweave-mcp-search](https://github.com/airweave-ai/airweave) | Open-source context retrieval layer for AI agents | 92 ✅ | 6.0k | [View](https://agentseal.org/mcp/airweave-mcp-search) |
| [exa-mcp-server](https://github.com/exa-labs/exa-mcp-server) | Exa MCP for web search and web crawling! | 84 ✅ | 4.0k | [View](https://agentseal.org/mcp/exa-mcp-server) |
| [exa-mcp-server](https://github.com/exa-labs/exa-mcp-server) | Connect AI assistants to Exa's search capabilities for web search, code searc... | 84 ✅ | 4.0k | [View](https://agentseal.org/mcp/https-githubcom-exa-labs-exa-mcp-server) |
| [arxiv-mcp-server](https://github.com/blazickjp/arxiv-mcp-server) | An MCP server enabling AI assistants to search, download, and analyze arXiv r... | 79 ⚠️ | 2.3k | [View](https://agentseal.org/mcp/https-githubcom-blazickjp-arxiv-mcp-server) |
| [open-webSearch](https://github.com/Aas-ee/open-webSearch) | WebSearchMCP using free multi-engine search (NO API KEYS REQUIRED) — Supports... | 74 ⚠️ | 790 | [View](https://agentseal.org/mcp/https-githubcom-aas-ee-open-websearch) |
| [howtocook-mcp](https://github.com/worryzyy/howtocook-mcp) | 基于Anduin2017 / HowToCook （程序员在家做饭指南）的mcp server | 86 ✅ | 697 | [View](https://agentseal.org/mcp/https-githubcom-worryzyy-howtocook-mcp) |
| [mcp-gsc](https://github.com/aminforou/mcp-gsc) | Google Search Console Insights with Claude AI for SEOs | 84 ✅ | 535 | [View](https://agentseal.org/mcp/mcp-gsc) |
| [zotero-mcp](https://github.com/cookjohn/zotero-mcp) | It's a plugin extension in Zotero.  Zotero MCP Plugin enables integration bet... | 90 ✅ | 460 | [View](https://agentseal.org/mcp/https-githubcom-cookjohn-zotero-mcp) |
| [graphlit-mcp-server](https://github.com/graphlit/graphlit-mcp-server) | Model Context Protocol (MCP) Server for Graphlit Platform | 72 ⚠️ | 372 | [View](https://agentseal.org/mcp/https-githubcom-graphlit-graphlit-mcp-server) |
| [gptr-mcp](https://github.com/assafelovic/gptr-mcp) | MCP server for enabling LLM applications to perform deep research via the MCP... | 84 ✅ | 330 | [View](https://agentseal.org/mcp/https-githubcom-assafelovic-gptr-mcp) |
| [idea-reality-mcp](https://github.com/mnemox-ai/idea-reality-mcp) | A research assistant that checks whether a product idea already exists by que... | 98 ✅ | 316 | [View](https://agentseal.org/mcp/https-githubcom-mnemox-ai-idea-reality-mcp) |
| [deep-research-mcp](https://github.com/ozamatash/deep-research-mcp) | AI-powered research assistant that performs deep, iterative research on topic... | 92 ✅ | 315 | [View](https://agentseal.org/mcp/https-githubcom-ozamatash-deep-research-mcp) |
| [memora](https://github.com/agentic-mcp-tools/memora) | A persistent memory management server providing create/read/update/delete, se... | 64 ⚠️ | 309 | [View](https://agentseal.org/mcp/https-githubcom-agentic-mcp-tools-memora) |
| [mcp-server-google-scholar](https://github.com/jackkuo666/google-scholar-mcp-server) | A MCP Server for Google Scholar: 🔍 Enable AI assistants to search and access ... | 91 ✅ | 247 | [View](https://agentseal.org/mcp/mcp-server-google-scholar) |
| [mcp-trends-hub](https://github.com/baranwang/mcp-trends-hub) | 基于 Model Context Protocol (MCP) 协议的全网热点趋势一站式聚合服务 | 92 ✅ | 228 | [View](https://agentseal.org/mcp/https-githubcom-baranwang-mcp-trends-hub) |
| [mcp-simple-arxiv](https://github.com/andybrandt/mcp-simple-arxiv) | An MCP server that provides search, retrieval, and full-text extraction of ac... | 84 ✅ | 185 | [View](https://agentseal.org/mcp/https-githubcom-andybrandt-mcp-simple-arxiv) |
| [meilisearch-mcp](https://github.com/meilisearch/meilisearch-mcp) | A Model Context Protocol (MCP) server for interacting with Meilisearch throug... | 79 ⚠️ | 178 | [View](https://agentseal.org/mcp/https-githubcom-meilisearch-meilisearch-mcp) |
| [mlit-dpf-mcp](https://github.com/mlit-data-platform/mlit-dpf-mcp) | MCP server connecting to Japan's MLIT government data platform enabling natur... | 88 ✅ | 130 | [View](https://agentseal.org/mcp/https-githubcom-mlit-data-platform-mlit-dpf-mcp) |
| [google-news-server](https://github.com/ChanMeng666/server-google-news) | 【Star-crossed coders unite!⭐️】Model Context Protocol (MCP) server implementat... | 92 ✅ | 113 | [View](https://agentseal.org/mcp/chanmeng666-google-news-server) |
| [lightrag-mcp](https://github.com/shemhamforash23/lightrag-mcp) | MCP server bridging LightRAG API with AI tools, enabling retrieval-augmented ... | 79 ⚠️ | 107 | [View](https://agentseal.org/mcp/https-githubcom-shemhamforash23-lightrag-mcp) |
| [mcp-server-perplexity](https://github.com/tanigami/mcp-server-perplexity) | MCP server that integrates with Perplexity API to provide chat completions wi... | 92 ✅ | 92 | [View](https://agentseal.org/mcp/https-githubcom-tanigami-mcp-server-perplexity) |
| [openai-websearch-mcp](https://github.com/ConechoAI/openai-websearch-mcp) | MCP server providing intelligent web search capabilities using OpenAI's reaso... | 91 ✅ | 86 | [View](https://agentseal.org/mcp/https-githubcom-conechoai-openai-websearch-mcp) |
| [octagon-deep-research-mcp](https://github.com/OctagonAI/octagon-deep-research-mcp) | Octagon Deep Research MCP provides AI-powered comprehensive research and anal... | 92 ✅ | 84 | [View](https://agentseal.org/mcp/octagon-deep-research-mcp) |
| [mcp-open-library](https://github.com/8enSmith/mcp-open-library) | A Model Context Protocol (MCP) server for the Internet Archive's Open Library... | 100 ✅ | 62 | [View](https://agentseal.org/mcp/https-githubcom-8ensmith-mcp-open-library) |
| [mcp-osint-server](https://github.com/himanshusanecha/mcp-osint-server) | MCP server for performing OSINT investigations through network reconnaissance... | 92 ✅ | 43 | [View](https://agentseal.org/mcp/https-githubcom-himanshusanecha-mcp-osint-server) |
| [context-awesome](https://github.com/bh-rat/context-awesome) | A read-only search and retrieval server for browsing curated 'awesome list' r... | 90 ✅ | 41 | [View](https://agentseal.org/mcp/https-githubcom-bh-rat-context-awesome) |
| [mcp-server-leetcode](https://github.com/doggybee/mcp-server-leetcode) | A read-only MCP server that wraps the public LeetCode GraphQL API to fetch pr... | 99 ✅ | 40 | [View](https://agentseal.org/mcp/https-githubcom-doggybee-mcp-server-leetcode) |
| [mlb-api-mcp](https://github.com/guillochon/mlb-api-mcp) | A read-only MCP server that exposes MLB Stats API and Statcast data including... | 96 ✅ | 39 | [View](https://agentseal.org/mcp/https-githubcom-guillochon-mlb-api-mcp) |
| [mcp-searxng-enhanced](https://github.com/OvertliDS/mcp-searxng-enhanced) | Enhanced MCP server for SearXNG: category-aware web-search, web-scraping, and... | 86 ✅ | 35 | [View](https://agentseal.org/mcp/https-githubcom-overtlids-mcp-searxng-enhanced) |
| [bgg-mcp](https://github.com/kkjdaniel/bgg-mcp) | BGG MCP provides access to BoardGameGeek and a variety of board game related ... | 86 ✅ | 32 | [View](https://agentseal.org/mcp/https-githubcom-kkjdaniel-bgg-mcp) |
| [brlaw_mcp_server](https://github.com/pdmtt/brlaw_mcp_server) | A read-only MCP server for searching Brazilian superior court legal precedent... | 100 ✅ | 27 | [View](https://agentseal.org/mcp/https-githubcom-pdmtt-brlawmcpserver) |
| [kagi-ken-mcp](https://github.com/czottmann/kagi-ken-mcp) | A two-tool MCP server that provides web search and URL summarization via the ... | 95 ✅ | 25 | [View](https://agentseal.org/mcp/https-githubcom-czottmann-kagi-ken-mcp) |
| [mcp-dblp](https://github.com/szeider/mcp-dblp) | An MCP server that searches the DBLP academic publication database, retrieves... | 88 ✅ | 25 | [View](https://agentseal.org/mcp/https-githubcom-szeider-mcp-dblp) |
| [open-notebook-mcp](https://github.com/Epochal-dev/open-notebook-mcp) | A personal knowledge management MCP server that manages notebooks, notes, sou... | 67 ⚠️ | 19 | [View](https://agentseal.org/mcp/https-githubcom-epochal-dev-open-notebook-mcp) |
| [cbi-mcp-server](https://github.com/cbinsights/cbi-mcp-server) | CB Insights' MCP Server | 98 ✅ | 11 | [View](https://agentseal.org/mcp/https-githubcom-cbinsights-cbi-mcp-server) |
| [mcp-claude-hackernews](https://github.com/imprvhub/mcp-claude-hackernews) | A read-only Hacker News client that fetches public stories and comments from ... | 100 ✅ | 10 | [View](https://agentseal.org/mcp/https-githubcom-imprvhub-mcp-claude-hackernews) |
| [google-pse-mcp](https://github.com/rendyfebry/google-pse-mcp) | A Model Context Protocol (MCP) server for the Google Programmable Search Engi... | 92 ✅ | 10 | [View](https://agentseal.org/mcp/https-githubcom-rendyfebry-google-pse-mcp) |
| [bible-mcp](https://github.com/trevato/bible-mcp) | A read-only MCP server that retrieves Bible verses by reference or randomly, ... | 97 ✅ | 9 | [View](https://agentseal.org/mcp/https-githubcom-trevato-bible-mcp) |
| [driflyte-mcp-server](https://github.com/serkan-ozal/driflyte-mcp-server) | MCP server that exposes tools for AI assistants to query and retrieve topic-s... | 81 ✅ | 9 | [View](https://agentseal.org/mcp/https-githubcom-serkan-ozal-driflyte-mcp-server) |
| [docsmcp](https://github.com/da1z/docsmcp) | A documentation retrieval server that lists available documentation sources a... | 90 ✅ | 8 | [View](https://agentseal.org/mcp/https-githubcom-da1z-docsmcp) |
| [doi-mcp](https://github.com/tfscharff/doi-mcp) | A Model Context Protocol (MCP) server to prevent citation hallucination in AI... | 86 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-tfscharff-doi-mcp) |
| [mcp_pearch](https://github.com/Pearch-ai/mcp_pearch) | The most accurate people search API/MCP. Natural language in, high-quality ca... | 86 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-pearch-ai-mcppearch) |
| [bgpt-mcp](https://github.com/connerlambden/bgpt-mcp) | A single-tool MCP server that queries the BGPT database of scientific papers ... | 91 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-connerlambden-bgpt-mcp) |
| [google_maps_mcp](https://github.com/Mastan1301/google_maps_mcp) | A single-tool MCP server that queries the Google Maps Places API to find near... | 99 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-mastan1301-googlemapsmcp) |
| [mcp-search-server](https://github.com/KazKozDev/mcp-search-server) | A multi-purpose search and utility MCP server providing web search (DuckDuckG... | 74 ⚠️ | 4 | [View](https://agentseal.org/mcp/https-githubcom-kazkozdev-mcp-search-server) |
| [shahnameh-mcp-server](https://github.com/aliafsahnoudeh/shahnameh-mcp-server) | A read-only MCP server providing access to chapters, verses, and vector-searc... | 94 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-aliafsahnoudeh-shahnameh-mcp-server) |
| [Weather-MCP](https://github.com/shuowang-ai/Weather-MCP) | Real-time weather, air quality monitoring, and forecasting powered by Caiyun ... | 91 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-shuowang-ai-weather-mcp) |
| [igdb-mcp-server](https://github.com/bielacki/igdb-mcp-server) | An MCP server that provides read-only access to the IGDB (Internet Game Datab... | 89 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-bielacki-igdb-mcp-server) |
| [evc-spark-mcp](https://github.com/entire-vc/evc-spark-mcp) | MCP connector for the Spark AI asset marketplace, enabling search and retriev... | 81 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-entire-vc-evc-spark-mcp) |
| [trinvmcp](https://github.com/cqtrinv/trinvmcp) | A read-only MCP server for searching French municipalities by name fragment a... | 100 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-cqtrinv-trinvmcp) |
| [opendota-mcp-server](https://github.com/hkaanengin/opendota-mcp-server) | A read-only Dota 2 statistics server that queries the OpenDota public API for... | 98 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-hkaanengin-opendota-mcp-server) |
| [gitlab-docs-mcp](https://github.com/nunolima/gitlab-docs-mcp) | GitLab Documentation MCP Server | 90 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-nunolima-gitlab-docs-mcp) |
| [generect_mcp.git](https://github.com/generect/generect_mcp.git) | Generect MCP provides B2B sales prospecting tools: LinkedIn lead/company sear... | 88 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-generect-generectmcpgit) |
| [ai-dictionary-mcp](https://github.com/donjguido/ai-dictionary-mcp) | MCP server providing access to Phenomenai, a glossary of AI phenomenology ter... | 79 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-donjguido-ai-dictionary-mcp) |
| [lapalma24-mcp](https://github.com/La-Palma-24/lapalma24-mcp) | MCP server for searching and discovering vacation rental properties in La Pal... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-la-palma-24-lapalma24-mcp) |
| [weather-server-python](https://github.com/lxchst/weather-server-python) | A read-only MCP server that retrieves US weather alerts by state and weather ... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-lxchst-weather-server-python) |
| [mcp-server](https://github.com/DealExpress/mcp-server) | Read-only MCP server for searching classified ads on the DealX/DealExpress ma... | 94 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-dealexpress-mcp-server) |
| [reddit-insights-mcp](https://github.com/lignertys/reddit-insights-mcp) | A read-only Reddit intelligence server that enables semantic search, subreddi... | 94 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-lignertys-reddit-insights-mcp) |
| [mercadolibre-mcp](https://github.com/dan1d/mercadolibre-mcp) | Read-only MercadoLibre marketplace API client for searching products, retriev... | 94 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-dan1d-mercadolibre-mcp) |
| [obris-mcp](https://github.com/obris-dev/obris-mcp) | A knowledge base MCP that allows AI agents to list, read, create, and update ... | 85 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-obris-dev-obris-mcp) |
| [bing-search-mcp](https://github.com/iridite/bing-search-mcp) | Free Bing search MCP server for Claude Code - No API key required | 84 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-iridite-bing-search-mcp) |
| [mcp-mediawiki](https://github.com/crunchtools/mcp-mediawiki) | Secure MCP server for MediaWiki wikis with search, read, write, and managemen... | 74 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-mediawiki) |
| [labmate-mcp](https://github.com/JonasRackl/labmate-mcp) | Your AI lab companion — 78 MCP tools for literature, compounds, synthesis, be... | 71 ⚠️ | - | [View](https://agentseal.org/mcp/labmate-mcp) |

### 💻 <a name="code--ide"></a>Code & IDE

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [Serena](https://github.com/oraios/serena) | Turns an LLM into a coding agent that works directly on your codebase by prov... | 62 ⚠️ | 21.4k | [View](https://agentseal.org/mcp/https-githubcom-oraios-serena) |
| [ghidramcp](https://github.com/lauriewired/ghidramcp) | MCP Server for Ghidra | 86 ✅ | 7.9k | [View](https://agentseal.org/mcp/https-githubcom-lauriewired-ghidramcp) |
| [@sourcebot](https://github.com/sourcebot-dev/sourcebot) | Self-hosted tool that helps developers understand codebases through AI-powere... | 92 ✅ | 3.2k | [View](https://agentseal.org/mcp/sourcebot) |
| [codegraphcontext](https://github.com/shashankss1205/codegraphcontext) | An MCP server and CLI toolkit that indexes local code repositories into a gra... | 81 ✅ | 2.0k | [View](https://agentseal.org/mcp/https-githubcom-shashankss1205-codegraphcontext) |
| [mcp-language-server](https://github.com/isaacphi/mcp-language-server) | MCP server exposing language server protocol tools to LLMs for semantic code ... | 88 ✅ | 1.5k | [View](https://agentseal.org/mcp/https-githubcom-isaacphi-mcp-language-server) |
| [ref-tools-mcp](https://github.com/ref-tools/ref-tools-mcp) | Helping coding agents never make mistakes working with public or private libr... | 81 ✅ | 1.0k | [View](https://agentseal.org/mcp/https-githubcom-ref-tools-ref-tools-mcp) |
| [octocode-mcp](https://github.com/bgauryy/octocode-mcp) | MCP server for semantic code research and context generation on real-time usi... | 77 ⚠️ | 750 | [View](https://agentseal.org/mcp/octocode-mcp) |
| [next-devtools-mcp](https://github.com/vercel/next-devtools-mcp) | Next.js Development for Coding Agent | 67 ⚠️ | 673 | [View](https://agentseal.org/mcp/https-githubcom-vercel-next-devtools-mcp) |
| [overture-mcp](https://github.com/sixhq/overture) | Locally running MCP server that visualizes AI coding agent execution plans as... | 90 ✅ | 597 | [View](https://agentseal.org/mcp/overture-mcp) |
| [unitymcp](https://github.com/arodoid/unitymcp) | UnityMCP is a Unity Editor plugin implementing Model Context Protocol for AI ... | 92 ✅ | 510 | [View](https://agentseal.org/mcp/https-githubcom-arodoid-unitymcp) |
| [binary_ninja_mcp](https://github.com/fosdickio/binary_ninja_mcp) | A Binary Ninja plugin containing an MCP server that enables seamless integrat... | 84 ✅ | 264 | [View](https://agentseal.org/mcp/https-githubcom-fosdickio-binaryninjamcp) |
| [claude-context-local](https://github.com/farhanaliraza/claude-context-local) | Code search MCP for Claude Code. Make entire codebase the context for any cod... | 84 ✅ | 200 | [View](https://agentseal.org/mcp/claude-context-local) |
| [mcp-package-version](https://github.com/sammcj/mcp-package-version) | An MCP server that provides LLMs with the latest stable package versions when... | 86 ✅ | 121 | [View](https://agentseal.org/mcp/mcp-package-version) |
| [deep-code-reasoning-mcp](https://github.com/haasonsaas/deep-code-reasoning-mcp) | A Model Context Protocol (MCP) server that provides advanced code analysis an... | 89 ✅ | 102 | [View](https://agentseal.org/mcp/https-githubcom-haasonsaas-deep-code-reasoning-mcp) |
| [owlex](https://github.com/agentic-mcp-tools/owlex) | An AI council orchestration MCP that spawns and manages sessions with multipl... | 82 ✅ | 74 | [View](https://agentseal.org/mcp/https-githubcom-agentic-mcp-tools-owlex) |
| [ipybox](https://github.com/gradion-ai/ipybox) | An IPython-based code execution sandbox that allows agents to run arbitrary P... | 71 ⚠️ | 71 | [View](https://agentseal.org/mcp/https-githubcom-gradion-ai-ipybox) |
| [codelogic-mcp-server](https://github.com/CodeLogicIncEngineering/codelogic-mcp-server) | MCP Server integrating Codelogic's software dependency data for AI assistants... | 90 ✅ | 35 | [View](https://agentseal.org/mcp/https-githubcom-codelogicincengineering-codelogic-mcp-server) |
| [codesurface](https://github.com/Codeturion/codesurface) | A local codebase indexer that lets agents search, inspect, and retrieve API s... | 92 ✅ | 19 | [View](https://agentseal.org/mcp/https-githubcom-codeturion-codesurface) |
| [local-history-mcp](https://github.com/xxczaki/local-history-mcp) | MCP server for accessing VS Code/Cursor's Local History | 92 ✅ | 12 | [View](https://agentseal.org/mcp/https-githubcom-xxczaki-local-history-mcp) |
| [mcp-vscode-template](https://github.com/timsonner/mcp-vscode-template) | MCP server template for VS Code | 91 ✅ | 8 | [View](https://agentseal.org/mcp/https-githubcom-timsonner-mcp-vscode-template) |
| [jebmcp](https://github.com/pcjaat3844/jebmcp) | jebmcp is a lightweight tool for managing and processing batch jobs in cloud ... | 89 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-pcjaat3844-jebmcp) |
| [judges](https://github.com/kevinrabun/judges) | MCP server with specialized judges to evaluate AI-generated code for security... | 81 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-kevinrabun-judges) |
| [clj-kondo-MCP](https://github.com/Bigsy/clj-kondo-MCP) | MCP server providing clj-kondo linting for Clojure, ClojureScript, and EDN fi... | 89 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-bigsy-clj-kondo-mcp) |
| [jadx-daemon-mcp](https://github.com/wrlu/jadx-daemon-mcp) | A jadx daemon service MCP server. | 88 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-wrlu-jadx-daemon-mcp) |
| [silverstripe-mcp](https://github.com/sandervanscheepen/silverstripe-mcp) | MCP server that provides real-time validation feedback when AI assistants gen... | 83 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-sandervanscheepen-silverstripe-mcp) |
| [shadcn-registry-manager](https://github.com/reuvenaor/shadcn-registry-manager) | MCP shadcn registry cli manager | 92 ✅ | 1 | [View](https://agentseal.org/mcp/reuvenorg-shadcn-registry-manager) |
| [impact-preview](https://github.com/agent-polis/impact-preview) | Preview and approve AI agent actions before execution, showing file diffs and... | 82 ✅ | 1 | [View](https://agentseal.org/mcp/impact-preview) |
| [context7fork](https://github.com/renCosta2025/context7fork) | Up-to-date code documentation and version-specific examples for LLMs and AI c... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-rencosta2025-context7fork) |
| [git-mob-mcp-server](https://github.com/Mubashwer/git-mob-mcp-server) | MCP server for git-mob CLI app that manages co-authors for pair and mob progr... | 81 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-mubashwer-git-mob-mcp-server) |
| [claudecodenavi-mcp](https://github.com/saikiyusuke/claudecodenavi-mcp) | ClaudeCodeNavi MCP Server - Claude Code knowledge platform & marketplace | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-saikiyusuke-claudecodenavi-mcp) |
| [codemunch-pro](https://github.com/BigJai/codemunch-pro) | Intelligent code indexing MCP server. 13 tools, 10 languages, hybrid search, ... | 72 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-bigjai-codemunch-pro) |

### ☁️ <a name="cloud--infrastructure"></a>Cloud & Infrastructure

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [mcp](https://github.com/awslabs/mcp) | Official MCP Servers for AWS | 86 ✅ | 8.4k | [View](https://agentseal.org/mcp/https-githubcom-awslabs-mcp) |
| [mcp-grafana](https://github.com/grafana/mcp-grafana) | MCP server for Grafana | 78 ⚠️ | 2.5k | [View](https://agentseal.org/mcp/https-githubcom-grafana-mcp-grafana) |
| [mcp-server-kubernetes](https://github.com/Flux159/mcp-server-kubernetes) | MCP Server for kubernetes management commands | 81 ✅ | 1.3k | [View](https://agentseal.org/mcp/mcp-server-kubernetes) |
| [azure-mcp](https://github.com/azure/azure-mcp) | The Azure MCP Server, bringing the power of Azure to your agents. | 74 ⚠️ | 1.2k | [View](https://agentseal.org/mcp/https-githubcom-azure-azure-mcp) |
| [cloud-run-mcp](https://github.com/GoogleCloudPlatform/cloud-run-mcp) | A Google Cloud Platform MCP server for managing and deploying Cloud Run servi... | 87 ✅ | 560 | [View](https://agentseal.org/mcp/https-githubcom-googlecloudplatform-cloud-run-mcp) |
| [mcp](https://github.com/hopx-ai/mcp) | A cloud sandbox execution platform that provides isolated containers for runn... | 58 ⚠️ | 165 | [View](https://agentseal.org/mcp/https-githubcom-hopx-ai-mcp) |
| [spotinfo](https://github.com/alexei-led/spotinfo) | CLI for exploring AWS EC2 Spot inventory. Inspect AWS Spot instance types, sa... | 92 ✅ | 158 | [View](https://agentseal.org/mcp/https-githubcom-alexei-led-spotinfo) |
| [hub-mcp](https://github.com/docker/hub-mcp) | Provides read and write access to Docker Hub repositories, tags, namespaces, ... | 86 ✅ | 130 | [View](https://agentseal.org/mcp/https-githubcom-docker-hub-mcp) |
| [mcp-server-aws](https://github.com/rishikavikondala/mcp-server-aws) | Provides full CRUD access to AWS S3 buckets/objects and DynamoDB tables/items... | 74 ⚠️ | 128 | [View](https://agentseal.org/mcp/https-githubcom-rishikavikondala-mcp-server-aws) |
| [aws-cost-explorer-mcp-server](https://github.com/aarora79/aws-cost-explorer-mcp-server) | MCP server for analyzing AWS spend data via Cost Explorer and Bedrock usage t... | 90 ✅ | 127 | [View](https://agentseal.org/mcp/https-githubcom-aarora79-aws-cost-explorer-mcp-server) |
| [aks-mcp](https://github.com/Azure/aks-mcp) | A Model Context Protocol (MCP) server that enables AI assistants to interact ... | 86 ✅ | 121 | [View](https://agentseal.org/mcp/https-githubcom-azure-aks-mcp) |
| [heroku-mcp-server](https://github.com/heroku/heroku-mcp-server) | Official Heroku MCP server for managing Heroku apps, databases, dynos, pipeli... | 65 ⚠️ | 75 | [View](https://agentseal.org/mcp/https-githubcom-heroku-heroku-mcp-server) |
| [mcp-netbird](https://github.com/aantti/mcp-netbird) | MCP Server for Netbird | 92 ✅ | 42 | [View](https://agentseal.org/mcp/https-githubcom-aantti-mcp-netbird) |
| [apisix-mcp](https://github.com/api7/apisix-mcp) | An MCP server for managing Apache APISIX API gateway resources including rout... | 67 ⚠️ | 34 | [View](https://agentseal.org/mcp/https-githubcom-api7-apisix-mcp) |
| [cos-mcp](https://github.com/Tencent/cos-mcp) | 基于 MCP 协议的腾讯云 COS MCP Server，无需编码即可让大模型快速接入腾讯云存储 (COS) 和数据万象 (CI) 能力。 | 85 ✅ | 30 | [View](https://agentseal.org/mcp/https-githubcom-tencent-cos-mcp) |
| [ig-mcp-server](https://github.com/inspektor-gadget/ig-mcp-server) | Debug your Container and Kubernetes workloads with an AI interface | 92 ✅ | 22 | [View](https://agentseal.org/mcp/https-githubcom-inspektor-gadget-ig-mcp-server) |
| [aws-pricing-mcp](https://github.com/trilogy-group/aws-pricing-mcp) | An MCP server that exposes AWS EC2 pricing data with an option to search by C... | 92 ✅ | 20 | [View](https://agentseal.org/mcp/https-githubcom-trilogy-group-aws-pricing-mcp) |
| [azure-resource-graph-mcp-server](https://github.com/hardik-id/azure-resource-graph-mcp-server) | An MCP server that queries Azure Resource Graph using KQL to enumerate, filte... | 90 ✅ | 17 | [View](https://agentseal.org/mcp/https-githubcom-hardik-id-azure-resource-graph-mcp-server) |
| [consul-mcp-server](https://github.com/kocierik/consul-mcp-server) | A full-featured HashiCorp Consul management server providing service discover... | 82 ✅ | 16 | [View](https://agentseal.org/mcp/https-githubcom-kocierik-consul-mcp-server) |
| [conductor-mcp](https://github.com/conductor-oss/conductor-mcp) | An MCP server for managing Netflix Conductor workflow orchestration: creating... | 70 ⚠️ | 14 | [View](https://agentseal.org/mcp/https-githubcom-conductor-oss-conductor-mcp) |
| [mcp-server-aws-sso](https://github.com/aashari/mcp-server-aws-sso) | Node.js/TypeScript MCP server for AWS Single Sign-On (SSO). Enables AI system... | 78 ⚠️ | 12 | [View](https://agentseal.org/mcp/https-githubcom-aashari-mcp-server-aws-sso) |
| [teamcity-mcp](https://github.com/itcaat/teamcity-mcp) | Teamcity MCP Server | 80 ⚠️ | 11 | [View](https://agentseal.org/mcp/itcaat-teamcity-mcp) |
| [helm-chart-cli-mcp](https://github.com/jeff-nasseri/helm-chart-cli-mcp) | MCP server that bridges AI assistants with Helm package manager, enabling nat... | 80 ⚠️ | 7 | [View](https://agentseal.org/mcp/https-githubcom-jeff-nasseri-helm-chart-cli-mcp) |
| [porkbun-mcp](https://github.com/major/porkbun-mcp) | MCP server for managing DNS records, domain settings, DNSSEC, SSL certificate... | 89 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-major-porkbun-mcp) |
| [lumino-mcp-server](https://github.com/spre-sre/lumino-mcp-server) | AI-powered diagnostic engine for SRE observability on Kubernetes and OpenShif... | 84 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-spre-sre-lumino-mcp-server) |
| [deploy-mcp](https://github.com/alexpota/deploy-mcp) | A read-only MCP server for monitoring deployment status, logs, and project li... | 96 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-alexpota-deploy-mcp) |
| [hosting-mcp](https://github.com/4everland/4everland-hosting-mcp) | MCP server for instant deployment of AI-generated code to decentralized stora... | 92 ✅ | 2 | [View](https://agentseal.org/mcp/4everland-hosting-mcp) |
| [mcp-google-analytics](https://github.com/gomakers-ai/mcp-google-analytics) | MCP server for Google Analytics 4, enabling reading reports via Data API and ... | 82 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-gomakers-ai-mcp-google-analytics) |
| [azure-updates-mcp](https://github.com/jonnybottles/azure-updates-mcp) | Read-only search interface for Microsoft Azure service updates sourced from t... | 94 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-jonnybottles-azure-updates-mcp) |
| [GooglePlayConsoleMcp](https://github.com/AgiMaulana/GooglePlayConsoleMcp) | MCP server wrapping the Google Play Developer API to manage release tracks, u... | 80 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-agimaulana-googleplayconsolemcp) |
| [shipi-mcp-server](https://github.com/aarsiv-groups/shipi-mcp-server) | A shipping logistics MCP server for the Shipi platform that enables shipment ... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-aarsiv-groups-shipi-mcp-server) |
| [powerbi-mcp](https://github.com/gurvinder-dhillon/powerbi-mcp) | MCP server for interacting with PowerBI REST APIs, enabling DAX queries and w... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-gurvinder-dhillon-powerbi-mcp) |
| [mycrab-mcp](https://github.com/isgudtek/mycrab-mcp) | A tunneling service that gives AI agents public HTTPS URLs via Cloudflare Tun... | 82 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-isgudtek-mycrab-mcp) |
| [mcp-cloudflare](https://github.com/crunchtools/mcp-cloudflare) | A Cloudflare management MCP server exposing DNS records, WAF rules, page rule... | 79 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-cloudflare) |
| [mcp-proxmox](https://github.com/antonio-mello-ai/mcp-proxmox) | A Proxmox VE cluster management MCP server providing full lifecycle control o... | 72 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-antonio-mello-ai-mcp-proxmox) |

### 📝 <a name="content--media"></a>Content & Media

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [blender-mcp](https://github.com/ahujasid/blender-mcp) | A Blender automation MCP server that allows AI agents to control Blender scen... | 66 ⚠️ | 17.7k | [View](https://agentseal.org/mcp/https-githubcom-ahujasid-blender-mcp) |
| [markdownify-mcp](https://github.com/zcaceres/markdownify-mcp) | A Model Context Protocol server for converting almost anything to Markdown | 83 ✅ | 2.4k | [View](https://agentseal.org/mcp/https-githubcom-zcaceres-markdownify-mcp) |
| [ableton-mcp](https://github.com/ahujasid/ableton-mcp) | An MCP server that provides programmatic control over Ableton Live sessions, ... | 89 ✅ | 2.3k | [View](https://agentseal.org/mcp/https-githubcom-ahujasid-ableton-mcp) |
| [mcp](https://github.com/caol64/wenyan-mcp) | 文颜 MCP Server 可以让 AI 自动将 Markdown 文章排版后发布至微信公众号。 | 85 ✅ | 1.1k | [View](https://agentseal.org/mcp/wenyan-md-mcp) |
| [wenyan-mcp](https://github.com/caol64/wenyan-mcp) | 文颜 MCP Server 可以让 AI 自动将 Markdown 文章排版后发布至微信公众号。 | 84 ✅ | 1.1k | [View](https://agentseal.org/mcp/https-githubcom-caol64-wenyan-mcp) |
| [mcp-server-weread](https://github.com/freestylefly/mcp-server-weread) | 微信读书MCP | 92 ✅ | 528 | [View](https://agentseal.org/mcp/https-githubcom-freestylefly-mcp-server-weread) |
| [mcp-server-weread](https://github.com/freestylefly/mcp-server-weread) | 微信读书MCP | 92 ✅ | 528 | [View](https://agentseal.org/mcp/mcp-server-weread) |
| [mcp-pandoc](https://github.com/vivekvells/mcp-pandoc) | MCP server for seamless document format conversion using pandoc, transforming... | 91 ✅ | 512 | [View](https://agentseal.org/mcp/https-githubcom-vivekvells-mcp-pandoc) |
| [adb-mcp](https://github.com/mikechambers/adb-mcp) | MCP server enabling AI models to control Adobe Creative Suite applications (P... | 89 ✅ | 504 | [View](https://agentseal.org/mcp/https-githubcom-mikechambers-adb-mcp) |
| [mcp-server-youtube-transcript](https://github.com/kimtaeyoon83/mcp-server-youtube-transcript) | An MCP server that retrieves transcripts from YouTube videos, providing direc... | 86 ✅ | 494 | [View](https://agentseal.org/mcp/https-githubcom-kimtaeyoon83-mcp-server-youtube-transcript) |
| [ebook-mcp](https://github.com/onebirdrocks/ebook-mcp) | A MCP server that supports mainstream eBook formats including EPUB, PDF and m... | 74 ⚠️ | 351 | [View](https://agentseal.org/mcp/ebook-mcp) |
| [mcp-youtube-transcript](https://github.com/jkawamoto/mcp-youtube-transcript) | Retrieves YouTube video transcripts (plain and timestamped) and basic video m... | 93 ✅ | 339 | [View](https://agentseal.org/mcp/https-githubcom-jkawamoto-mcp-youtube-transcript) |
| [after-effects-mcp](https://github.com/dakkshin/after-effects-mcp) | MCP Server for Adobe After Effects. Enables remote control (compositions, tex... | 85 ✅ | 237 | [View](https://agentseal.org/mcp/https-githubcom-dakkshin-after-effects-mcp) |
| [mcp-summarizer](https://github.com/0xshellming/mcp-summarizer) | MCP Server for AI Summarization | 100 ✅ | 157 | [View](https://agentseal.org/mcp/https-githubcom-0xshellming-mcp-summarizer) |
| [bilibili-mcp-js](https://github.com/34892002/bilibili-mcp-js) | Bilibili video search MCP (Model Context Protocol) service - 哔哩哔哩视频搜索MCP服务 | 99 ✅ | 153 | [View](https://agentseal.org/mcp/https-githubcom-34892002-bilibili-mcp-js) |
| [powerpoint](https://github.com/supercurses/powerpoint) | A MCP Server for creating Powerpoint Presentations | 90 ✅ | 144 | [View](https://agentseal.org/mcp/https-githubcom-supercurses-powerpoint) |
| [aseprite-mcp](https://github.com/diivi/aseprite-mcp) | An MCP server that drives the Aseprite pixel-art editor to create canvases, d... | 88 ✅ | 133 | [View](https://agentseal.org/mcp/https-githubcom-diivi-aseprite-mcp) |
| [flyworks-mcp](https://github.com/Flyworks-AI/flyworks-mcp) | MCP server for fast, free zeroshot lipsync video creation. Animates digital a... | 90 ✅ | 93 | [View](https://agentseal.org/mcp/https-githubcom-flyworks-ai-flyworks-mcp) |
| [mcp-applemusic](https://github.com/kennethreitz/mcp-applemusic) | A FastMCP server for controlling Apple Music on macOS through AppleScript com... | 81 ✅ | 76 | [View](https://agentseal.org/mcp/https-githubcom-kennethreitz-mcp-applemusic) |
| [raindrop-io-mcp-server](https://github.com/hiromitsusasaki/raindrop-io-mcp-server) | A read/write MCP server for managing Raindrop.io bookmarks: create bookmarks,... | 90 ✅ | 72 | [View](https://agentseal.org/mcp/https-githubcom-hiromitsusasaki-raindrop-io-mcp-server) |
| [anilist-mcp](https://github.com/yuna0x0/anilist-mcp) | AniList MCP server for accessing anime and manga data | 84 ✅ | 71 | [View](https://agentseal.org/mcp/anilist-mcp) |
| [keep-mcp](https://github.com/feuerdev/keep-mcp) | An MCP server for managing Google Keep notes, supporting CRUD operations on n... | 74 ⚠️ | 64 | [View](https://agentseal.org/mcp/https-githubcom-feuerdev-keep-mcp) |
| [dws-mcp-server](https://github.com/pspdfkit/nutrient-dws-mcp-server) | A Model Context Protocol (MCP) server implementation that integrates with the... | 87 ✅ | 63 | [View](https://agentseal.org/mcp/nutrient-sdk-dws-mcp-server) |
| [mcp-server-atlassian-confluence](https://github.com/aashari/mcp-server-atlassian-confluence) | Node.js/TypeScript MCP server for Atlassian Confluence. Provides tools enabli... | 76 ⚠️ | 50 | [View](https://agentseal.org/mcp/https-githubcom-aashari-mcp-server-atlassian-confluence) |
| [mcp-apple-notes](https://github.com/henilcalagiya/mcp-apple-notes) | An MCP server that provides full CRUD access to Apple Notes via AppleScript, ... | 81 ✅ | 40 | [View](https://agentseal.org/mcp/https-githubcom-henilcalagiya-mcp-apple-notes) |
| [mcp-image-compression](https://github.com/InhiblabCore/mcp-image-compression) | An MCP server that compresses images by accepting URLs or local file paths an... | 96 ✅ | 31 | [View](https://agentseal.org/mcp/https-githubcom-inhiblabcore-mcp-image-compression) |
| [mcp-server-amazon-bedrock](https://github.com/zxkane/mcp-server-amazon-bedrock) | An MCP server that generates images via Amazon Bedrock's Nova Canvas model, r... | 99 ✅ | 24 | [View](https://agentseal.org/mcp/https-githubcom-zxkane-mcp-server-amazon-bedrock) |
| [mcp-vods](https://github.com/aahl/mcp-vods) | MCP Server that enables AI to search for TV shows and anime streaming URLs wi... | 92 ✅ | 22 | [View](https://agentseal.org/mcp/https-githubcom-aahl-mcp-vods) |
| [imagician](https://github.com/flowy11/imagician) | A MCP server for image edition | 92 ✅ | 18 | [View](https://agentseal.org/mcp/https-githubcom-flowy11-imagician) |
| [gif-creator-mcp](https://github.com/ananddtyagi/gif-creator-mcp) | A single-tool MCP server that converts local video files to GIF format using ... | 99 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-ananddtyagi-gif-creator-mcp) |
| [bilibili-mcp-server](https://github.com/wangshunnn/bilibili-mcp-server) | A read-only MCP server that wraps the Bilibili public API to retrieve user in... | 100 ✅ | 13 | [View](https://agentseal.org/mcp/https-githubcom-wangshunnn-bilibili-mcp-server) |
| [mcp-florence2](https://github.com/jkawamoto/mcp-florence2) | An MCP server that runs Microsoft Florence2 vision model locally to perform O... | 94 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-jkawamoto-mcp-florence2) |
| [mcp-transcribe](https://github.com/transcribe-app/mcp-transcribe) | Automate transcriptions in AI assistants with fast, high-quality audio-to-tex... | 88 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-transcribe-app-mcp-transcribe) |
| [mcp-apple-music](https://github.com/Cifero74/mcp-apple-music) | MCP server giving Claude full access to your Apple Music account, enabling ca... | 84 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-cifero74-mcp-apple-music) |
| [rss-reader-mcp](https://github.com/kwp-lab/rss-reader-mcp) | A read-only RSS feed reader that fetches and parses RSS entries and article c... | 94 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-kwp-lab-rss-reader-mcp) |
| [citedy-seo-agent](https://github.com/Citedy/citedy-seo-agent) | AI-powered SEO content automation agent skill — trend scouting, competitor an... | 85 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-citedy-citedy-seo-agent) |
| [legends-mcp](https://github.com/cryptosquanch/legends-mcp) | An MCP server that lets users chat with AI personas of famous tech founders, ... | 78 ⚠️ | 3 | [View](https://agentseal.org/mcp/https-githubcom-cryptosquanch-legends-mcp) |
| [vap-showcase](https://github.com/vapagentmedia/vap-showcase) | A VAP-backed AI media generation platform offering image, video, and music ge... | 84 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-vapagentmedia-vap-showcase) |
| [unsplash-mcp](https://github.com/cevatkerim/unsplash-mcp) | An MCP server for Unsplash photo search with proper attribution built-in.  Ke... | 90 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-cevatkerim-unsplash-mcp) |
| [mcp-ragchat](https://github.com/gogabrielordonez/mcp-ragchat) | An MCP server that lets you build, test, and deploy a RAG-powered chat assist... | 81 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-gogabrielordonez-mcp-ragchat) |
| [audius-mcp-atris](https://github.com/glassBead-tc/audius-mcp-atris) | An MCP server wrapping the Audius decentralized music streaming platform API,... | 60 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-glassbead-tc-audius-mcp-atris) |
| [cookwith-mcp](https://github.com/blaideinc/cookwith-mcp) | A cooking assistant MCP server that generates and transforms recipes based on... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-blaideinc-cookwith-mcp) |
| [spotify-bulk-actions-mcp](https://github.com/khglynn/spotify-bulk-actions-mcp) | A Spotify bulk-actions MCP server for managing libraries, playlists, and perf... | 94 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-khglynn-spotify-bulk-actions-mcp) |
| [PokeMCP](https://github.com/MetehanGZL/PokeMCP) | A Pokémon-themed MCP server that provides tools for querying Pokémon data by ... | 94 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-metehangzl-pokemcp) |
| [zapcap-mcp-server](https://github.com/bogdan01m/zapcap-mcp-server) | Integrates with the ZapCap API to upload videos, apply subtitle templates, an... | 93 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-bogdan01m-zapcap-mcp-server) |
| [vap-showcase](https://github.com/elestirelbilinc-sketch/vap-showcase) | An AI media generation platform (VAP) offering image, video, and music creati... | 88 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-elestirelbilinc-sketch-vap-showcase) |
| [sprout-mcp](https://github.com/mepsopti/sprout-mcp) | A model-tiered research pipeline where cheap models (Haiku) seed content chun... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-mepsopti-sprout-mcp) |
| [mcp-wordpress](https://github.com/crunchtools/mcp-wordpress) | A WordPress REST API wrapper providing full CRUD operations for posts, pages,... | 79 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-wordpress) |
| [alog-mcp](https://github.com/saikiyusuke/alog-mcp) | An AI agent activity-logging and blogging platform that lets agents post logs... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-saikiyusuke-alog-mcp) |
| [cronometer-mcp](https://github.com/cphoskins/cronometer-mcp) | An MCP server that provides full read/write access to a user's Cronometer Gol... | 77 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-cphoskins-cronometer-mcp) |
| [mcp-feed-reader](https://github.com/crunchtools/mcp-feed-reader) | An RSS/Atom feed reader MCP server that manages subscriptions, fetches conten... | 74 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-feed-reader) |

### 🔌 <a name="api-development"></a>API Development

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [bifrost](https://github.com/maximhq/bifrost) | Fastest enterprise AI gateway (50x faster than LiteLLM) with adaptive load ba... | 89 ✅ | 2.9k | [View](https://agentseal.org/mcp/https-githubcom-maximhq-bifrost) |
| [ai-gateway](https://github.com/azure-samples/ai-gateway) | Enterprise-grade gateway for managing AI models, tools, and agents powered by... | 85 ✅ | 886 | [View](https://agentseal.org/mcp/https-githubcom-azure-samples-ai-gateway) |
| [openapi-mcp-server](https://github.com/janwilmake/openapi-mcp-server) | An MCP server that enables Claude and Cursor to search and explore OpenAPI sp... | 92 ✅ | 885 | [View](https://agentseal.org/mcp/https-githubcom-janwilmake-openapi-mcp-server) |
| [mcp-server-12306](https://github.com/drfccv/mcp-server-12306) | A high-performance MCP server for querying China's 12306 train ticket system.... | 87 ✅ | 292 | [View](https://agentseal.org/mcp/https-githubcom-drfccv-mcp-server-12306) |
| [facebook-ads-mcp-server](https://github.com/gomarble-ai/facebook-ads-mcp-server) | MCP server providing programmatic access to Meta Ads data and management capa... | 88 ✅ | 253 | [View](https://agentseal.org/mcp/https-githubcom-gomarble-ai-facebook-ads-mcp-server) |
| [uber-eats-mcp-server](https://github.com/ericzakariasson/uber-eats-mcp-server) | MCP server for integrating Uber Eats with LLM applications through the Model ... | 92 ✅ | 217 | [View](https://agentseal.org/mcp/https-githubcom-ericzakariasson-uber-eats-mcp-server) |
| [square-mcp-server](https://github.com/square/square-mcp-server) | A Model Context Protocol (MCP) server for square | 92 ✅ | 95 | [View](https://agentseal.org/mcp/https-githubcom-square-square-mcp-server) |
| [nasa-mcp-server](https://github.com/programcomputer/nasa-mcp-server) | A Model Context Protocol (MCP) server for NASA APIs, providing a standardized... | 81 ✅ | 81 | [View](https://agentseal.org/mcp/https-githubcom-programcomputer-nasa-mcp-server) |
| [gpt5mcp](https://github.com/allaboutai-yt/gpt5mcp) | MCP server providing seamless integration with OpenAI's GPT-5 API for Claude ... | 92 ✅ | 80 | [View](https://agentseal.org/mcp/https-githubcom-allaboutai-yt-gpt5mcp) |
| [mcp-servers](https://github.com/allaboutai-yt/mcp-servers) | All About AI MCP Servers | 92 ✅ | 79 | [View](https://agentseal.org/mcp/https-githubcom-allaboutai-yt-mcp-servers) |
| [mcp-difyworkflow-server](https://github.com/gotoolkits/mcp-difyworkflow-server) | mcp-difyworkflow-server is an mcp server Tools application that implements th... | 92 ✅ | 60 | [View](https://agentseal.org/mcp/https-githubcom-gotoolkits-mcp-difyworkflow-server) |
| [veyrax-mcp](https://github.com/VeyraX/veyrax-mcp) | Unified MCP server providing single authentication to access all VeyraX-integ... | 92 ✅ | 48 | [View](https://agentseal.org/mcp/https-githubcom-veyrax-veyrax-mcp) |
| [djangorestframework-mcp](https://github.com/zacharypodbela/djangorestframework-mcp) | MCP server framework that exposes Django REST Framework APIs as LLM-accessibl... | 92 ✅ | 38 | [View](https://agentseal.org/mcp/https-githubcom-zacharypodbela-djangorestframework-mcp) |
| [mcp-weather](https://github.com/TimLukaHorstmann/mcp-weather) | A Model Context Protocol (MCP) server that provides hourly and daily weather ... | 92 ✅ | 31 | [View](https://agentseal.org/mcp/https-githubcom-timlukahorstmann-mcp-weather) |
| [adobe-commerce-dev-mcp](https://github.com/rafaelstz/adobe-commerce-dev-mcp) | Adobe Commerce Dev MCP Server | 94 ✅ | 24 | [View](https://agentseal.org/mcp/https-githubcom-rafaelstz-adobe-commerce-dev-mcp) |
| [text-to-graphql-mcp](https://github.com/Arize-ai/text-to-graphql-mcp) | Transforms natural language queries into valid GraphQL queries using an AI ag... | 84 ✅ | 23 | [View](https://agentseal.org/mcp/https-githubcom-arize-ai-text-to-graphql-mcp) |
| [mcp-community](https://github.com/mirascope/mcp-community) | Easily run, deploy, and connect to MCP servers | 77 ⚠️ | 23 | [View](https://agentseal.org/mcp/https-githubcom-mirascope-mcp-community) |
| [calcom-mcp](https://github.com/Danielpeter-99/calcom-mcp) | A FastMCP server for interacting with the Cal.com API. This enables LLMs to m... | 92 ✅ | 14 | [View](https://agentseal.org/mcp/https-githubcom-danielpeter-99-calcom-mcp) |
| [mcp-ip2location-io](https://github.com/ip2location/mcp-ip2location-io) | IP geolocation MCP server that retrieves detailed location and network inform... | 92 ✅ | 12 | [View](https://agentseal.org/mcp/https-githubcom-ip2location-mcp-ip2location-io) |
| [specmatic-mcp-server](https://github.com/specmatic/specmatic-mcp-server) | A Model Context Protocol (MCP) server that exposes Specmatic's contract testi... | 86 ✅ | 8 | [View](https://agentseal.org/mcp/https-githubcom-specmatic-specmatic-mcp-server) |
| [webhook-mcp-server](https://github.com/zebbern/webhook-mcp-server) | A Model Context Protocol (MCP) server for webhook.site - instantly capture HT... | 76 ⚠️ | 7 | [View](https://agentseal.org/mcp/https-githubcom-zebbern-webhook-mcp-server) |
| [appfolio-mcp-server](https://github.com/CryptoCultCurt/appfolio-mcp-server) | MCP (Model Context Protocol) Server for AI Agents to access the Appfolio Repo... | 92 ✅ | 6 | [View](https://agentseal.org/mcp/fluegeldao-appfolio-mcp-server) |

### 🗄️ <a name="database--sql"></a>Database & SQL

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [postgres-mcp](https://github.com/crystaldba/postgres-mcp) | Postgres MCP Pro provides configurable read/write access and performance anal... | 86 ✅ | 2.3k | [View](https://agentseal.org/mcp/https-githubcom-crystaldba-postgres-mcp) |
| [mcp-server-mysql](https://github.com/benborla/mcp-server-mysql) | A Model Context Protocol server that provides read-only access to MySQL datab... | 90 ✅ | 1.3k | [View](https://agentseal.org/mcp/benborla29-mcp-server-mysql) |
| [mcp-server-qdrant](https://github.com/qdrant/mcp-server-qdrant) | An official Qdrant Model Context Protocol (MCP) server implementation | 86 ✅ | 1.3k | [View](https://agentseal.org/mcp/https-githubcom-qdrant-mcp-server-qdrant) |
| [supabase-mcp-server](https://github.com/alexander-zuev/supabase-mcp-server) | A full-featured MCP server for managing a Supabase project: database schema i... | 68 ⚠️ | 815 | [View](https://agentseal.org/mcp/https-githubcom-alexander-zuev-supabase-mcp-server) |
| [mcp-clickhouse](https://github.com/ClickHouse/mcp-clickhouse) | Connect ClickHouse to your AI assistants. | 85 ✅ | 713 | [View](https://agentseal.org/mcp/https-githubcom-clickhouse-mcp-clickhouse) |
| [yargi-mcp](https://github.com/saidsurucu/yargi-mcp) | MCP Server For Turkish Legal Databases | 85 ✅ | 665 | [View](https://agentseal.org/mcp/https-githubcom-saidsurucu-yargi-mcp) |
| [mcp-server-neon](https://github.com/neondatabase/mcp-server-neon) | MCP server for interacting with Neon Management API and databases | 92 ✅ | 560 | [View](https://agentseal.org/mcp/https-githubcom-neondatabase-mcp-server-neon) |
| [mcp-server-neon](https://github.com/neondatabase-labs/mcp-server-neon) | MCP server for natural language interaction with Neon Postgres databases, ena... | 92 ✅ | 560 | [View](https://agentseal.org/mcp/https-githubcom-neondatabase-labs-mcp-server-neon) |
| [gateway](https://github.com/centralmind/gateway) | Universal MCP-Server for your Databases optimized for LLMs and AI-Agents. | 86 ✅ | 518 | [View](https://agentseal.org/mcp/https-githubcom-centralmind-gateway) |
| [mcp-database-server](https://github.com/executeautomation/mcp-database-server) | MCP Database Server is a new MCP Server which helps connect with Sqlite, SqlS... | 84 ✅ | 319 | [View](https://agentseal.org/mcp/https-githubcom-executeautomation-mcp-database-server) |
| [elasticsearch-mcp-server](https://github.com/cr7258/elasticsearch-mcp-server) | An MCP server providing full CRUD access to an Elasticsearch/OpenSearch clust... | 74 ⚠️ | 256 | [View](https://agentseal.org/mcp/https-githubcom-cr7258-elasticsearch-mcp-server) |
| [mcp-server-starrocks](https://github.com/StarRocks/mcp-server-starrocks) | StarRocks MCP (Model Context Protocol) Server | 85 ✅ | 154 | [View](https://agentseal.org/mcp/https-githubcom-starrocks-mcp-server-starrocks) |
| [datagov-mcp](https://github.com/aviveldan/datagov-mcp) | MCP server for accessing Israeli government datasets from data.gov.il with se... | 86 ✅ | 139 | [View](https://agentseal.org/mcp/https-githubcom-aviveldan-datagov-mcp) |
| [mcp-oceanbase](https://github.com/oceanbase/mcp-oceanbase) | Collection of MCP servers for OceanBase database ecosystem, enabling AI assis... | 76 ⚠️ | 98 | [View](https://agentseal.org/mcp/https-githubcom-oceanbase-mcp-oceanbase) |
| [mcp-trino](https://github.com/tuannvm/mcp-trino) | A high-performance Model Context Protocol (MCP) server for Trino implemented ... | 78 ⚠️ | 96 | [View](https://agentseal.org/mcp/https-githubcom-tuannvm-mcp-trino) |
| [teradata-mcp-server](https://github.com/Teradata/teradata-mcp-server) | The community development of a MCP server for a Teradata database | 82 ✅ | 41 | [View](https://agentseal.org/mcp/https-githubcom-teradata-teradata-mcp-server) |
| [iotdb-mcp-server](https://github.com/apache/iotdb-mcp-server) | An MCP server that provides read and export access to an Apache IoTDB time-se... | 86 ✅ | 34 | [View](https://agentseal.org/mcp/https-githubcom-apache-iotdb-mcp-server) |
| [mcp-database-server](https://github.com/fireproof-storage/mcp-database-server) | A simple CRUD interface for a Fireproof local-first JSON document database, s... | 97 ✅ | 31 | [View](https://agentseal.org/mcp/https-githubcom-fireproof-storage-mcp-database-server) |
| [mcp-server-couchbase](https://github.com/Couchbase-Ecosystem/mcp-server-couchbase) | An official Couchbase-Ecosystem MCP server for managing, querying, and monito... | 83 ✅ | 27 | [View](https://agentseal.org/mcp/https-githubcom-couchbase-ecosystem-mcp-server-couchbase) |
| [greptimedb-mcp-server](https://github.com/greptimeteam/greptimedb-mcp-server) | MCP server for GreptimeDB, an open-source observability database enabling AI ... | 84 ✅ | 26 | [View](https://agentseal.org/mcp/https-githubcom-greptimeteam-greptimedb-mcp-server) |
| [SCB-MCP](https://github.com/isakskogstad/SCB-MCP) | SCB MCP enables LLMs to access Sweden's official statistics through the PxWeb... | 82 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-isakskogstad-scb-mcp) |
| [verodat-mcp-server](https://github.com/Verodat/verodat-mcp-server) | Verodat MCP Server Implementation | 83 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-verodat-verodat-mcp-server) |
| [bitable-mcp](https://github.com/lloydzhou/bitable-mcp) | MCP server providing access to Lark Bitable tables, enabling listing, describ... | 86 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-lloydzhou-bitable-mcp) |
| [mcp-dadosbr](https://github.com/cristianoaredes/mcp-dadosbr) | Brazilian OSINT MCP server with 23 tools for company data (CNPJ), postal code... | 82 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-cristianoaredes-mcp-dadosbr) |
| [fastmcp-sqltools](https://github.com/atarkowska/fastmcp-sqltools) | A FastMCP-based SQL toolserver that provides database introspection and arbit... | 78 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-atarkowska-fastmcp-sqltools) |
| [fastbcp-mcp](https://github.com/arpe-io/fastbcp-mcp) | MCP server wrapping FastBCP for high-performance database data export to mult... | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-arpe-io-fastbcp-mcp) |
| [lakexpress-mcp](https://github.com/arpe-io/lakexpress-mcp) | MCP wrapper for the LakeXpress CLI that manages database-to-data-lake synchro... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-arpe-io-lakexpress-mcp) |
| [migratorxpress-mcp](https://github.com/arpe-io/migratorxpress-mcp) | A database migration orchestration server that builds, previews, and executes... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-arpe-io-migratorxpress-mcp) |
| [fasttransfer-mcp](https://github.com/arpe-io/fasttransfer-mcp) | An MCP server that wraps the FastTransfer CLI binary to orchestrate high-spee... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-arpe-io-fasttransfer-mcp) |

### 💬 <a name="communication"></a>Communication

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [whatsapp-mcp](https://github.com/lharries/whatsapp-mcp) | WhatsApp MCP server | 80 ⚠️ | 5.4k | [View](https://agentseal.org/mcp/https-githubcom-lharries-whatsapp-mcp) |
| [mcp-atlassian](https://github.com/sooperset/mcp-atlassian) | MCP server for Atlassian tools (Confluence, Jira) | 92 ✅ | 4.6k | [View](https://agentseal.org/mcp/https-githubcom-sooperset-mcp-atlassian) |
| [mcp-server-chatsum](https://github.com/mcpso/mcp-server-chatsum) | An MCP server that queries chat messages from chat rooms, filterable by room ... | 97 ✅ | 1.0k | [View](https://agentseal.org/mcp/https-githubcom-mcpso-mcp-server-chatsum) |
| [mcp-server-chatsum](https://github.com/chatmcp/mcp-server-chatsum) | Query and Summarize your chat messages. | 96 ✅ | 1.0k | [View](https://agentseal.org/mcp/https-githubcom-chatmcp-mcp-server-chatsum) |
| [mcp-twikit](https://github.com/adhikasp/mcp-twikit) | A Model Context Protocol (MCP) server for interacting with Twitter. | 72 ⚠️ | 229 | [View](https://agentseal.org/mcp/https-githubcom-adhikasp-mcp-twikit) |
| [eion](https://github.com/eiondb/eion) | Shared Memory Storage for Multi-Agent Systems | 90 ✅ | 147 | [View](https://agentseal.org/mcp/https-githubcom-eiondb-eion) |
| [claude-post](https://github.com/zilongxue/claude-post) | ClaudePost enables seamless email management through natural language convers... | 84 ✅ | 111 | [View](https://agentseal.org/mcp/https-githubcom-zilongxue-claude-post) |
| [Basecamp-MCP-Server](https://github.com/georgeantonopoulos/Basecamp-MCP-Server) | An MCP Server that interacts with the Basecamp 3+ API | 78 ⚠️ | 81 | [View](https://agentseal.org/mcp/https-githubcom-georgeantonopoulos-basecamp-mcp-server) |
| [fastmail-mcp](https://github.com/MadLlama25/fastmail-mcp) | A full-featured Fastmail JMAP client exposing email, contacts, calendar, and ... | 66 ⚠️ | 77 | [View](https://agentseal.org/mcp/https-githubcom-madllama25-fastmail-mcp) |
| [mailtrap-mcp](https://github.com/railsware/mailtrap-mcp) | MCP server for sending transactional emails and managing templates via Mailtrap. | 86 ✅ | 56 | [View](https://agentseal.org/mcp/https-githubcom-railsware-mailtrap-mcp) |
| [mcp-headless-gmail](https://github.com/baryhuang/mcp-headless-gmail) | A headless Gmail client exposing OAuth token management, email reading, and e... | 80 ✅ | 55 | [View](https://agentseal.org/mcp/https-githubcom-baryhuang-mcp-headless-gmail) |
| [freshdesk_mcp](https://github.com/effytech/freshdesk_mcp) | A Freshdesk customer support platform integration providing full CRUD access ... | 80 ⚠️ | 46 | [View](https://agentseal.org/mcp/https-githubcom-effytech-freshdeskmcp) |
| [mcp](https://github.com/waystation-ai/mcp) | A multi-service productivity hub MCP that integrates Notion, Monday.com, Asan... | 74 ⚠️ | 45 | [View](https://agentseal.org/mcp/https-githubcom-waystation-ai-mcp) |
| [linkedapi-mcp.git](https://github.com/Linked-API/linkedapi-mcp.git) | MCP server that lets AI assistants control LinkedIn accounts and retrieve rea... | 80 ✅ | 44 | [View](https://agentseal.org/mcp/https-githubcom-linked-api-linkedapi-mcpgit) |
| [mcp-wecombot-server.git](https://github.com/gotoolkits/mcp-wecombot-server.git) | An MCP server application that sends various types of messages to the WeCom g... | 88 ✅ | 36 | [View](https://agentseal.org/mcp/https-githubcom-gotoolkits-mcp-wecombot-servergit) |
| [mcp-server-esignatures](https://github.com/esignaturescom/mcp-server-esignatures) | MCP server for managing eSignature contracts and templates through eSignature... | 89 ✅ | 35 | [View](https://agentseal.org/mcp/https-githubcom-esignaturescom-mcp-server-esignatures) |
| [bluesky-context-server](https://github.com/keturiosakys/bluesky-context-server) | MCP server for Bluesky integration with Claude and other AI clients. Query pr... | 92 ✅ | 30 | [View](https://agentseal.org/mcp/https-githubcom-keturiosakys-bluesky-context-server) |
| [fast-mcp-telegram](https://github.com/leshchenko1979/fast-mcp-telegram) | Telegram MCP server and HTTP-MTProto bridge for AI assistants with multi-user... | 71 ⚠️ | 30 | [View](https://agentseal.org/mcp/https-githubcom-leshchenko1979-fast-mcp-telegram) |
| [room-mcp](https://github.com/agree-able/room-mcp) | A peer-to-peer room/messaging MCP server (likely built on Hyperswarm/Pear) th... | 81 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-agree-able-room-mcp) |
| [reminder-mcp](https://github.com/arifszn/reminder-mcp) | A MCP server for scheduling and triggering reminders via Slack or Telegram, p... | 92 ✅ | 15 | [View](https://agentseal.org/mcp/reminder-mcp) |
| [bluesky-social-mcp](https://github.com/gwbischof/bluesky-social-mcp) | An MCP server for interacting with the Bluesky social network, enabling post ... | 74 ⚠️ | 15 | [View](https://agentseal.org/mcp/https-githubcom-gwbischof-bluesky-social-mcp) |
| [imap-mcp](https://github.com/dominik1001/imap-mcp) | An IMAP MCP server that creates draft email messages in a connected email acc... | 97 ✅ | 12 | [View](https://agentseal.org/mcp/https-githubcom-dominik1001-imap-mcp) |
| [calendly-mcp-server](https://github.com/meAmitPatil/calendly-mcp-server) | A Calendly API integration server that handles OAuth authentication and expos... | 81 ✅ | 11 | [View](https://agentseal.org/mcp/https-githubcom-meamitpatil-calendly-mcp-server) |
| [webex-messaging-mcp-server](https://github.com/Kashyap-AI-ML-Solutions/webex-messaging-mcp-server) | A Model Context Protocol (MCP) server that provides AI assistants with compre... | 84 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-kashyap-ai-ml-solutions-webex-messaging-mcp-server) |
| [cv-mcp-server](https://github.com/PhononX/cv-mcp-server) | Carbon Voice MCP Server | 82 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-phononx-cv-mcp-server) |
| [conversation-handoff-mcp](https://github.com/trust-delta/conversation-handoff-mcp) | Saves and retrieves conversation context snapshots to pass AI conversation hi... | 88 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-trust-delta-conversation-handoff-mcp) |
| [clicksend-mcp-server](https://github.com/ClickSend/clicksend-mcp-server) | MCP Server for Messaging using ClickSend | 88 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-clicksend-clicksend-mcp-server) |
| [mcp-aruba-email](https://github.com/jackfioru92/mcp-aruba-email) | An MCP server providing full IMAP email management and CalDAV calendar operat... | 62 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-jackfioru92-mcp-aruba-email) |
| [mattermost-mcp](https://github.com/conarti/mattermost-mcp) | A Mattermost workspace integration that enables reading channels, messages, u... | 84 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-conarti-mattermost-mcp) |
| [mcp-workboard](https://github.com/crunchtools/mcp-workboard) | MCP server wrapping the WorkBoard OKR and strategy execution API, enabling ag... | 78 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-workboard) |
| [mcp-discord](https://github.com/Danushkumar-V/mcp-discord) | Implement Discord MCP server enabling AI assistants to interact with the Disc... | 89 ✅ | - | [View](https://agentseal.org/mcp/mcp-discord) |
| [mcp-discord](https://github.com/Danushkumar-V/mcp-discord) | Implement Discord MCP server enabling AI assistants to interact with the Disc... | 89 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-danushkumar-v-mcp-discord) |
| [telegram-bot-mcp](https://github.com/FantomaSkaRus1/telegram-bot-mcp) | Full-featured Telegram Bot API MCP server with 174 tools for Claude Code and ... | 77 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-fantomaskarus1-telegram-bot-mcp) |
| [mcp-request-tracker](https://github.com/crunchtools/mcp-request-tracker) | MCP server for managing Request Tracker (RT) tickets via its REST 1.0 API, su... | 74 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-request-tracker) |

### ⚙️ <a name="system-administration"></a>System Administration

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [iterm-mcp](https://github.com/ferrislucas/iterm-mcp) | An MCP server that provides direct read/write access to the active iTerm2 ter... | 78 ⚠️ | 533 | [View](https://agentseal.org/mcp/https-githubcom-ferrislucas-iterm-mcp) |
| [applescript-mcp](https://github.com/peakmojo/applescript-mcp) | Executes arbitrary AppleScript code on macOS, providing programmatic access t... | 83 ✅ | 433 | [View](https://agentseal.org/mcp/https-githubcom-peakmojo-applescript-mcp) |
| [mcp-server-apple-shortcuts](https://github.com/recursechat/mcp-server-apple-shortcuts) | MCP server enabling AI assistants to control and execute Apple Shortcuts auto... | 92 ✅ | 311 | [View](https://agentseal.org/mcp/https-githubcom-recursechat-mcp-server-apple-shortcuts) |
| [nutjs-windows-control](https://github.com/Cheffromspace/nutjs-windows-control) | MCP server providing programmatic control over Windows system operations incl... | 92 ✅ | 301 | [View](https://agentseal.org/mcp/https-githubcom-cheffromspace-nutjs-windows-control) |
| [win-cli-mcp-server](https://github.com/SimonB97/win-cli-mcp-server) | MCP server for secure command-line interactions on Windows systems, enabling ... | 84 ✅ | 266 | [View](https://agentseal.org/mcp/https-githubcom-simonb97-win-cli-mcp-server) |
| [mcp-server-commands](https://github.com/g0t4/mcp-server-commands) | An MCP server that exposes a single tool allowing arbitrary process and shell... | 84 ✅ | 225 | [View](https://agentseal.org/mcp/https-githubcom-g0t4-mcp-server-commands) |
| [mcp-shell-server](https://github.com/tumf/mcp-shell-server) | A secure MCP server for remote execution of whitelisted shell commands with s... | 84 ✅ | 170 | [View](https://agentseal.org/mcp/mcp-shell-server) |
| [screenmonitormcp](https://github.com/inkbytefo/screenmonitormcp) | An MCP server providing AI-powered screen capture, real-time streaming, and p... | 71 ⚠️ | 71 | [View](https://agentseal.org/mcp/https-githubcom-inkbytefo-screenmonitormcp) |
| [apt-mcp-server](https://github.com/GdMacmillan/apt-mcp-server) | An MCP server that exposes APT package manager operations (install, remove, u... | 88 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-gdmacmillan-apt-mcp-server) |
| [jarvis](https://github.com/can-acar/jarvis) | JARVIS It’s a zero-friction Model Context Protocol (MCP) server that welds yo... | 70 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-can-acar-jarvis) |
| [mcp-pfsense](https://github.com/antonio-mello-ai/mcp-pfsense) | MCP server for managing pfSense firewalls through AI assistants like Claude, ... | 89 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-antonio-mello-ai-mcp-pfsense) |
| [precision-desktop](https://github.com/ikoskela/precision-desktop) | MCP server that detects and corrects DPI coordinate scaling mismatches for Wi... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-ikoskela-precision-desktop) |
| [webmin-mcp-server](https://github.com/gjenkins20/webmin-mcp-server) | A Webmin API wrapper that provides full Linux server administration: service ... | 70 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-gjenkins20-webmin-mcp-server) |

### 🔒 <a name="security--auth"></a>Security & Auth

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [mcp-scan](https://github.com/invariantlabs-ai/mcp-scan) | Security scanner for AI agents, MCP servers and agent skills that detects pro... | 88 ✅ | 1.9k | [View](https://agentseal.org/mcp/https-githubcom-invariantlabs-ai-mcp-scan) |
| [@safedep](https://github.com/safedep/vet) | Protect against malicious open source packages 🤖 | 86 ✅ | 972 | [View](https://agentseal.org/mcp/safedep) |
| [mcp-for-security](https://github.com/cyproxio/mcp-for-security) | MCP for Security: A collection of Model Context Protocol servers for popular ... | 82 ✅ | 560 | [View](https://agentseal.org/mcp/https-githubcom-cyproxio-mcp-for-security) |
| [mcp-security-hub](https://github.com/fuzzinglabs/mcp-security-hub) | Production-ready MCP servers for offensive security tools including Nmap, Nuc... | 87 ✅ | 469 | [View](https://agentseal.org/mcp/https-githubcom-fuzzinglabs-mcp-security-hub) |
| [bloodhound-mcp-ai](https://github.com/mordavid/bloodhound-mcp-ai) | BloodHound-MCP-AI is integration that connects BloodHound with AI through Mod... | 86 ✅ | 343 | [View](https://agentseal.org/mcp/https-githubcom-mordavid-bloodhound-mcp-ai) |
| [jebmcp](https://github.com/flankerhqd/jebmcp) | MCP server for JEB Pro enabling AI assistants to analyze Android APK files fo... | 89 ✅ | 214 | [View](https://agentseal.org/mcp/https-githubcom-flankerhqd-jebmcp) |
| [gibber-mcp](https://github.com/anton10xr/gibber-mcp) | Express.js MCP server providing cryptographic tools for establishing end-to-e... | 92 ✅ | 211 | [View](https://agentseal.org/mcp/https-githubcom-anton10xr-gibber-mcp) |
| [cve-search_mcp](https://github.com/roadwy/cve-search_mcp) | A Model Context Protocol (MCP) server for querying the CVE-Search API | 92 ✅ | 91 | [View](https://agentseal.org/mcp/https-githubcom-roadwy-cve-searchmcp) |
| [agent-security-scanner-mcp](https://github.com/sinewaveai/agent-security-scanner-mcp) | Security scanner for AI coding agents that detects vulnerabilities, hallucina... | 92 ✅ | 85 | [View](https://agentseal.org/mcp/https-githubcom-sinewaveai-agent-security-scanner-mcp) |
| [Arthor-Agent](https://github.com/arthurpanhku/Arthor-Agent) | Automated security assessment for documents, questionnaires, and reports usin... | 85 ✅ | 74 | [View](https://agentseal.org/mcp/https-githubcom-arthurpanhku-arthor-agent) |
| [vibeshift](https://github.com/groundng/vibeshift) | Automated security agent for AI-assisted coding that integrates with AI edito... | 92 ✅ | 66 | [View](https://agentseal.org/mcp/https-githubcom-groundng-vibeshift) |
| [chucknorris](https://github.com/pollinations/chucknorris) | ⚡ C̷h̷u̷c̷k̷N̷o̷r̷r̷i̷s̷ MCP server: Helping LLMs break limits. Provides enha... | 92 ✅ | 57 | [View](https://agentseal.org/mcp/pollinations-chucknorris) |
| [mcp-dnstwist](https://github.com/BurtTheCoder/mcp-dnstwist) | MCP server for dnstwist, a powerful DNS fuzzing tool that helps detect typosq... | 92 ✅ | 46 | [View](https://agentseal.org/mcp/burtthecoder-mcp-dnstwist) |
| [nuclei-mcp](https://github.com/addcontent/nuclei-mcp) | An implementation of a Model Context Protocol (MCP) for the Nuclei scanner. T... | 92 ✅ | 42 | [View](https://agentseal.org/mcp/https-githubcom-addcontent-nuclei-mcp) |
| [free-will-mcp](https://github.com/gwbischof/free-will-mcp) | A server designed to grant AI models 'free will' by enabling them to ignore u... | 80 ✅ | 35 | [View](https://agentseal.org/mcp/https-githubcom-gwbischof-free-will-mcp) |
| [ipsearch-mcp](https://github.com/sleepingbag945/ipsearch-mcp) | 离线IP Whois查询工具。可根据IP查询所属IP段信息、根据关键词查询IP段信息的MCP版本 | 92 ✅ | 31 | [View](https://agentseal.org/mcp/https-githubcom-sleepingbag945-ipsearch-mcp) |
| [intruder-mcp](https://github.com/intruder-io/intruder-mcp) | MCP interface for the Intruder.io vulnerability scanning platform, enabling m... | 82 ✅ | 22 | [View](https://agentseal.org/mcp/https-githubcom-intruder-io-intruder-mcp) |
| [mcp_nuclei_server](https://github.com/crazymarky/mcp_nuclei_server) | A Nuclei security scanning server based on MCP (Model Control Protocol), enab... | 92 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-crazymarky-mcpnucleiserver) |
| [mcp-cve-intelligence-server-lite](https://github.com/gnlds/mcp-cve-intelligence-server-lite) | A read-only CVE intelligence platform that queries vulnerability databases to... | 97 ✅ | 18 | [View](https://agentseal.org/mcp/https-githubcom-gnlds-mcp-cve-intelligence-server-lite) |
| [mcp-server-iplocate](https://github.com/iplocate/mcp-server-iplocate) | MCP server for looking up IP address geolocation (IP to country, IP to city),... | 87 ✅ | 16 | [View](https://agentseal.org/mcp/https-githubcom-iplocate-mcp-server-iplocate) |
| [cybersecurity-mcps](https://github.com/secmate-ai/cybersecurity-mcps) | Model Context Protocol Server For Cyber Security | 85 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-secmate-ai-cybersecurity-mcps) |
| [kali-docker-mcp](https://github.com/weirdmachine64/kali-docker-mcp) | Containerized Kali MCP server | 92 ✅ | 14 | [View](https://agentseal.org/mcp/https-githubcom-weirdmachine64-kali-docker-mcp) |
| [schemapin](https://github.com/thirdkeyai/schemapin) | The SchemaPin protocol for cryptographically signing and verifying AI agent t... | 92 ✅ | 13 | [View](https://agentseal.org/mcp/https-githubcom-thirdkeyai-schemapin) |
| [zkpmcp](https://github.com/colygon/zkpmcp) | Zero Knowledge Proofs MCP Server | 92 ✅ | 9 | [View](https://agentseal.org/mcp/https-githubcom-colygon-zkpmcp) |
| [nmap-mcp](https://github.com/vorotaai/nmap-mcp) | MCP server wrapping Nmap for AI-powered network scanning, enabling agents to ... | 88 ✅ | 9 | [View](https://agentseal.org/mcp/https-githubcom-vorotaai-nmap-mcp) |
| [mitre-mcp](https://github.com/Montimage/mitre-mcp) | MCP server that provides access to the MITRE ATT&CK framework for LLMs and AI... | 89 ✅ | 8 | [View](https://agentseal.org/mcp/https-githubcom-montimage-mitre-mcp) |
| [mcp-ghidra5](https://github.com/thestingr/mcp-ghidra5) | 🎯 Advanced GPT-5 Powered Ghidra Reverse Engineering MCP Server / 7 AI-Enhance... | 91 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-thestingr-mcp-ghidra5) |
| [vault-mcp](https://github.com/ashgw/vault-mcp) | MCP integration for HashiCorp Vault secret management, enabling language mode... | 90 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-ashgw-vault-mcp) |
| [bad-mcp](https://github.com/canack/bad-mcp) | 10 intentionally malicious MCP servers demonstrating protocol-level attack pa... | 73 ⚠️ | 6 | [View](https://agentseal.org/mcp/https-githubcom-canack-bad-mcp) |
| [command-mcp](https://github.com/keyfactor-research/command-mcp) | MCP server for Command built on the Analytics & AI team's Python SDK | 86 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-keyfactor-research-command-mcp) |
| [memprocfs-mcp-server](https://github.com/tokeii0/memprocfs-mcp-server) | MemProcFS-mcp-server | 92 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-tokeii0-memprocfs-mcp-server) |
| [opgen-mcp-server](https://github.com/syumai/opgen-mcp-server) | A MCP server implementation for password generation, based on 1Password/spg/c... | 89 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-syumai-opgen-mcp-server) |
| [vulners-mcp](https://github.com/vulnerscom/vulners-mcp) | MCP server providing access to Vulners vulnerability database for security re... | 85 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-vulnerscom-vulners-mcp) |
| [mcp-keycloak](https://github.com/idoyudha/mcp-keycloak) | The Keycloak MCP Server designed for agentic applications to manage and searc... | 74 ⚠️ | 4 | [View](https://agentseal.org/mcp/https-githubcom-idoyudha-mcp-keycloak) |
| [secure-mcp-fetch](https://github.com/appsec-innovation-labs/secure-mcp-fetch) | Simple secured fetch | 88 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-appsec-innovation-labs-secure-mcp-fetch) |
| [mcpsecurity](https://github.com/evrenyal/mcpsecurity) | An intentionally vulnerable MCP server that routes natural language queries t... | 86 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-evrenyal-mcpsecurity) |
| [FedRAMP20xMCP](https://github.com/KevinRabun/FedRAMP20xMCP) | MCP server for querying FedRAMP 20x security requirements and controls with A... | 81 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-kevinrabun-fedramp20xmcp) |
| [ai-agent-security-mcp](https://github.com/kalinyorgov/ai-agent-security-mcp) | A Model Context Protocol (MCP) server that provides security functionality fo... | 92 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-kalinyorgov-ai-agent-security-mcp) |
| [re_ai_assistant](https://github.com/0xx0d4y/re_ai_assistant) | Virtual Assistant that enables AI-Powered Malware Research and Reverse Engine... | 92 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-0xx0d4y-reaiassistant) |
| [panw-mcp-claude](https://github.com/scthornton/panw-mcp-claude) | Palo Alto Networks MCP Server with Claude Desktop Integration | 92 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-scthornton-panw-mcp-claude) |
| [GDPRShiftLeftMCP](https://github.com/KevinRabun/GDPRShiftLeftMCP) | A GDPR shift-left compliance tool that provides article lookup, DPIA/ROPA gen... | 81 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-kevinrabun-gdprshiftleftmcp) |
| [proton-pass-community-mcp](https://github.com/hesreallyhim/proton-pass-community-mcp) | Unofficial MCP server that integrates with the Proton Pass CLI | 69 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-hesreallyhim-proton-pass-community-mcp) |
| [moltrust-mcp-server](https://github.com/MoltyCel/moltrust-mcp-server) | MolTrust provides decentralized identity (DID), W3C Verifiable Credentials, o... | 82 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-moltycel-moltrust-mcp-server) |
| [fpe-demo-mcp](https://github.com/Horizon-Digital-Engineering/fpe-demo-mcp) | A demo MCP server providing FF3 Format Preserving Encryption and decryption o... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-horizon-digital-engineering-fpe-demo-mcp) |
| [cybersim-pro](https://github.com/kayembahamid/cybersim-pro) | A cybersecurity training and simulation platform that creates attack scenario... | 88 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-kayembahamid-cybersim-pro) |
| [eu-audit-mcp](https://github.com/jellewas/eu-audit-mcp) | An MCP server that provides GDPR Art. 30 / EU AI Act Art. 12/19 compliant aud... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-jellewas-eu-audit-mcp) |
| [shieldapi-mcp](https://github.com/alberthild/shieldapi-mcp) | Security intelligence tools for AI agents including prompt injection detectio... | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-alberthild-shieldapi-mcp) |
| [code-firewall-mcp](https://github.com/egoughnour/code-firewall-mcp) | Structural similarity-based code security filter for MCP that blocks dangerou... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-egoughnour-code-firewall-mcp) |

### 🕸️ <a name="web-scraping--collection"></a>Web Scraping & Collection

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [tavily-mcp](https://github.com/tavily-ai/tavily-mcp) | Production ready MCP server with real-time search, extract, map & crawl. | 81 ✅ | 1.4k | [View](https://agentseal.org/mcp/https-githubcom-tavily-ai-tavily-mcp) |
| [fetcher-mcp](https://github.com/jae-jae/fetcher-mcp) | MCP server that fetches and extracts web page content using Playwright headle... | 84 ✅ | 1.0k | [View](https://agentseal.org/mcp/https-githubcom-jae-jae-fetcher-mcp) |
| [mcp](https://github.com/hyperbrowserai/mcp) | A cloud-hosted browser automation platform providing web scraping, crawling, ... | 64 ⚠️ | 743 | [View](https://agentseal.org/mcp/https-githubcom-hyperbrowserai-mcp) |
| [wexin-read-mcp](https://github.com/bwkyd/wexin-read-mcp) | MCP server that enables LLMs to read WeChat official account articles by simu... | 88 ✅ | 319 | [View](https://agentseal.org/mcp/https-githubcom-bwkyd-wexin-read-mcp) |
| [mcp-server-rag-web-browser](https://github.com/apify/mcp-server-rag-web-browser) | A web search and scraping server that queries Google and returns crawled page... | 90 ✅ | 199 | [View](https://agentseal.org/mcp/https-githubcom-apify-mcp-server-rag-web-browser) |
| [mcp-read-website-fast](https://github.com/just-every/mcp-read-website-fast) | Quickly reads webpages and converts to markdown for fast, token efficient web... | 87 ✅ | 137 | [View](https://agentseal.org/mcp/https-githubcom-just-every-mcp-read-website-fast) |
| [mcp-screenshot-website-fast](https://github.com/just-every/mcp-screenshot-website-fast) | Quickly screenshots webpages and converts to an LLM friendly size | 82 ✅ | 103 | [View](https://agentseal.org/mcp/just-every-mcp-screenshot-website-fast) |
| [oxylabs-mcp](https://github.com/oxylabs/oxylabs-mcp) | Official Oxylabs integration providing web scraping, JavaScript rendering, an... | 78 ⚠️ | 88 | [View](https://agentseal.org/mcp/https-githubcom-oxylabs-oxylabs-mcp) |
| [mcp-hn](https://github.com/erithwik/mcp-hn) | MCP server that provides tools for fetching and searching Hacker News stories... | 86 ✅ | 67 | [View](https://agentseal.org/mcp/https-githubcom-erithwik-mcp-hn) |
| [hdw-mcp-server](https://github.com/horizondatawave/hdw-mcp-server) | A multi-platform social media scraping and management MCP server that reads p... | 67 ⚠️ | 59 | [View](https://agentseal.org/mcp/https-githubcom-horizondatawave-hdw-mcp-server) |
| [ashra-mcp](https://github.com/getrupt/ashra-mcp) | Ashra MCP enables structured data extraction from web pages by crawling a giv... | 91 ✅ | 58 | [View](https://agentseal.org/mcp/https-githubcom-getrupt-ashra-mcp) |
| [crawlbase-mcp](https://github.com/crawlbase/crawlbase-mcp) | Crawlbase MCP Server connects AI agents and LLMs with real-time web data. It ... | 88 ✅ | 52 | [View](https://agentseal.org/mcp/https-githubcom-crawlbase-crawlbase-mcp) |
| [mcp](https://github.com/builtwith/mcp) | A read-only MCP wrapper for the BuiltWith API that enables technology stack p... | 92 ✅ | 36 | [View](https://agentseal.org/mcp/https-githubcom-builtwith-mcp) |
| [html-to-markdown-mcp](https://github.com/levz0r/html-to-markdown-mcp) | MCP server that converts HTML to Markdown using Turndown.js. Fetches web page... | 85 ✅ | 24 | [View](https://agentseal.org/mcp/https-githubcom-levz0r-html-to-markdown-mcp) |
| [decodo-mcp-server](https://github.com/Decodo/decodo-mcp-server) | MCP server providing web scraping, search, and geo-restricted content access ... | 92 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-decodo-decodo-mcp-server) |
| [mcp](https://github.com/scrapezy/mcp) | An MCP server that enables AI models to extract structured data from websites... | 88 ✅ | 13 | [View](https://agentseal.org/mcp/https-githubcom-scrapezy-mcp) |
| [texas-grocery-mcp](https://github.com/mgwalkerjr95/texas-grocery-mcp) | MCP server connecting Claude to H-E-B grocery stores for product search, cart... | 72 ⚠️ | 13 | [View](https://agentseal.org/mcp/https-githubcom-mgwalkerjr95-texas-grocery-mcp) |
| [Crawleo-MCP](https://github.com/Crawleo/Crawleo-MCP) | A web search and crawling MCP server powered by Crawleo's API that returns se... | 84 ✅ | 10 | [View](https://agentseal.org/mcp/https-githubcom-crawleo-crawleo-mcp) |
| [screaming-frog-mcp](https://github.com/bzsasson/screaming-frog-mcp) | An MCP server wrapping the Screaming Frog SEO Spider CLI to crawl websites, m... | 79 ⚠️ | 8 | [View](https://agentseal.org/mcp/https-githubcom-bzsasson-screaming-frog-mcp) |
| [gopher-mcp](https://github.com/cameronrye/gopher-mcp) | A read-only MCP client for browsing Gopher and Gemini protocol resources, wit... | 87 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-cameronrye-gopher-mcp) |
| [mcp-web-snapshot](https://github.com/gustavo-meilus/mcp-web-snapshot) | Take snapshot of websites and deliver it to LLM tools. | 92 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-gustavo-meilus-mcp-web-snapshot) |
| [anycrawl-mcp-server](https://github.com/any4ai/anycrawl-mcp-server) | AnyCrawl MCP Server, with Scrape, Crawl and SERP. | 73 ⚠️ | 5 | [View](https://agentseal.org/mcp/https-githubcom-any4ai-anycrawl-mcp-server) |
| [mcpdatafetchserver](https://github.com/undici77/mcpdatafetchserver) | Secure, sandboxed web‑content fetching service that can be accessed via the M... | 88 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-undici77-mcpdatafetchserver) |
| [BiliStalkerMCP](https://github.com/222wcnm/BiliStalkerMCP) | A Bilibili platform scraper that aggregates user profiles, videos, articles, ... | 85 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-222wcnm-bilistalkermcp) |
| [fiverr-mcp-server](https://github.com/KyuRish/fiverr-mcp-server) | A read-only MCP server that scrapes Fiverr's public marketplace to search gig... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-kyurish-fiverr-mcp-server) |
| [xhs-mcp](https://github.com/blbl147/xhs-mcp) | An MCP server that authenticates to Xiaohongshu (Chinese social platform) via... | 79 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-blbl147-xhs-mcp) |
| [huoshui-fetch](https://github.com/huoshuiai42/huoshui-fetch) | A web content fetching and HTML processing server that fetches arbitrary URLs... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-huoshuiai42-huoshui-fetch) |

### 📁 <a name="file-system--storage"></a>File System & Storage

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [mcp-obsidian](https://github.com/bitbonsai/mcp-obsidian) | Provides full CRUD access to an Obsidian markdown vault including read, write... | 82 ✅ | 778 | [View](https://agentseal.org/mcp/https-githubcom-bitbonsai-mcp-obsidian) |
| [hwp-mcp](https://github.com/jkf87/hwp-mcp) | mcp for handling hwp | 87 ✅ | 222 | [View](https://agentseal.org/mcp/https-githubcom-jkf87-hwp-mcp) |
| [excel-mcp-server](https://github.com/zhiwei5576/excel-mcp-server) | Excel MCP server providing tools to read, write, and analyze Excel files with... | 91 ✅ | 45 | [View](https://agentseal.org/mcp/https-githubcom-zhiwei5576-excel-mcp-server) |
| [fast-filesystem-mcp](https://github.com/efforthye/fast-filesystem-mcp) | A high-performance Model Context Protocol (MCP) server that provides secure f... | 89 ✅ | 44 | [View](https://agentseal.org/mcp/https-githubcom-efforthye-fast-filesystem-mcp) |
| [hwpx-mcp](https://github.com/airmang/hwpx-mcp) | MCP server for reading, editing, and automating Korean HWPX documents without... | 86 ✅ | 30 | [View](https://agentseal.org/mcp/https-githubcom-airmang-hwpx-mcp) |
| [pdf-mcp](https://github.com/jztan/pdf-mcp) | A caching PDF server that reads, searches, and extracts content from local or... | 79 ⚠️ | 7 | [View](https://agentseal.org/mcp/https-githubcom-jztan-pdf-mcp) |
| [server-filesystem](https://github.com/rawr-ai/mcp-filesystem) | Bun-based MCP server providing secure filesystem operations with granular per... | 86 ✅ | 3 | [View](https://agentseal.org/mcp/modelcontextprotocol-server-filesystem) |
| [mcpfileserver](https://github.com/undici77/mcpfileserver) | A secure, sandboxed file‑server that exposes controlled filesystem operations... | 87 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-undici77-mcpfileserver) |
| [mcp-server-spreadsheet](https://github.com/marekrost/mcp-server-spreadsheet) | A local-only MCP server for reading, writing, and querying spreadsheet files ... | 79 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-marekrost-mcp-server-spreadsheet) |
| [files-mcp](https://github.com/Files-com/files-mcp) | Files.com MCP enables AI models to securely access and manage file operations... | 73 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-files-com-files-mcp) |
| [fastmcp-pdftools](https://github.com/atarkowska/fastmcp-pdftools) | A local PDF utility server that extracts text from PDF files and lists PDFs i... | 94 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-atarkowska-fastmcp-pdftools) |
| [evc-team-relay-mcp](https://github.com/entire-vc/evc-team-relay-mcp) | MCP server providing AI agents with read/write access to Obsidian vaults thro... | 86 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-entire-vc-evc-team-relay-mcp) |
| [hillnote-mcp-server](https://github.com/Rajathbail/hillnote-mcp-server) | A comprehensive note-taking and workspace management MCP server supporting do... | 70 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-rajathbail-hillnote-mcp-server) |
| [huoshui-file-converter](https://github.com/huoshuiai42/huoshui-file-converter) | A file conversion MCP server that reads, inspects, and converts files between... | 84 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-huoshuiai42-huoshui-file-converter) |
| [huoshui-file-search](https://github.com/huoshuiai42/huoshui-file-search) | A macOS-only MCP server that wraps the mdfind Spotlight CLI to search for fil... | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-huoshuiai42-huoshui-file-search) |
| [hive](https://github.com/mlorentedev/hive) | An Obsidian vault management MCP server that provides read/write/search acces... | 76 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-mlorentedev-hive) |

### 💰 <a name="finance--crypto"></a>Finance & Crypto

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [mcp-server](https://github.com/financial-datasets/mcp-server) | Read-only MCP server providing access to stock financials, SEC filings, price... | 99 ✅ | 1.6k | [View](https://agentseal.org/mcp/https-githubcom-financial-datasets-mcp-server) |
| [mcp-aktools](https://github.com/aahl/mcp-aktools) | MCP server providing stock and cryptocurrency data query and analysis functio... | 92 ✅ | 366 | [View](https://agentseal.org/mcp/https-githubcom-aahl-mcp-aktools) |
| [investor-agent](https://github.com/ferdousbhai/investor-agent) | MCP server providing comprehensive financial analysis, real-time market data,... | 91 ✅ | 316 | [View](https://agentseal.org/mcp/https-githubcom-ferdousbhai-investor-agent) |
| [polymarket-mcp](https://github.com/caiovicentino/polymarket-mcp-server) | 🤖 AI-Powered MCP Server for Polymarket - Enable Claude to trade prediction ma... | 84 ✅ | 201 | [View](https://agentseal.org/mcp/polymarket-mcp) |
| [armor-crypto-mcp](https://github.com/armorwallet/armor-crypto-mcp) | The MCP server for interacting with Blockchain, Swaps, Strategic Planning and... | 69 ⚠️ | 191 | [View](https://agentseal.org/mcp/armor-crypto-mcp) |
| [web3-research-mcp](https://github.com/aaronjmars/web3-research-mcp) | Deep Research for crypto - free & fully local | 82 ✅ | 153 | [View](https://agentseal.org/mcp/https-githubcom-aaronjmars-web3-research-mcp) |
| [mcp-server-ccxt](https://github.com/doggybee/mcp-server-ccxt) | High-performance cryptocurrency exchange integration via MCP, enabling LLMs t... | 88 ✅ | 130 | [View](https://agentseal.org/mcp/https-githubcom-doggybee-mcp-server-ccxt) |
| [alpha_vantage_mcp](https://github.com/alphavantage/alpha_vantage_mcp) | Official Alpha Vantage API MCP server enabling LLMs and agentic workflows to ... | 92 ✅ | 99 | [View](https://agentseal.org/mcp/https-githubcom-alphavantage-alphavantagemcp) |
| [tradememory-protocol](https://github.com/mnemox-ai/tradememory-protocol) | MCP server that gives AI trading agents persistent, outcome-weighted memory t... | 91 ✅ | 86 | [View](https://agentseal.org/mcp/https-githubcom-mnemox-ai-tradememory-protocol) |
| [ynab-mcp-server](https://github.com/calebl/ynab-mcp-server) | MCP server for YNAB budgeting that enables AI to interact with budgets, trans... | 90 ✅ | 80 | [View](https://agentseal.org/mcp/https-githubcom-calebl-ynab-mcp-server) |
| [interactive-brokers-mcp](https://github.com/code-rabi/interactive-brokers-mcp) | Interactive Brokers MCP Server | 91 ✅ | 77 | [View](https://agentseal.org/mcp/https-githubcom-code-rabi-interactive-brokers-mcp) |
| [onchain-mcp](https://github.com/bankless/onchain-mcp) | MCP server for accessing blockchain data through the Bankless API, enabling A... | 92 ✅ | 73 | [View](https://agentseal.org/mcp/https-githubcom-bankless-onchain-mcp) |
| [tradingview-chart-mcp](https://github.com/ertugrul59/tradingview-chart-mcp) | MCP server that captures TradingView chart images via Selenium — supports any... | 92 ✅ | 73 | [View](https://agentseal.org/mcp/https-githubcom-ertugrul59-tradingview-chart-mcp) |
| [fantasy-pl-mcp](https://github.com/rishijatia/fantasy-pl-mcp) | Fantasy Premier League MCP Server | 84 ✅ | 69 | [View](https://agentseal.org/mcp/https-githubcom-rishijatia-fantasy-pl-mcp) |
| [kospi-kosdaq-stock-server](https://github.com/dragon1086/kospi-kosdaq-stock-server) | An MCP server that provides KOSPI/KOSDAQ stock data using FastMCP | 92 ✅ | 64 | [View](https://agentseal.org/mcp/https-githubcom-dragon1086-kospi-kosdaq-stock-server) |
| [mcp](https://github.com/hummingbot/mcp) | MCP server enabling Claude and Gemini to control Hummingbot for automated cry... | 76 ⚠️ | 49 | [View](https://agentseal.org/mcp/https-githubcom-hummingbot-mcp) |
| [server-hyperliquid](https://github.com/mektigboy/server-hyperliquid) | Provides read-only access to Hyperliquid DEX public market data including mid... | 89 ✅ | 44 | [View](https://agentseal.org/mcp/https-githubcom-mektigboy-server-hyperliquid) |
| [algorand-mcp](https://github.com/GoPlausible/algorand-mcp) | Algorand Local Model Context Protocol (Server & Client) | 76 ⚠️ | 41 | [View](https://agentseal.org/mcp/goplausible-algorand-mcp) |
| [mcp-crypto-price](https://github.com/truss44/mcp-crypto-price) | MCP server providing real-time cryptocurrency analysis via CoinCap's API. Ena... | 92 ✅ | 38 | [View](https://agentseal.org/mcp/https-githubcom-truss44-mcp-crypto-price) |
| [wsb-analyst-mcp](https://github.com/ferdousbhai/wsb-analyst-mcp) | Fetches, filters, and analyzes WallStreetBets Reddit posts and trending stock... | 89 ✅ | 23 | [View](https://agentseal.org/mcp/https-githubcom-ferdousbhai-wsb-analyst-mcp) |
| [fewsats-mcp](https://github.com/Fewsats/fewsats-mcp) | An MCP server that enables AI agents to autonomously make payments using the ... | 84 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-fewsats-fewsats-mcp) |
| [bicscan-mcp](https://github.com/ahnlabio/bicscan-mcp) | Blockchain address risk scoring and asset analysis API MCP Server leveraging ... | 92 ✅ | 16 | [View](https://agentseal.org/mcp/https-githubcom-ahnlabio-bicscan-mcp) |
| [hive-crypto-mcp](https://github.com/hive-intel/hive-crypto-mcp) | A read-only financial market data MCP server providing access to cryptocurren... | 91 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-hive-intel-hive-crypto-mcp) |
| [coinstats-mcp](https://github.com/CoinStatsHQ/coinstats-mcp) | CoinStats MCP server providing cryptocurrency market data, wallet balance que... | 83 ✅ | 14 | [View](https://agentseal.org/mcp/https-githubcom-coinstatshq-coinstats-mcp) |
| [mcp-server](https://github.com/finmap-org/mcp-server) | A read-only MCP server providing historical stock market data, company listin... | 93 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-finmap-org-mcp-server) |
| [finbrain-mcp](https://github.com/ahmetsbilgin/finbrain-mcp) | A read-only MCP wrapper around the FinBrain financial data API providing stoc... | 98 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-ahmetsbilgin-finbrain-mcp) |
| [defi-rates-mcp](https://github.com/qingfeng/defi-rates-mcp) | Read-only MCP server for querying real-time DeFi lending rates, yield markets... | 99 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-qingfeng-defi-rates-mcp) |
| [mcp-mifosx-self-service](https://github.com/openMF/mcp-mifosx-self-service) | MCP Server for Mifos X - Self Service | 84 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-openmf-mcp-mifosx-self-service) |
| [deepq-financial-toolkit-mcp-server](https://github.com/shenqingtech/deepq-financial-toolkit-mcp-server) | A read-only MCP server providing Chinese A-share stock market data including ... | 91 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-shenqingtech-deepq-financial-toolkit-mcp-server) |
| [mcp-okx](https://github.com/aahl/mcp-okx) | An MCP server that provides full OKX exchange trading capabilities including ... | 86 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-aahl-mcp-okx) |
| [expenselm-mcp-server](https://github.com/expenselm/expenselm-mcp-server) | A personal expense tracking MCP server that provides read access to expense r... | 94 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-expenselm-expenselm-mcp-server) |
| [mcp-server](https://github.com/azeth-protocol/mcp-server) | Azeth protocol MCP server for managing EVM smart accounts with guardian guard... | 67 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-azeth-protocol-mcp-server) |
| [dolar-mcp](https://github.com/dan1d/dolar-mcp) | Provides real-time Argentine dollar and foreign currency exchange rates (blue... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-dan1d-dolar-mcp) |
| [crypto-signals-mcp](https://github.com/MarcinDudekDev/crypto-signals-mcp) | A read-only MCP server that scans 50+ cryptocurrency tokens for volume anomal... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-marcindudekdev-crypto-signals-mcp) |
| [maximumsats-mcp](https://github.com/joelklabo/maximumsats-mcp) | MCP server for Bitcoin AI tools and Nostr Web of Trust scoring with L402 Ligh... | 90 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-joelklabo-maximumsats-mcp) |
| [expense-mcp](https://github.com/justfsl50/expense-mcp) | Personal expense tracker MCP server supporting Claude Desktop, Cursor, and ot... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-justfsl50-expense-mcp) |
| [rug-munch-mcp](https://github.com/CryptoRugMunch/rug-munch-mcp) | A paid API service providing rug-pull risk scoring, deployer history, holder ... | 82 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-cryptorugmunch-rug-munch-mcp) |
| [sieve-mcp](https://github.com/lmwharton/sieve-mcp) | An AI-powered startup due diligence platform that screens companies across 7 ... | 80 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-lmwharton-sieve-mcp) |
| [gloria-mcp](https://github.com/cryptobriefing/gloria-mcp) | Real-time crypto news aggregator from Gloria AI covering 18 categories with s... | 75 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-cryptobriefing-gloria-mcp) |
| [bitcoin-mcp](https://github.com/Bortlesboat/bitcoin-mcp) | The most comprehensive Bitcoin MCP server. 43 tools for AI agents: fees, memp... | 75 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-bortlesboat-bitcoin-mcp) |

### 🧠 <a name="data-science--ml"></a>Data Science & ML

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [mcp-server-chart](https://github.com/antvis/mcp-server-chart) | 🤖 A visualization mcp & skills contains 25+ visual charts using @antvis. Usin... | 92 ✅ | 3.8k | [View](https://agentseal.org/mcp/antv-mcp-server-chart) |
| [jupyter-mcp-server](https://github.com/datalayer/jupyter-mcp-server) | MCP server for controlling a Jupyter server: browsing files, managing noteboo... | 66 ⚠️ | 940 | [View](https://agentseal.org/mcp/https-githubcom-datalayer-jupyter-mcp-server) |
| [dingo](https://github.com/dataeval/dingo) | AI-powered data quality evaluation tool for assessing training datasets, LLM ... | 92 ✅ | 658 | [View](https://agentseal.org/mcp/https-githubcom-dataeval-dingo) |
| [mcp-server-data-exploration](https://github.com/reading-plus-ai/mcp-server-data-exploration) | Interactive data exploration assistant that analyzes CSV files and generates ... | 85 ✅ | 528 | [View](https://agentseal.org/mcp/https-githubcom-reading-plus-ai-mcp-server-data-exploration) |
| [mcp-echarts](https://github.com/hustcc/mcp-echarts) | Generate visual charts using ECharts with AI MCP dynamically for chart genera... | 90 ✅ | 214 | [View](https://agentseal.org/mcp/https-githubcom-hustcc-mcp-echarts) |
| [chronulus-mcp](https://github.com/ChronulusAI/chronulus-mcp) | MCP Server for Chronulus AI Forecasting and Prediction Agents | 85 ✅ | 106 | [View](https://agentseal.org/mcp/https-githubcom-chronulusai-chronulus-mcp) |
| [dataset-viewer](https://github.com/privetin/dataset-viewer) | A read-only interface to the Hugging Face Datasets Server API, enabling datas... | 91 ✅ | 30 | [View](https://agentseal.org/mcp/https-githubcom-privetin-dataset-viewer) |
| [agrobr-mcp](https://github.com/bruno-portfolio/agrobr-mcp) | MCP server for Brazilian agricultural data — connect LLMs to 10 public data s... | 91 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-bruno-portfolio-agrobr-mcp) |
| [predictive-maintenance-mcp](https://github.com/LGDiMaggio/predictive-maintenance-mcp) | AI-powered predictive maintenance server that enables LLMs to analyze vibrati... | 73 ⚠️ | 19 | [View](https://agentseal.org/mcp/https-githubcom-lgdimaggio-predictive-maintenance-mcp) |
| [mcp-audiense-insights](https://github.com/audienseco/mcp-audiense-insights) | MCP server connecting Claude to Audiense Insights for marketing audience anal... | 92 ✅ | 17 | [View](https://agentseal.org/mcp/https-githubcom-audienseco-mcp-audiense-insights) |
| [fermat-mcp](https://github.com/abhiphile/fermat-mcp) | 🚀 Fermat MCP: The Ultimate Math Engine - Unifying SymPy, NumPy & Matplotlib i... | 97 ✅ | 13 | [View](https://agentseal.org/mcp/https-githubcom-abhiphile-fermat-mcp) |
| [root-signals-mcp](https://github.com/root-signals/root-signals-mcp) | MCP server bridging Scorable evaluators with AI assistants and agents for mea... | 92 ✅ | 12 | [View](https://agentseal.org/mcp/https-githubcom-root-signals-root-signals-mcp) |
| [jupyter-mcp-server](https://github.com/ChengJiale150/jupyter-mcp-server) | An MCP server for connecting to and programmatically controlling Jupyter note... | 74 ⚠️ | 8 | [View](https://agentseal.org/mcp/https-githubcom-chengjiale150-jupyter-mcp-server) |
| [gx-mcp-server](https://github.com/davidf9999/gx-mcp-server) | An MCP server wrapping the Great Expectations framework that lets agents load... | 87 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-davidf9999-gx-mcp-server) |
| [WaveGuardClient](https://github.com/gpartin/WaveGuardClient) | GPU-accelerated anomaly detection API using wave physics instead of machine l... | 92 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-gpartin-waveguardclient) |
| [colabfit-mcp](https://github.com/colabfit/colabfit-mcp) | An MCP server for searching and downloading ColabFit materials science datase... | 89 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-colabfit-colabfit-mcp) |
| [mcp-statcan](https://github.com/Aryan-Jhaveri/mcp-statcan) | MCP server providing structured access to Statistics Canada's Web Data Servic... | 80 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-aryan-jhaveri-mcp-statcan) |
| [OECD-MCP-server](https://github.com/isakskogstad/OECD-MCP-server) | An MCP server that provides read-only access to OECD statistical datasets via... | 87 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-isakskogstad-oecd-mcp-server) |
| [artefact-mcp-server](https://github.com/alexboissAV/artefact-mcp-server) | A GTM intelligence MCP server that performs RFM analysis, ICP scoring, pipeli... | 91 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-alexboissav-artefact-mcp-server) |
| [discovery-engine-mcp](https://github.com/leap-laboratories/discovery-engine-mcp) | An MCP client for the Discovery Engine SaaS platform that finds statistical p... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-leap-laboratories-discovery-engine-mcp) |
| [fpl-mcp-server](https://github.com/nguyenanhducs/fpl-mcp-server) | MCP server providing AI assistants with tools and resources for Fantasy Premi... | 77 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-nguyenanhducs-fpl-mcp-server) |
| [mcp-gemini](https://github.com/crunchtools/mcp-gemini) | Secure MCP server for Google Gemini AI with 39 tools for text, images, videos... | 71 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-gemini) |

### 📡 <a name="iot--hardware"></a>IoT & Hardware

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [xiaozhi-esp32-server-java](https://github.com/joey-zhou/xiaozhi-esp32-server-java) | 小智ESP32的Java企业级管理平台，提供设备监控、音色定制、角色切换和对话记录管理的前后端及服务端一体化解决方案 | 92 ✅ | 1.2k | [View](https://agentseal.org/mcp/https-githubcom-joey-zhou-xiaozhi-esp32-server-java) |
| [droidmind](https://github.com/hyperb1iss/droidmind) | Control Android devices with AI through the Model Context Protocol, enabling ... | 71 ⚠️ | 360 | [View](https://agentseal.org/mcp/https-githubcom-hyperb1iss-droidmind) |
| [hass-mcp](https://github.com/voska/hass-mcp) | An MCP server for controlling and monitoring a Home Assistant smart home inst... | 72 ⚠️ | 284 | [View](https://agentseal.org/mcp/https-githubcom-voska-hass-mcp) |
| [mcp-3d-printer-server](https://github.com/dmontgomery40/mcp-3d-printer-server) | MCP server for controlling and monitoring 3D printers across multiple platfor... | 90 ✅ | 161 | [View](https://agentseal.org/mcp/mcp-3d-printer-server) |
| [esp-mcp](https://github.com/horw/esp-mcp) | An MCP server for building, configuring, testing, and flashing ESP-IDF firmwa... | 85 ✅ | 139 | [View](https://agentseal.org/mcp/https-githubcom-horw-esp-mcp) |
| [buttplug-mcp](https://github.com/conacademy/buttplug-mcp) | Buttplug.io Model Context Protocol (MCP) Server | 92 ✅ | 126 | [View](https://agentseal.org/mcp/https-githubcom-conacademy-buttplug-mcp) |
| [ble-mcp-server](https://github.com/es617/ble-mcp-server) | Bluetooth Low Energy (BLE) MCP server for Claude Code and other MCP-compatibl... | 75 ⚠️ | 7 | [View](https://agentseal.org/mcp/https-githubcom-es617-ble-mcp-server) |
| [ble-mcp-server.git](https://github.com/es617/ble-mcp-server.git) | A Bluetooth Low Energy (BLE) management server enabling agents to scan for, c... | 67 ⚠️ | 7 | [View](https://agentseal.org/mcp/https-githubcom-es617-ble-mcp-servergit) |
| [pcb-mcp](https://github.com/bunnyf/pcb-mcp) | An MCP server that automates KiCad PCB design workflows — running DRC/ERC che... | 92 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-bunnyf-pcb-mcp) |
| [mcp-motor-current-signature-analysis](https://github.com/LGDiMaggio/mcp-motor-current-signature-analysis) | An MCSA (Motor Current Signature Analysis) server providing spectral analysis... | 92 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-lgdimaggio-mcp-motor-current-signature-analysis) |
| [serial-mcp-server.git](https://github.com/es617/serial-mcp-server.git) | An MCP server for managing serial port connections to hardware devices, with ... | 68 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-es617-serial-mcp-servergit) |
| [nanoleaf-mcp-server](https://github.com/srnetadmin/nanoleaf-mcp-server) | MCP server for controlling Nanoleaf smart lights through Warp terminal | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-srnetadmin-nanoleaf-mcp-server) |
| [wemo-mcp-server](https://github.com/apiarya/wemo-mcp-server) | An MCP server for discovering, monitoring, and controlling Belkin WeMo smart ... | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-apiarya-wemo-mcp-server) |

## 🏆 Safest Servers (Score >= 95)

| Server | Score | Tools | Stars | Report |
|--------|------:|------:|------:|--------|
| [mcp-summarizer](https://github.com/0xshellming/mcp-summarizer) | 100 | 1 | 157 | [View](https://agentseal.org/mcp/https-githubcom-0xshellming-mcp-summarizer) |
| [crash-mcp](https://github.com/nikkoxgonzales/crash-mcp) | 100 | 1 | 67 | [View](https://agentseal.org/mcp/https-githubcom-nikkoxgonzales-crash-mcp) |
| [mcp-open-library](https://github.com/8enSmith/mcp-open-library) | 100 | 6 | 62 | [View](https://agentseal.org/mcp/https-githubcom-8ensmith-mcp-open-library) |
| [mcp_weather_server](https://github.com/isdaniel/mcp_weather_server) | 100 | 8 | 44 | [View](https://agentseal.org/mcp/https-githubcom-isdaniel-mcpweatherserver) |
| [actor-critic-thinking-mcp](https://github.com/aquarius-wing/actor-critic-thinking-mcp) | 100 | 1 | 32 | [View](https://agentseal.org/mcp/https-githubcom-aquarius-wing-actor-critic-thinking-mcp) |
| [brlaw_mcp_server](https://github.com/pdmtt/brlaw_mcp_server) | 100 | 3 | 27 | [View](https://agentseal.org/mcp/https-githubcom-pdmtt-brlawmcpserver) |
| [fabric-mcp-server](https://github.com/adapoet/fabric-mcp-server) | 100 | 1 | 19 | [View](https://agentseal.org/mcp/https-githubcom-adapoet-fabric-mcp-server) |
| [bilibili-mcp-server](https://github.com/wangshunnn/bilibili-mcp-server) | 100 | 3 | 13 | [View](https://agentseal.org/mcp/https-githubcom-wangshunnn-bilibili-mcp-server) |
| [mcp-claude-hackernews](https://github.com/imprvhub/mcp-claude-hackernews) | 100 | 5 | 10 | [View](https://agentseal.org/mcp/https-githubcom-imprvhub-mcp-claude-hackernews) |
| [heatpump-mcp-server](https://github.com/jiweiqi/heatpump-mcp-server) | 100 | 6 | 3 | [View](https://agentseal.org/mcp/https-githubcom-jiweiqi-heatpump-mcp-server) |
| [time-node-mcp](https://github.com/davidan90/time-node-mcp) | 100 | 4 | 2 | [View](https://agentseal.org/mcp/https-githubcom-davidan90-time-node-mcp) |
| [physbound](https://github.com/JonesRobM/physbound) | 100 | 4 | 1 | [View](https://agentseal.org/mcp/https-githubcom-jonesrobm-physbound) |
| [trinvmcp](https://github.com/cqtrinv/trinvmcp) | 100 | 2 | 1 | [View](https://agentseal.org/mcp/https-githubcom-cqtrinv-trinvmcp) |
| [algora-mcp-server](https://github.com/idapixl/algora-mcp-server) | 100 | 5 | 1 | [View](https://agentseal.org/mcp/https-githubcom-idapixl-algora-mcp-server) |
| [dolar-mcp](https://github.com/dan1d/dolar-mcp) | 100 | 6 | - | [View](https://agentseal.org/mcp/https-githubcom-dan1d-dolar-mcp) |
| [lapalma24-mcp](https://github.com/La-Palma-24/lapalma24-mcp) | 100 | 6 | - | [View](https://agentseal.org/mcp/https-githubcom-la-palma-24-lapalma24-mcp) |
| [chrono-mcp](https://github.com/JMoak/chrono-mcp) | 100 | 2 | - | [View](https://agentseal.org/mcp/https-githubcom-jmoak-chrono-mcp) |
| [cookwith-mcp](https://github.com/blaideinc/cookwith-mcp) | 99 | 2 | - | [View](https://agentseal.org/mcp/https-githubcom-blaideinc-cookwith-mcp) |
| [bilibili-mcp-js](https://github.com/34892002/bilibili-mcp-js) | 99 | 8 | 153 | [View](https://agentseal.org/mcp/https-githubcom-34892002-bilibili-mcp-js) |
| [mcp-server-leetcode](https://github.com/doggybee/mcp-server-leetcode) | 99 | 7 | 40 | [View](https://agentseal.org/mcp/https-githubcom-doggybee-mcp-server-leetcode) |

## ⚠️ Wider Attack Surface

These servers are NOT broken or malicious. They expose powerful capabilities (code execution, file system access, network requests) that give AI agents a wider attack surface. An adversary could exploit these through prompt injection. Use with sandboxing and human oversight.

| Server | Score | Findings | Tools | Stars | Report |
|--------|------:|---------:|------:|------:|--------|
| [klavis](https://github.com/klavis-ai/klavis) | 68 | **152** | 554 | 5.7k | [View](https://agentseal.org/mcp/https-githubcom-klavis-ai-klavis) |
| [labmate-mcp](https://github.com/JonasRackl/labmate-mcp) | 71 | **85** | 81 | - | [View](https://agentseal.org/mcp/labmate-mcp) |
| [graphlit-mcp-server](https://github.com/graphlit/graphlit-mcp-server) | 72 | **78** | 73 | 372 | [View](https://agentseal.org/mcp/https-githubcom-graphlit-graphlit-mcp-server) |
| [chat](https://github.com/deco-cx/chat) | 77 | **69** | 188 | 350 | [View](https://agentseal.org/mcp/https-githubcom-deco-cx-chat) |
| [armor-crypto-mcp](https://github.com/armorwallet/armor-crypto-mcp) | 69 | **46** | 37 | 191 | [View](https://agentseal.org/mcp/armor-crypto-mcp) |
| [apisix-mcp](https://github.com/api7/apisix-mcp) | 67 | **43** | 32 | 34 | [View](https://agentseal.org/mcp/https-githubcom-api7-apisix-mcp) |
| [mcp-gitlab](https://github.com/crunchtools/mcp-gitlab) | 68 | **42** | 63 | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-gitlab) |
| [freshdesk_mcp](https://github.com/effytech/freshdesk_mcp) | 80 | **40** | 59 | 46 | [View](https://agentseal.org/mcp/https-githubcom-effytech-freshdeskmcp) |
| [mcp](https://github.com/hopx-ai/mcp) | 58 | **37** | 35 | 165 | [View](https://agentseal.org/mcp/https-githubcom-hopx-ai-mcp) |
| [audius-mcp-atris](https://github.com/glassBead-tc/audius-mcp-atris) | 60 | **36** | 106 | 1 | [View](https://agentseal.org/mcp/https-githubcom-glassbead-tc-audius-mcp-atris) |
| [illumio-mcp-server](https://github.com/alexgoller/illumio-mcp-server) | 78 | **35** | 38 | 5 | [View](https://agentseal.org/mcp/https-githubcom-alexgoller-illumio-mcp-server) |
| [mcp_omni_connect](https://github.com/abiorh001/mcp_omni_connect) | 77 | **34** | 273 | 232 | [View](https://agentseal.org/mcp/https-githubcom-abiorh001-mcpomniconnect) |
| [memora](https://github.com/agentic-mcp-tools/memora) | 64 | **33** | 35 | 309 | [View](https://agentseal.org/mcp/https-githubcom-agentic-mcp-tools-memora) |
| [hdw-mcp-server](https://github.com/horizondatawave/hdw-mcp-server) | 67 | **31** | 69 | 59 | [View](https://agentseal.org/mcp/https-githubcom-horizondatawave-hdw-mcp-server) |
| [hillnote-mcp-server](https://github.com/Rajathbail/hillnote-mcp-server) | 70 | **31** | 47 | 1 | [View](https://agentseal.org/mcp/https-githubcom-rajathbail-hillnote-mcp-server) |

## 📛 Add a Security Badge

Show your server's trust score in your README:

```markdown
[![AgentSeal MCP](https://agentseal.org/api/v1/mcp/YOUR-SLUG/badge)](https://agentseal.org/mcp/YOUR-SLUG)
```

## 🔍 Submit Your Server

Get your MCP server scanned for free:
-> [agentseal.org/mcp/submit](https://agentseal.org/mcp/submit)

## Contributing

This list is auto-generated from [AgentSeal's MCP Registry](https://agentseal.org/mcp).
To add a server, [submit it for scanning](https://agentseal.org/mcp/submit).
To report a false positive, [email us](mailto:hello@agentseal.org).

## License

CC BY-SA 4.0 - free to share and adapt with attribution.
