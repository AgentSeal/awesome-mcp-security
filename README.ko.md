# 🛡️ MCP 서버 보안 레지스트리

> **764개의 MCP 서버**를 스캔하고 AI 에이전트 보안 위험을 분석했습니다.
> 점수는 AI 에이전트가 각 서버를 얼마나 안전하게 사용할 수 있는지를 반영하며, 서버 자체의 코드 품질을 평가하는 것이 아닙니다.
> 매일 업데이트됩니다. [AgentSeal](https://agentseal.org) 제공.

[English](README.md) · [中文](README.zh.md) · [日本語](README.ja.md) · **한국어**

## 빠른 통계

| 지표 | 수량 |
|------|------|
| 스캔된 총 서버 수 | **764** |
| ✅ 안전 (점수 ≥ 80) | **598** |
| ⚠️ 검토 필요 (점수 50-79) | **166** |
| 총 보안 발견 사항 | **6098** |
| 최종 업데이트 | 2026년 3월 13일 |

## 평가 방식

모든 서버는 **9개의 보안 분석기**를 통해 테스트됩니다:

- **스키마 분석** - 도구 매개변수 유형 및 제약 조건 검증
- **정적 패턴 탐지** - 커맨드 인젝션, SSRF, 경로 탐색 패턴 탐지
- **프롬프트 인젝션 스캔** - 도구 설명에 숨겨진 지시 탐지
- **독성 흐름 매핑** - 위험한 도구 체인 식별 (예: 비밀키 읽기 - 외부 URL로 전송)
- **유니코드 탐지** - 보이지 않는 문자 공격 포착
- **심층 분석** - 45개 이상의 MCP 전용 공격 패턴으로 능동적 탐지
- **주석 및 지시 분석** - 동작 변경 메타데이터 검사
- **리소스 분석** - 노출된 리소스와 템플릿 평가
- **LLM 분류** - Claude 기반 도구 의도 시맨틱 분석

**신뢰 점수:** 0-100은 AI 에이전트가 이 서버를 얼마나 안전하게 사용할 수 있는지를 측정합니다.
낮은 점수는 서버에 버그가 있거나 악의적이라는 의미가 아닙니다. AI 에이전트가 해당 서버를 사용할 때 더 넓은 공격 표면(예: 코드 실행, 파일 접근, 네트워크 요청)이 존재하며, 공격자가 프롬프트 인젝션이나 도구 오염을 통해 이를 악용할 수 있다는 것을 의미합니다.

- **안전 (>= 80):** 공격 표면이 작습니다. 에이전트가 최소한의 위험으로 사용할 수 있습니다.
- **검토 필요 (50-79):** 공격 표면을 확장하는 상당한 기능이 있습니다. 적절한 보호 장치와 함께 사용하세요.
- **위험 (20-49):** 공격 표면이 넓습니다. 엄격한 샌드박싱과 사람의 감독이 필요합니다.
- **위험함 (< 20):** 심각한 보안 문제가 있습니다. 자동화된 사용은 권장하지 않습니다.

## 범례

| 기호 | 의미 |
|------|------|
| ✅ | 안전 - AI 에이전트의 공격 표면이 작음 |
| ⚠️ | 검토 필요 - 더 넓은 기능, 보호 장치와 함께 사용 |
| 🟠 | 위험 - 공격 표면이 넓음, 샌드박싱 필요 |
| 🔴 | 위험함 - 자동화된 사용 비권장 |

## 카테고리

- [🛠️ 개발자 도구](#developer-tools) (240)
- [🔍 검색 및 지식](#search--knowledge) (59)
- [💻 코드 및 IDE](#code--ide) (27)
- [☁️ 클라우드 및 인프라](#cloud--infrastructure) (32)
- [📝 콘텐츠 및 미디어](#content--media) (45)
- [🔌 API 개발](#api-development) (17)
- [🗄️ 데이터베이스 및 SQL](#database--sql) (25)
- [💬 커뮤니케이션](#communication) (27)
- [⚙️ 시스템 관리](#system-administration) (11)
- [🔒 보안 및 인증](#security--auth) (40)
- [🕸️ 웹 스크래핑 및 수집](#web-scraping--collection) (23)
- [📁 파일 시스템 및 스토리지](#file-system--storage) (13)
- [💰 금융 및 암호화폐](#finance--crypto) (35)
- [🧠 데이터 과학 및 ML](#data-science--ml) (17)
- [📡 IoT 및 하드웨어](#iot--hardware) (11)

### 🛠️ <a name="developer-tools"></a>개발자 도구

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [markitdown](https://github.com/microsoft/markitdown) | 파일 및 오피스 문서를 Markdown으로 변환하는 Python 도구. | 88 ✅ | 90.7k | [View](https://agentseal.org/mcp/https-githubcom-microsoft-markitdown) |
| [chrome-devtools-mcp](https://github.com/chromedevtools/chrome-devtools-mcp) | 코딩 에이전트를 위한 Chrome DevTools | 73 ⚠️ | 28.8k | [View](https://agentseal.org/mcp/chrome-devtools-mcp) |
| [Playwright](https://github.com/microsoft/playwright-mcp) | Playwright를 사용하여 대규모 언어 모델(LLM)의 브라우저 상호작용을 자동화... | 62 ⚠️ | 28.7k | [View](https://agentseal.org/mcp/https-githubcom-microsoft-playwright-mcp) |
| [GitHub](https://github.com/github/github-mcp-server) | GitHub API와의 고급 자동화 및 상호작용 기능을 제공... | 70 ⚠️ | 27.8k | [View](https://agentseal.org/mcp/https-githubcom-github-github-mcp-server) |
| [claude-flow](https://github.com/ruvnet/claude-flow) | 자율 에이전트 스웜을 배포하는 엔터프라이즈 AI 오케스트레이션 플랫폼... | 86 ✅ | 20.9k | [View](https://agentseal.org/mcp/https-githubcom-ruvnet-claude-flow) |
| [beads](https://github.com/steveyegge/beads) | Beads - 코딩 에이전트를 위한 메모리 업그레이드 | 86 ✅ | 18.9k | [View](https://agentseal.org/mcp/https-githubcom-steveyegge-beads) |
| [archon](https://github.com/coleam00/archon) | Archon OS 베타 - AI 에이전트를 위한 지식 및 작업 관리 백본... | 92 ✅ | 13.8k | [View](https://agentseal.org/mcp/https-githubcom-coleam00-archon) |
| [mcp-go](https://github.com/mark3labs/mcp-go) | Model Context Protocol(MCP)의 Go 구현으로, 원활한 통합을 지원... | 89 ✅ | 8.3k | [View](https://agentseal.org/mcp/https-githubcom-mark3labs-mcp-go) |
| [git-mcp](https://github.com/idosal/git-mcp) | 코드 환각을 종식시키세요! GitMCP는 무료 오픈소스 원격 MCP... | 78 ⚠️ | 7.8k | [View](https://agentseal.org/mcp/git-mcp) |
| [browser-tools-mcp](https://github.com/agentdeskai/browser-tools-mcp) | Cursor 및 기타 MCP 호환 IDE에서 직접 브라우저 로그를 모니터링. | 91 ✅ | 7.1k | [View](https://agentseal.org/mcp/https-githubcom-agentdeskai-browser-tools-mcp) |
| [cursor-talk-to-figma-mcp](https://github.com/sonnylazuardi/cursor-talk-to-figma-mcp) | Cursor, Claude Code 등 AI 에이전트가 Figma를 읽고 수정할 수 있는 MCP 통합... | 88 ✅ | 6.5k | [View](https://agentseal.org/mcp/https-githubcom-sonnylazuardi-cursor-talk-to-figma-mcp) |
| [cursor-talk-to-figma-mcp](https://github.com/grab/cursor-talk-to-figma-mcp) | TalkToFigma: AI 에이전트(Cursor, Claude Code)와 Figma 간 MCP 통합... | 88 ✅ | 6.5k | [View](https://agentseal.org/mcp/https-githubcom-grab-cursor-talk-to-figma-mcp) |
| [ida-pro-mcp](https://github.com/mrexodia/ida-pro-mcp) | IDA Pro와 언어 모델을 연결하는 AI 기반 역공학 어시스턴트... | 88 ✅ | 6.3k | [View](https://agentseal.org/mcp/ida-pro-mcp) |
| [mcp](https://github.com/browsermcp/mcp) | Browser MCP는 AI 앱이 브라우저와 상호작용할 수 있게 하는 MCP 서버... | 86 ✅ | 6.0k | [View](https://agentseal.org/mcp/browsermcp-mcp) |
| [desktopcommandermcp](https://github.com/wonderwhy-er/desktopcommandermcp) | 터미널 제어, 파일 시스템 검색 기능을 제공하는 Claude용 MCP 서버... | 63 ⚠️ | 5.7k | [View](https://agentseal.org/mcp/https-githubcom-wonderwhy-er-desktopcommandermcp) |
| [klavis](https://github.com/klavis-ai/klavis) | Klavis AI (YC X25): AI 에이전트가 도구를 원격으로 사용할 수 있는 MCP 통합 플랫폼... | 68 ⚠️ | 5.7k | [View](https://agentseal.org/mcp/https-githubcom-klavis-ai-klavis) |
| [praisonai](https://github.com/mervinpraison/praisonai) | PraisonAI 🦞 - 24/7 AI 직원 팀. 복잡한 과제를 자동화하고 해결... | 78 ⚠️ | 5.7k | [View](https://agentseal.org/mcp/https-githubcom-mervinpraison-praisonai) |
| [playwright-mcp-server](https://github.com/executeautomation/mcp-playwright) | Playwright MCP 서버 - 브라우저와 API를 자동화하는 도구... | 73 ⚠️ | 5.3k | [View](https://agentseal.org/mcp/executeautomation-playwright-mcp-server) |
| [magic](https://github.com/21st-dev/magic-mcp) | Cursor/WindSurf/Cline에서 사용하는 v0 같은 도구. 21st dev Magic MCP 서버... | 82 ✅ | 4.4k | [View](https://agentseal.org/mcp/21st-dev-magic) |
| [osaurus](https://github.com/osaurus-ai/osaurus) | 나만의 AI. AI 에이전트를 위한 네이티브 macOS 하니스 - 모든 모델, 영구... | 79 ⚠️ | 4.1k | [View](https://agentseal.org/mcp/osaurus-ai-osaurus) |
| [context-mode](https://github.com/mksglu/context-mode) | MCP는 도구 접근을 위한 프로토콜. 컨텍스트를 위한 가상화 레이어. | 78 ⚠️ | 3.7k | [View](https://agentseal.org/mcp/https-githubcom-mksglu-context-mode) |
| [mcp-feedback-enhanced](https://github.com/minidoracat/mcp-feedback-enhanced) | AI 도구의 대화형 사용자 피드백 및 명령 실행을 위한 향상된 MCP 서버... | 91 ✅ | 3.6k | [View](https://agentseal.org/mcp/https-githubcom-minidoracat-mcp-feedback-enhanced) |
| [archestra](https://github.com/archestra-ai/archestra) | 가드레일, MCP 레지스트리, 게이트웨이 및 오케스트레이터를 갖춘 엔터프라이즈 AI 플랫폼 | 92 ✅ | 3.5k | [View](https://agentseal.org/mcp/https-githubcom-archestra-ai-archestra) |
| [refact-chat-js](https://github.com/smallcloudai/refact) | 엔지니어링 작업을 처음부터 끝까지 처리하는 AI 에이전트: 개발자 도구와 통합... | 92 ✅ | 3.5k | [View](https://agentseal.org/mcp/refact-chat-js) |
| [shadcn-ui-mcp-server](https://github.com/jpisnice/shadcn-ui-mcp-server) | LLM이 shadcn UI 컴포넌트 구조, 사용법에 대한 컨텍스트를 얻을 수 있는 MCP 서버... | 83 ✅ | 2.7k | [View](https://agentseal.org/mcp/jpisnice-shadcn-ui-mcp-server) |
| [mcp-cli](https://github.com/chrishayuk/mcp-cli) | Model Context Protocol 서버와 상호작용하기 위한 명령줄 인터페이스... | 92 ✅ | 1.9k | [View](https://agentseal.org/mcp/https-githubcom-chrishayuk-mcp-cli) |
| [ios-simulator-mcp](https://github.com/joshuayoes/ios-simulator-mcp) | iOS 시뮬레이터와 상호작용하기 위한 MCP 서버 | 91 ✅ | 1.7k | [View](https://agentseal.org/mcp/https-githubcom-joshuayoes-ios-simulator-mcp) |
| [mcp-installer](https://github.com/anaisbetts/mcp-installer) | 다른 MCP 서버를 설치해주는 MCP 서버 | 89 ✅ | 1.5k | [View](https://agentseal.org/mcp/anaisbetts-mcp-installer) |
| [notebooklm-mcp](https://github.com/pleaseprompto/notebooklm-mcp) | NotebookLM용 MCP 서버 - AI 에이전트(Claude Code, Codex)가 연구할 수 있도록... | 73 ⚠️ | 1.4k | [View](https://agentseal.org/mcp/https-githubcom-pleaseprompto-notebooklm-mcp) |
| [coderunner](https://github.com/instavm/coderunner) | AI 에이전트를 위한 로컬 샌드박스 | 80 ⚠️ | 801 | [View](https://agentseal.org/mcp/https-githubcom-instavm-coderunner) |
| [vibetest-use](https://github.com/browser-use/vibetest-use) | Vibetest MCP - Browser-Use 에이전트를 이용한 자동화된 QA 테스트 | 87 ✅ | 772 | [View](https://agentseal.org/mcp/https-githubcom-browser-use-vibetest-use) |
| [driftdetect-mcp](https://github.com/dadbodgeoff/drift) | AI를 위한 코드베이스 인텔리전스. 패턴과 규칙을 탐지하고 결정을 기억... | 85 ✅ | 760 | [View](https://agentseal.org/mcp/driftdetect-mcp) |
| [just-prompt](https://github.com/disler/just-prompt) | 주요 LLM 제공자에 대한 통합 인터페이스를 제공하는 MCP 서버... | 89 ✅ | 719 | [View](https://agentseal.org/mcp/https-githubcom-disler-just-prompt) |
| [blueprint-mcp](https://github.com/arcadeai/blueprint-mcp) | @antvis를 사용한 코드베이스 및 시스템 아키텍처 이해를 위한 다이어그램 생성... | 92 ✅ | 585 | [View](https://agentseal.org/mcp/https-githubcom-arcadeai-blueprint-mcp) |
| [n8n-workflow-builder](https://github.com/makafeli/n8n-workflow-builder) | Model Context Protocol을 통한 n8n 워크플로우 자동화를 위한 AI 어시스턴트 통합... | 87 ✅ | 501 | [View](https://agentseal.org/mcp/https-githubcom-makafeli-n8n-workflow-builder) |
| [web-agent-protocol](https://github.com/ota-tech-ai/web-agent-protocol) | 🌐Web Agent Protocol (WAP) - 브라우저에서 사용자 상호작용을 기록하고 재생... | 92 ✅ | 493 | [View](https://agentseal.org/mcp/https-githubcom-ota-tech-ai-web-agent-protocol) |
| [airtable-mcp-server](https://github.com/domdomegg/airtable-mcp-server) | 🗂️🤖 AI 시스템이 Airtable과 상호작용할 수 있게 하는 Model Context Protocol 서버... | 81 ✅ | 430 | [View](https://agentseal.org/mcp/https-githubcom-domdomegg-airtable-mcp-server) |
| [kicad-mcp](https://github.com/lamaalrajih/kicad-mcp) | Mac, Windows, Linux용 KiCad Model Context Protocol 서버 | 92 ✅ | 401 | [View](https://agentseal.org/mcp/https-githubcom-lamaalrajih-kicad-mcp) |
| [lingti-bot](https://github.com/ruilisi/lingti-bot) | 🐕⚡ 극도로 간결하고 효율적인, 초 단위 접속, 원클릭 사용 AI Bot | 75 ⚠️ | 368 | [View](https://agentseal.org/mcp/https-githubcom-ruilisi-lingti-bot) |
| [MemoryMesh](https://github.com/CheMiguel23/MemoryMesh) | MCP를 사용하여 구조화된 정보를 제공하는 지식 그래프 서버... | 81 ✅ | 335 | [View](https://agentseal.org/mcp/https-githubcom-chemiguel23-memorymesh) |
| [paws-on-mcp](https://github.com/hemanth/paws-on-mcp) | 최신 사양을 구현하는 포괄적인 Model Context Protocol(MCP) 서버... | 86 ✅ | 331 | [View](https://agentseal.org/mcp/https-githubcom-hemanth-paws-on-mcp) |
| [moling](https://github.com/gojue/moling) | MoLing은 컴퓨터 사용 및 브라우저 사용 기반 MCP 서버로, 로컬에 배포... | 78 ⚠️ | 330 | [View](https://agentseal.org/mcp/https-githubcom-gojue-moling) |
| [consult7](https://github.com/szeider/consult7) | 대용량 컨텍스트를 가진 언어 모델을 상담하는 MCP 서버 | 85 ✅ | 291 | [View](https://agentseal.org/mcp/https-githubcom-szeider-consult7) |
| [chrome-devtools-mcp](https://github.com/benjaminr/chrome-devtools-mcp) | Chrome DevTools Protocol을 따르는 Chrome DevTools용 MCP 서버... | 74 ⚠️ | 289 | [View](https://agentseal.org/mcp/https-githubcom-benjaminr-chrome-devtools-mcp) |
| [FileScopeMCP](https://github.com/admica/FileScopeMCP) | 의존성 관계를 기반으로 중요한 파일을 식별하여 코드베이스를 분석... | 82 ✅ | 283 | [View](https://agentseal.org/mcp/https-githubcom-admica-filescopemcp) |
| [MCP-Server-Playwright](https://github.com/Automata-Labs-team/MCP-Server-Playwright) | 전체 원격 제어를 제공하는 Playwright 기반 브라우저 자동화 MCP 서버... | 74 ⚠️ | 283 | [View](https://agentseal.org/mcp/https-githubcom-automata-labs-team-mcp-server-playwright) |
| [mcp-reasoner](https://github.com/jacck/mcp-reasoner) | 빔 서치를 포함한 Claude Desktop용 체계적 추론 MCP 서버 구현... | 92 ✅ | 277 | [View](https://agentseal.org/mcp/https-githubcom-jacck-mcp-reasoner) |
| [lucid](https://github.com/get-lucid/lucid) | 검증된 실시간 지식으로 자율 에이전트를 기반하는 인텔리전스 레이어... | 92 ✅ | 260 | [View](https://agentseal.org/mcp/https-githubcom-get-lucid-lucid) |
| [weather-mcp-server](https://github.com/tuankiri/weather-mcp-server) | AI 어시스턴트가 실시간 날씨 데이터를 검색할 수 있는 MCP 서버... | 92 ✅ | 239 | [View](https://agentseal.org/mcp/https-githubcom-tuankiri-weather-mcp-server) |
| [frida-mcp](https://github.com/dnakov/frida-mcp) | Frida용 MCP stdio 서버 | 91 ✅ | 237 | [View](https://agentseal.org/mcp/https-githubcom-dnakov-frida-mcp) |
| [tmux-mcp](https://github.com/nickgnd/tmux-mcp) | 터미널 멀티플렉서 tmux를 위한 MCP 서버. | 83 ✅ | 235 | [View](https://agentseal.org/mcp/https-githubcom-nickgnd-tmux-mcp) |
| [tmux-mcp](https://github.com/nickgnd/tmux-mcp) | 터미널 멀티플렉서 tmux를 위한 MCP 서버. | 83 ✅ | 235 | [View](https://agentseal.org/mcp/tmux-mcp) |
| [overseer](https://github.com/dmmulroy/overseer) | 에이전트 작업 관리를 위한 CLI 및 Codemode MCP 서버 | 92 ✅ | 222 | [View](https://agentseal.org/mcp/https-githubcom-dmmulroy-overseer) |
| [mcp-taskmanager](https://github.com/kazuph/mcp-taskmanager) | Claude가 대기열 기반 시스템에서 작업을 관리하고 실행할 수 있게 하는 MCP 서버... | 91 ✅ | 212 | [View](https://agentseal.org/mcp/kazuph-mcp-taskmanager) |
| [opik-mcp](https://github.com/comet-ml/opik-mcp) | 원활한 IDE 통합을 지원하는 Opik용 Model Context Protocol(MCP) 구현... | 92 ✅ | 199 | [View](https://agentseal.org/mcp/https-githubcom-comet-ml-opik-mcp) |
| [@rocketshipai](https://github.com/rocketship-ai/rocketship) | 코딩 에이전트가 테스트를 작성하고 실행할 수 있는 오픈소스 QA 테스트 프레임워크... | 92 ✅ | 182 | [View](https://agentseal.org/mcp/rocketshipai) |
| [anki-mcp-server](https://github.com/scorzeth/anki-mcp-server) | 로컬 Anki 플래시카드 앱과 통합되어 카드 관리를 지원하는 MCP 서버... | 98 ✅ | 178 | [View](https://agentseal.org/mcp/https-githubcom-scorzeth-anki-mcp-server) |
| [mcp-doc](https://github.com/meterlong/mcp-doc) | FastMCP 기반의 강력한 Word 문서 처리 서비스로, AI 어시스턴트가 활용... | 89 ✅ | 173 | [View](https://agentseal.org/mcp/https-githubcom-meterlong-mcp-doc) |
| [llmctx](https://github.com/khromov/llmctx) | AI 코딩 도구를 위한 Svelte 5 및 SvelteKit 개발자 문서를 제공하는 MCP 엔드포인트... | 92 ✅ | 160 | [View](https://agentseal.org/mcp/https-githubcom-khromov-llmctx) |
| [mcp-server-langfuse](https://github.com/langfuse/mcp-server-langfuse) | Langfuse 프롬프트 관리를 위한 Model Context Protocol(MCP) 서버... | 92 ✅ | 158 | [View](https://agentseal.org/mcp/https-githubcom-langfuse-mcp-server-langfuse) |
| [erickwendel-contributions-mcp](https://github.com/erickwendel/erickwendel-contributions-mcp) | Erick Wendel의 기여를 조회하는 도구를 제공하는 MCP 서버... | 92 ✅ | 136 | [View](https://agentseal.org/mcp/https-githubcom-erickwendel-erickwendel-contributions-mcp) |
| [mcp-server](https://github.com/browserstack/mcp-server) | BrowserStack 공식 MCP 서버 | 69 ⚠️ | 130 | [View](https://agentseal.org/mcp/https-githubcom-browserstack-mcp-server) |
| [mcp-server-atlassian-bitbucket](https://github.com/aashari/mcp-server-atlassian-bitbucket) | Atlassian Bitbucket용 Node.js/TypeScript MCP 서버. AI 시스템(LLM)을 지원... | 74 ⚠️ | 127 | [View](https://agentseal.org/mcp/https-githubcom-aashari-mcp-server-atlassian-bitbucket) |
| [pluggedin-mcp-proxy](https://github.com/VeriTeknik/pluggedin-mcp-proxy) | Plugged.in MCP 서버는 하나의 MCP로 다른 모든 MCP를 관리합니다. | 81 ✅ | 124 | [View](https://agentseal.org/mcp/https-githubcom-veriteknik-pluggedin-mcp-proxy) |
| [mcp-gdb](https://github.com/signal-slot/mcp-gdb) | AI 어시스턴트를 위한 GDB 디버깅 기능을 제공하는 MCP 서버... | 86 ✅ | 110 | [View](https://agentseal.org/mcp/https-githubcom-signal-slot-mcp-gdb) |
| [sourcerer-mcp](https://github.com/st3v3nmw/sourcerer-mcp) | 토큰 낭비를 줄이는 시맨틱 코드 검색 및 탐색 MCP | 86 ✅ | 108 | [View](https://agentseal.org/mcp/https-githubcom-st3v3nmw-sourcerer-mcp) |
| [lapras-mcp-server](https://github.com/lapras-inc/lapras-mcp-server) | lapras.com 공식 MCP Server | 89 ✅ | 100 | [View](https://agentseal.org/mcp/https-githubcom-lapras-inc-lapras-mcp-server) |
| [terminal-controller-mcp](https://github.com/gongrzhe/terminal-controller-mcp) | 안전한 터미널 명령 실행을 가능하게 하는 MCP 서버... | 80 ⚠️ | 99 | [View](https://agentseal.org/mcp/https-githubcom-gongrzhe-terminal-controller-mcp) |
| [json-mcp-server](https://github.com/gongrzhe/json-mcp-server) | JSON 처리 및 가공 MCP 서버 | 88 ✅ | 89 | [View](https://agentseal.org/mcp/https-githubcom-gongrzhe-json-mcp-server) |
| [unreal-mcp](https://github.com/runreal/unreal-mcp) | Unreal Python 원격 실행을 사용하는 Unreal Engine용 MCP 서버 | 71 ⚠️ | 82 | [View](https://agentseal.org/mcp/runreal-unreal-mcp) |
| [mcp-server-circleci](https://github.com/CircleCI-Public/mcp-server-circleci) | CircleCI를 위해 설계된 MCP 전용 서버 구현... | 80 ✅ | 80 | [View](https://agentseal.org/mcp/https-githubcom-circleci-public-mcp-server-circleci) |
| [mcp-server-openai](https://github.com/pierrebrunelle/mcp-server-openai) | MCP 프로토콜을 사용하여 Claude에서 직접 OpenAI 모델을 쿼리. | 92 ✅ | 79 | [View](https://agentseal.org/mcp/mcp-server-openai) |
| [multi-ai-advisor-mcp](https://github.com/yuchenssr/multi-ai-advisor-mcp) | 의사결정을 위한 모델 평의회 | 92 ✅ | 78 | [View](https://agentseal.org/mcp/https-githubcom-yuchenssr-multi-ai-advisor-mcp) |
| [roundtable](https://github.com/askbudi/roundtable) | 여러 AI 코딩 어시스턴트(Claude, Gemini...)를 조율하는 로컬 MCP 서버... | 81 ✅ | 78 | [View](https://agentseal.org/mcp/https-githubcom-askbudi-roundtable) |
| [unifai-sdk-js](https://github.com/unifai-network/unifai-sdk-js) | AI 네이티브 플랫폼 Unifai를 위한 Javascript/Typescript SDK... | 86 ✅ | 75 | [View](https://agentseal.org/mcp/https-githubcom-unifai-network-unifai-sdk-js) |
| [energyplus-mcp](https://github.com/lbnl-eta/energyplus-mcp) | AI 어시스턴트가 건물 에너지 시뮬레이션을 수행할 수 있게 하는 최초의 오픈소스 MCP 서버... | 90 ✅ | 69 | [View](https://agentseal.org/mcp/https-githubcom-lbnl-eta-energyplus-mcp) |
| [alibabacloud-devops-mcp-server](https://github.com/aliyun/alibabacloud-devops-mcp-server) | Yunxiao MCP 서버는 AI 어시스턴트에게 DevOps 도구와 상호작용하는 기능을 제공... | 87 ✅ | 69 | [View](https://agentseal.org/mcp/https-githubcom-aliyun-alibabacloud-devops-mcp-server) |
| [clarity-mcp-server](https://github.com/microsoft/clarity-mcp-server) | Microsoft Clarity를 위한 Model Context Protocol(MCP) 서버 | 84 ✅ | 68 | [View](https://agentseal.org/mcp/microsoft-clarity-mcp-server) |
| [deepseek-thinker-mcp](https://github.com/ruixingshi/deepseek-thinker-mcp) | OpenAI API를 통해 Deepseek의 추론 프로세스에 접근할 수 있는 MCP 서버... | 92 ✅ | 67 | [View](https://agentseal.org/mcp/https-githubcom-ruixingshi-deepseek-thinker-mcp) |
| [xiaozhi-autoglm-mcp](https://github.com/xinnan-tech/xiaozhi-autoglm-mcp) | AI를 통한 Android 기기 자동화 및 모바일 에이전트 제어를 위한 MCP 서버... | 92 ✅ | 64 | [View](https://agentseal.org/mcp/https-githubcom-xinnan-tech-xiaozhi-autoglm-mcp) |
| [mcp-miro](https://github.com/k-jarzyna/mcp-miro) | Model Context Protocol을 위한 Miro 통합 | 84 ✅ | 62 | [View](https://agentseal.org/mcp/https-githubcom-k-jarzyna-mcp-miro) |
| [mcp-server-atlassian-jira](https://github.com/aashari/mcp-server-atlassian-jira) | Atlassian Jira용 Node.js/TypeScript MCP 서버. AI 시스템(LLM)에 도구 제공... | 80 ⚠️ | 60 | [View](https://agentseal.org/mcp/https-githubcom-aashari-mcp-server-atlassian-jira) |
| [gdb-mcp](https://github.com/smadi0x86/gdb-mcp) | GDB 및 LLDB용 디버깅 기능을 제공하는 멀티 디버거 MCP 서버... | 86 ✅ | 56 | [View](https://agentseal.org/mcp/https-githubcom-smadi0x86-gdb-mcp) |
| [whois-mcp](https://github.com/bharathvaj-ganesan/whois-mcp) | WHOIS 조회를 위한 MCP 서버. | 92 ✅ | 52 | [View](https://agentseal.org/mcp/https-githubcom-bharathvaj-ganesan-whois-mcp) |
| [webpage-screenshot-mcp](https://github.com/ananddtyagi/webpage-screenshot-mcp) | Puppeteer를 사용하여 웹페이지 스크린샷을 캡처하는 MCP 서버... | 87 ✅ | 52 | [View](https://agentseal.org/mcp/https-githubcom-ananddtyagi-webpage-screenshot-mcp) |
| [iphone-mcp](https://github.com/blitzdotdev/iphone-mcp) | AI가 iPhone을 사용할 수 있게 하는 MCP 서버 | 86 ✅ | 50 | [View](https://agentseal.org/mcp/blitzdev-iphone-mcp) |
| [random-number-mcp](https://github.com/zazencodes/random-number-mcp) | LLM에 필수적인 난수 생성 기능을 제공하는 프로덕션 레디 MCP 서버... | 90 ✅ | 47 | [View](https://agentseal.org/mcp/https-githubcom-zazencodes-random-number-mcp) |
| [shadowgit-mcp](https://github.com/blade47/shadowgit-mcp) | AI 어시스턴트에게 안전한 Git 작업을 제공하는 MCP 서버... | 85 ✅ | 46 | [View](https://agentseal.org/mcp/https-githubcom-blade47-shadowgit-mcp) |
| [xray](https://github.com/srijanshukla18/xray) | XRAY MCP는 코딩 에이전트를 위한 점진적 코드 인텔리전스 및 탐색 기능 제공... | 82 ✅ | 46 | [View](https://agentseal.org/mcp/https-githubcom-srijanshukla18-xray) |
| [frida-game-hacking-mcp](https://github.com/0xhackerfren/frida-game-hacking-mcp) | Cheat Engine 기능을 에뮬레이션하는 Frida MCP 구현... | 71 ⚠️ | 46 | [View](https://agentseal.org/mcp/https-githubcom-0xhackerfren-frida-game-hacking-mcp) |
| [mcp_weather_server](https://github.com/isdaniel/mcp_weather_server) | 현재 및 예보 날씨, 대기질 데이터를 제공하는 읽기 전용 MCP 서버... | 100 ✅ | 44 | [View](https://agentseal.org/mcp/https-githubcom-isdaniel-mcpweatherserver) |
| [mcp-server-taskwarrior](https://github.com/awwaiid/mcp-server-taskwarrior) | 에이전트가 작업을 나열, 추가, 완료할 수 있게 하는 Taskwarrior MCP 서버... | 91 ✅ | 44 | [View](https://agentseal.org/mcp/https-githubcom-awwaiid-mcp-server-taskwarrior) |
| [mobile-dev-mcp-server](https://github.com/jsuarezruiz/mobile-dev-mcp-server) | 모바일 기기 및 시뮬레이터를 관리하고 상호작용하기 위한 MCP... | 83 ✅ | 42 | [View](https://agentseal.org/mcp/https-githubcom-jsuarezruiz-mobile-dev-mcp-server) |
| [powertools-mcp](https://github.com/aws-powertools/powertools-mcp) | Powertools for AWS 공식 MCP 서버 | 88 ✅ | 41 | [View](https://agentseal.org/mcp/https-githubcom-aws-powertools-powertools-mcp) |
| [dynamic-shell-server](https://github.com/codelion/dynamic-shell-server) | 동적 셸 명령 MCP 서버 | 86 ✅ | 41 | [View](https://agentseal.org/mcp/https-githubcom-codelion-dynamic-shell-server) |
| [unreal-api-mcp](https://github.com/Codeturion/unreal-api-mcp) | 에이전트가 Unreal Engine API 문서를 검색할 수 있는 읽기 전용 참조 서버... | 93 ✅ | 40 | [View](https://agentseal.org/mcp/https-githubcom-codeturion-unreal-api-mcp) |
| [test-coverage-mcp](https://github.com/goldbergyoni/test-coverage-mcp) | 컨텍스트 엔지니어링: 에이전트가 🧪 테스트 커버리지에 미치는 영향을 인지하게... | 89 ✅ | 40 | [View](https://agentseal.org/mcp/https-githubcom-goldbergyoni-test-coverage-mcp) |
| [mcp-tasks](https://github.com/flesler/mcp-tasks) | 멀티 포맷을 지원하는 포괄적이고 효율적인 작업 관리 MCP 서버... | 91 ✅ | 39 | [View](https://agentseal.org/mcp/https-githubcom-flesler-mcp-tasks) |
| [anki-mcp](https://github.com/nietus/anki-mcp) | 플래시카드 생성, 업데이트, 복습이 가능한 Anki 플래시카드 관리 서버... | 75 ⚠️ | 39 | [View](https://agentseal.org/mcp/https-githubcom-nietus-anki-mcp) |
| [mcp](https://github.com/screenshotone/mcp) | ScreenshotOne API를 위한 간단한 MCP 서버 구현 | 88 ✅ | 35 | [View](https://agentseal.org/mcp/https-githubcom-screenshotone-mcp) |
| [package-registry-mcp](https://github.com/artmann/package-registry-mcp) | NPM, Cargo 등의 최신 패키지 정보를 검색하고 가져오는 MCP 서버... | 86 ✅ | 35 | [View](https://agentseal.org/mcp/package-registry-mcp) |
| [kilntainers](https://github.com/kiln-ai/kilntainers) | 모든 에이전트에게 셸 명령 실행을 위한 임시 Linux 샌드박스를 제공하는 MCP 서버... | 85 ✅ | 34 | [View](https://agentseal.org/mcp/https-githubcom-kiln-ai-kilntainers) |
| [actor-critic-thinking-mcp](https://github.com/aquarius-wing/actor-critic-thinking-mcp) | MCP 기반 이중 관점 사고 분석 서버... | 100 ✅ | 32 | [View](https://agentseal.org/mcp/https-githubcom-aquarius-wing-actor-critic-thinking-mcp) |
| [maven-mcp-server](https://github.com/Bigsy/maven-mcp-server) | Maven 아티팩트의 최신 버전을 확인하는 도구를 제공하는 MCP 서버... | 92 ✅ | 31 | [View](https://agentseal.org/mcp/https-githubcom-bigsy-maven-mcp-server) |
| [PiloTY](https://github.com/yiwenlu66/PiloTY) | PiloTY: MCP를 통한 PTY 작업의 AI 파일럿 - AI 에이전트가 대화형 터미널을 제어... | 74 ⚠️ | 30 | [View](https://agentseal.org/mcp/https-githubcom-yiwenlu66-piloty) |
| [splunk-mcp-server2](https://github.com/splunk/splunk-mcp-server2) | 비공식. Python 및 TypeScript/JS로 구현된 Splunk MCP 서버... | 86 ✅ | 29 | [View](https://agentseal.org/mcp/https-githubcom-splunk-splunk-mcp-server2) |
| [mcpcap](https://github.com/mcpcap/mcpcap) | 전문 네트워크 패킷 캡처 분석을 위한 모듈형 Python MCP 서버... | 75 ⚠️ | 28 | [View](https://agentseal.org/mcp/https-githubcom-mcpcap-mcpcap) |
| [mcp-simple-timeserver](https://github.com/andybrandt/mcp-simple-timeserver) | 로컬 시간, NTP를 통한 UTC, 시간대 변환을 제공하는 시간 유틸리티 MCP 서버... | 92 ✅ | 27 | [View](https://agentseal.org/mcp/https-githubcom-andybrandt-mcp-simple-timeserver) |
| [gemini-cli-orchestrator](https://github.com/dnnyngyen/gemini-cli-orchestrator) | Claude Code가 분석을 위해 Gemini를 오케스트레이션할 수 있는 MCP 서버... | 91 ✅ | 25 | [View](https://agentseal.org/mcp/https-githubcom-dnnyngyen-gemini-cli-orchestrator) |
| [ScreenshotMCP](https://github.com/upnorthmedia/ScreenshotMCP) | 웹사이트 스크린샷 캡처를 위한 Model Context Protocol MCP 서버... | 88 ✅ | 25 | [View](https://agentseal.org/mcp/https-githubcom-upnorthmedia-screenshotmcp) |
| [mcp-task-orchestrator](https://github.com/EchoingVesper/mcp-task-orchestrator) | 작업 오케스트레이션 기능을 제공하는 Model Context Protocol 서버... | 88 ✅ | 24 | [View](https://agentseal.org/mcp/https-githubcom-echoingvesper-mcp-task-orchestrator) |
| [code-memory](https://github.com/kapillamba4/code-memory) | 벡터 임베딩을 사용한 로컬 시맨틱 코드 검색. 텔레메트리 없음... | 72 ⚠️ | 24 | [View](https://agentseal.org/mcp/https-githubcom-kapillamba4-code-memory) |
| [anti-bullshit-mcp-server](https://github.com/bmorphism/anti-bullshit-mcp-server) | 주장 분석, 출처 검증, 조작 감지를 위한 MCP 서버... | 92 ✅ | 23 | [View](https://agentseal.org/mcp/https-githubcom-bmorphism-anti-bullshit-mcp-server) |
| [blowback-context](https://github.com/esnark/blowback) | AI 도구와 통합되는 프론트엔드 개발 환경용 MCP 서버... | 87 ✅ | 22 | [View](https://agentseal.org/mcp/blowback-context) |
| [create-mcp-ts](https://github.com/stephencme/create-mcp-ts) | TypeScript로 새 MCP 서버를 생성, 배터리 포함. | 91 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-stephencme-create-mcp-ts) |
| [mcpretentious](https://github.com/oetiker/mcpretentious) | iTerm2 터미널을 조종하는 강력한 MCP 서버. | 88 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-oetiker-mcpretentious) |
| [securitycopilotmcpserver](https://github.com/jguimera/securitycopilotmcpserver) | Security Copilot, Sentinel 및 기타 도구와 통합되는 MCP 서버... | 82 ✅ | 20 | [View](https://agentseal.org/mcp/https-githubcom-jguimera-securitycopilotmcpserver) |
| [termlink](https://github.com/chu2bard/termlink) | 셸 및 터미널 작업을 위한 MCP 서버 | 91 ✅ | 19 | [View](https://agentseal.org/mcp/https-githubcom-chu2bard-termlink) |
| [hyperbolic-mcp](https://github.com/HyperbolicLabs/hyperbolic-mcp) | Claude가 Hyperbolic의 GPU 클라우드와 상호작용할 수 있는 MCP 서버... | 86 ✅ | 19 | [View](https://agentseal.org/mcp/https-githubcom-hyperboliclabs-hyperbolic-mcp) |
| [anki-connect-mcp](https://github.com/spacholski1225/anki-connect-mcp) | Anki Web을 위한 사용자 정의 MCP 구현으로, 원활한 통합 지원... | 80 ⚠️ | 18 | [View](https://agentseal.org/mcp/https-githubcom-spacholski1225-anki-connect-mcp) |
| [alertmanager-mcp-server](https://github.com/ntk148v/alertmanager-mcp-server) | AI 어시스턴트가 Alertmanager와 통합할 수 있게 하는 MCP 서버... | 87 ✅ | 16 | [View](https://agentseal.org/mcp/https-githubcom-ntk148v-alertmanager-mcp-server) |
| [mcp_server_pcileech](https://github.com/evan7198/mcp_server_pcileech) | pcileech를 사용하여 다른 PC의 메모리를 읽거나 쓰는 간단한 MCP 서버 | 85 ✅ | 16 | [View](https://agentseal.org/mcp/https-githubcom-evan7198-mcpserverpcileech) |
| [Autogen_MCP](https://github.com/DynamicEndpoints/Autogen_MCP) | Microsoft AutoGen 에이전트를 생성, 구성, 실행할 수 있는 MCP 서버... | 76 ⚠️ | 16 | [View](https://agentseal.org/mcp/https-githubcom-dynamicendpoints-autogenmcp) |
| [npm-search-mcp-server](https://github.com/btwiuse/npm-search-mcp-server) | npm 패키지 검색을 위한 MCP 서버 | 92 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-btwiuse-npm-search-mcp-server) |
| [android-mcp-server](https://github.com/jiantao88/android-mcp-server) | Android MCP 서버 구현 | 87 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-jiantao88-android-mcp-server) |
| [networksdb-mcp](https://github.com/mordavid/networksdb-mcp) | NetworksDB API와의 빠른 MCP 통합 - IP 주소, 조직 등을 조회... | 86 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-mordavid-networksdb-mcp) |
| [context-crystallizer](https://github.com/hubertciebiada/context-crystallizer) | 대규모 저장소를 AI가 소비할 수 있는 지식 베이스로 변환... | 82 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-hubertciebiada-context-crystallizer) |
| [agentops-mcp](https://github.com/AgentOps-AI/agentops-mcp) | API 키를 통해 인증하여 AgentOps 에이전트 텔레메트리를 쿼리하는 MCP 서버... | 96 ✅ | 14 | [View](https://agentseal.org/mcp/https-githubcom-agentops-ai-agentops-mcp) |
| [argus-mcp](https://github.com/lokafinnsw/argus-mcp) | 제로 트러스트 접근 방식의 AI 코드 리뷰 MCP 서버. 멀티 모델 지원, 캐싱... | 92 ✅ | 14 | [View](https://agentseal.org/mcp/https-githubcom-lokafinnsw-argus-mcp) |
| [mcp-time](https://github.com/TheoBrigitte/mcp-time) | 시간 관련 유틸리티를 제공하는 MCP 서버... | 89 ✅ | 14 | [View](https://agentseal.org/mcp/theofoobar-mcp-time) |
| [currents-mcp](https://github.com/currents-dev/currents-mcp) | Currents MCP 서버 | 84 ✅ | 14 | [View](https://agentseal.org/mcp/https-githubcom-currents-dev-currents-mcp) |
| [domain-tools-mcp-server](https://github.com/deshabhishek007/domain-tools-mcp-server) | 종합 도메인 분석을 위한 MCP 서버: WHOIS... | 92 ✅ | 13 | [View](https://agentseal.org/mcp/https-githubcom-deshabhishek007-domain-tools-mcp-server) |
| [riza-mcp](https://github.com/riza-io/riza-mcp) | Riza API를 통한 LLM 생성 코드의 격리된 코드 인터프리터... | 91 ✅ | 13 | [View](https://agentseal.org/mcp/https-githubcom-riza-io-riza-mcp) |
| [qrcode_mcp](https://github.com/2niuhe/qrcode_mcp) | QR코드를 생성하는 MCP 도구 | 91 ✅ | 12 | [View](https://agentseal.org/mcp/https-githubcom-2niuhe-qrcodemcp) |
| [d.i.e-mcp](https://github.com/lazy-importer/d.i.e-mcp) | DIE (Detect It Easy)를 위한 MCP 서버 | 92 ✅ | 11 | [View](https://agentseal.org/mcp/https-githubcom-lazy-importer-die-mcp) |
| [mcp-go-debugger](https://github.com/sunfmin/mcp-go-debugger) | MCP와 통합된 Go 디버거로, 실행, 연결, 중단점 설정이 가능... | 88 ✅ | 11 | [View](https://agentseal.org/mcp/https-githubcom-sunfmin-mcp-go-debugger) |
| [teamcity-mcp](https://github.com/itcaat/teamcity-mcp) | TeamCity MCP 서버 | 86 ✅ | 11 | [View](https://agentseal.org/mcp/https-githubcom-itcaat-teamcity-mcp) |
| [kylas-crm-mcp-server](https://github.com/kylastech/kylas-crm-mcp-server) | 리드 생성, 업데이트, 검색을 지원하는 Kylas CRM 통합 서버... | 67 ⚠️ | 11 | [View](https://agentseal.org/mcp/https-githubcom-kylastech-kylas-crm-mcp-server) |
| [memory-mcp](https://github.com/chenxiaofie/memory-mcp) | 메시지를 캐싱하고 작업 에피소드를 관리하는 로컬 대화 메모리 시스템... | 91 ✅ | 10 | [View](https://agentseal.org/mcp/https-githubcom-chenxiaofie-memory-mcp) |
| [mcp-gitlab-jira](https://github.com/HainanZhao/mcp-gitlab-jira) | GitLab 및 Jira 통합을 위한 MCP 서버로, AI 에이전트가 상호작용할 수 있게... | 92 ✅ | 9 | [View](https://agentseal.org/mcp/mcp-gitlab-jira) |
| [pyxel-mcp](https://github.com/kitao/pyxel-mcp) | Pyxel 레트로 게임 스크립트를 실행하고 시각/오디오 정보를 제공하는 MCP 서버... | 79 ⚠️ | 9 | [View](https://agentseal.org/mcp/https-githubcom-kitao-pyxel-mcp) |
| [mcp-agentic-framework](https://github.com/Piotr1215/mcp-agentic-framework) | AI 에이전트가 등록, 탐색할 수 있는 멀티 에이전트 조율 프레임워크... | 78 ⚠️ | 9 | [View](https://agentseal.org/mcp/https-githubcom-piotr1215-mcp-agentic-framework) |
| [canvas-lms-mcp](https://github.com/ahnopologetic/canvas-lms-mcp) | AI 시스템과 Canvas LMS를 연결하여 교육 데이터에 접근하는 MCP 서버... | 89 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-ahnopologetic-canvas-lms-mcp) |
| [mcp-project-manager](https://github.com/croffasia/mcp-project-manager) | 🚀 MCP를 통한 계층적 작업 관리 서버. 작업 생성... | 88 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-croffasia-mcp-project-manager) |
| [mcp-server-adb](https://github.com/watabee/mcp-server-adb) | Android Debug Bridge(ADB)용 MCP 서버로, Claude가 Android 기기와 상호작용 가능... | 87 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-watabee-mcp-server-adb) |
| [piston-mcp](https://github.com/alvii147/piston-mcp) | Piston 런타임을 사용하여 여러 프로그래밍 언어로 임의 코드를 실행... | 84 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-alvii147-piston-mcp) |
| [sonatype-mcp](https://github.com/brianveltman/sonatype-mcp) | Sonatype Nexus Repository Manager용 MCP 서버 | 84 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-brianveltman-sonatype-mcp) |
| [skill-ninja-mcp-server](https://github.com/aktsmm/skill-ninja-mcp-server) | SKILL.md 파일을 검색, 설치, 관리하는 에이전트 스킬 패키지 관리자... | 76 ⚠️ | 7 | [View](https://agentseal.org/mcp/https-githubcom-aktsmm-skill-ninja-mcp-server) |
| [mcp-idb](https://github.com/noahlozevski/mcp-idb) | fb-idb 브리지용 MCP 서버. | 86 ✅ | 6 | [View](https://agentseal.org/mcp/noahlozevski-mcp-idb) |
| [spm-mcp](https://github.com/simpleswift/spm-mcp) | Swift로 작성된 Swift Package Manager MCP 서버 | 85 ✅ | 6 | [View](https://agentseal.org/mcp/simpleswift-spm-mcp) |
| [public-apis-mcp](https://github.com/zazencodes/public-apis-mcp) | MCP를 사용하여 무료 API를 검색 | 85 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-zazencodes-public-apis-mcp) |
| [reexpress_mcp_server](https://github.com/ReexpressAI/reexpress_mcp_server) | Reexpress Model-Context-Protocol (MCP) 서버 | 82 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-reexpressai-reexpressmcpserver) |
| [mcpgex](https://github.com/patzedi/mcpgex) | 정규식 패턴 찾기, 테스트, 개선을 위한 MCP 서버 | 92 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-patzedi-mcpgex) |
| [mcp-sandbox](https://github.com/danstarns/mcp-sandbox) | 모든 JavaScript 모듈을 자동 리플렉션으로 샌드박스된 MCP 서버로 변환... | 92 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-danstarns-mcp-sandbox) |
| [mcp-grep](https://github.com/247arjun/mcp-grep) | grep CLI 도구를 감싸는 MCP 서버 래퍼 | 87 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-247arjun-mcp-grep) |
| [log-analyzer-mcp](https://github.com/Fato07/log-analyzer-mcp) | 다양한 형식의 로그 파일을 파싱, 검색, 디버깅하는 MCP 서버... | 81 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-fato07-log-analyzer-mcp) |
| [time-mcp-pypi.git](https://github.com/domdomegg/time-mcp-pypi.git) | 현재 UTC 날짜와 시간을 가져오는 도구를 제공하는 최소 Python MCP 서버... | 92 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-domdomegg-time-mcp-pypigit) |
| [sonarcloud-mcp](https://github.com/dozzman/sonarcloud-mcp) | 이슈를 가져오는 SonarCloud/SonarQube Cloud MCP 서버 | 92 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-dozzman-sonarcloud-mcp) |
| [aria-validate-mcp-server](https://github.com/yamanoku/aria-validate-mcp-server) | ARIA (접근 가능한 리치 인터넷 애플리케이션) 검증을 위한 MCP 서버... | 92 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-yamanoku-aria-validate-mcp-server) |
| [node-code-sandbox-mcp](https://github.com/mozicim/node-code-sandbox-mcp) | 🐢🚀 Node.js 샌드박스 MCP 서버 - MCP를 구현하는 Node.js 서버... | 77 ⚠️ | 4 | [View](https://agentseal.org/mcp/node-code-sandbox-mcp) |
| [conan-mcp](https://github.com/conan-io/conan-mcp) | Conan 패키지 관리자용 MCP 서버로, 프로젝트 생성을 지원... | 77 ⚠️ | 4 | [View](https://agentseal.org/mcp/https-githubcom-conan-io-conan-mcp) |
| [mcp-refactoring.git](https://github.com/marshally/mcp-refactoring.git) | Fowler 스타일 코드 리팩토링을 나열, 미리보기, 적용하는 MCP 서버... | 92 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-marshally-mcp-refactoringgit) |
| [mcp-postman](https://github.com/freebeiro/mcp-postman) | Cloudflare Workers로 구축된 MCP 서버로 통합을 지원... | 92 ✅ | 3 | [View](https://agentseal.org/mcp/mcp-postman) |
| [context-rot-detection](https://github.com/milos-product-maker/context-rot-detection) | AI 에이전트에게 인지 건강에 대한 실시간 가시성을 제공하는 MCP 서비스... | 92 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-milos-product-maker-context-rot-detection) |
| [cfr_mcp_server](https://github.com/mr-xn/cfr_mcp_server) | cfr.jar 디컴파일 기능을 래핑하고 SSR을 지원하는 Python 기반 MCP 서버 구현... | 92 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-mr-xn-cfrmcpserver) |
| [krs-poland-mcp-server](https://github.com/pkolawa/krs-poland-mcp-server) | 폴란드 KRS 공개 API를 위한 MCP 서버. | 92 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-pkolawa-krs-poland-mcp-server) |
| [mcp-ghidra5-windows](https://github.com/thestingr/mcp-ghidra5-windows) | 🏢 GPT-5 기반 Ghidra 역공학을 위한 엔터프라이즈 Windows 서비스... | 92 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-thestingr-mcp-ghidra5-windows) |
| [math-mcp-learning-server](https://github.com/clouatre-labs/math-mcp-learning-server) | 산술, 행렬 대수 등 17개 수학 도구를 갖춘 교육용 MCP 서버... | 84 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-clouatre-labs-math-mcp-learning-server) |
| [mcp-relay](https://github.com/mhcoen/mcp-relay) | Claude Desktop과 Claude Code가 불투명 메시지를 전달할 수 있는 메시지 릴레이 버퍼... | 79 ⚠️ | 3 | [View](https://agentseal.org/mcp/https-githubcom-mhcoen-mcp-relay) |
| [snowfakery-mcp](https://github.com/composable-delivery/snowfakery-mcp) | 현실적인 가짜 데이터를 생성하는 도구 Snowfakery를 래핑하는 MCP 서버... | 76 ⚠️ | 3 | [View](https://agentseal.org/mcp/https-githubcom-composable-delivery-snowfakery-mcp) |
| [memory-mcp](https://github.com/michael-denyer/memory-mcp) | 즉각적인 회상을 위한 핫 캐시를 갖춘 AI 어시스턴트용 영구 메모리 시스템... | 71 ⚠️ | 3 | [View](https://agentseal.org/mcp/https-githubcom-michael-denyer-memory-mcp) |
| [selenium-selfhealing-mcp](https://github.com/aiqualitylab/selenium-selfhealing-mcp) | UI 변경 시 깨진 Selenium 테스트 로케이터를 자동 수정하는 MCP 서버... | 92 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-aiqualitylab-selenium-selfhealing-mcp) |
| [mcp-agile-luminary](https://github.com/AgileLuminary/mcp-agile-luminary) | Agile Luminary 프로젝트 관리 앱과 연결하기 위한 MCP 서버 | 92 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-agileluminary-mcp-agile-luminary) |
| [frida-mcp](https://github.com/rmorgans/frida-mcp) | AI 시스템이 동적으로 계측하고 분석할 수 있게 하는 Frida용 MCP 서버... | 91 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-rmorgans-frida-mcp) |
| [clix-mcp-server](https://github.com/clix-so/clix-mcp-server) | AI 에이전트가 실시간, 신뢰할 수 있는 Clix 문서를 제공할 수 있게 하는 MCP 서버... | 89 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-clix-so-clix-mcp-server) |
| [mcp-page-capture](https://github.com/chasesaurabh/mcp-page-capture) | 웹 페이지 스크린샷을 캡처하고 자동화를 위한 MCP 호환 메타데이터를 반환... | 88 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-chasesaurabh-mcp-page-capture) |
| [ctfd-mcp-server](https://github.com/mrjamescot/ctfd-mcp-server) | AI 에이전트를 CTFd 인스턴스와 연결하는 MCP 구성. | 88 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-mrjamescot-ctfd-mcp-server) |
| [coderide-mcp](https://github.com/PixdataOrg/coderide-mcp) | AI 코딩 에이전트를 위한 프로젝트 및 작업 관리 MCP 서버... | 85 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-pixdataorg-coderide-mcp) |
| [github-projects-mcp](https://github.com/redducklabs/github-projects-mcp) | GitHub GraphQL API를 래핑하는 GitHub Projects v2 관리 서버... | 82 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-redducklabs-github-projects-mcp) |
| [tools](https://github.com/the-basilisk-ai/squad-mcp) | Claude와 통합되는 AI 기반 제품 발견 및 전략 플랫폼... | 81 ✅ | 2 | [View](https://agentseal.org/mcp/squadai-tools) |
| [xctools-mcp-server](https://github.com/nzrsky/xctools-mcp-server) | 다양한 Xcode 관련 도구를 위한 Model Context Protocol 서버 | 81 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-nzrsky-xctools-mcp-server) |
| [terminal-mcp](https://github.com/mkpvishnu/terminal-mcp) | 대화형 터미널 세션을 위한 MCP 서버: SSH, REPL, 데이터베이스 CLI 등... | 81 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-mkpvishnu-terminal-mcp) |
| [agentic-store-mcp](https://github.com/agenticstore/agentic-store-mcp) | AgenticStore의 무료 오픈소스 MCP 도구로 AI 에이전트에 슈퍼파워를 부여... | 75 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-agenticstore-agentic-store-mcp) |
| [physbound](https://github.com/JonesRobM/physbound) | 링크 버짓, 섀넌-하틀리 용량을 계산하는 RF/물리 검증 MCP 서버... | 100 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-jonesrobm-physbound) |
| [char-index-mcp](https://github.com/agent-hanju/char-index-mcp) | 찾기, 분할, 삽입을 제공하는 순수 문자열/문자 인덱스 조작 라이브러리... | 97 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-agent-hanju-char-index-mcp) |
| [M365-roadmap-mcp-server](https://github.com/jonnybottles/M365-roadmap-mcp-server) | AI 에이전트가 Microsoft 365 로드맵을 프로그래밍 방식으로 쿼리할 수 있는 Python MCP 서버... | 87 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-jonnybottles-m365-roadmap-mcp-server) |
| [meta-prompt-mcp](https://github.com/kapillamba4/meta-prompt-mcp) | Google 및 Anthropic의 공식 프롬프팅 가이드를 검색하는 참조 서버... | 84 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-kapillamba4-meta-prompt-mcp) |
| [mcp-autogen-doc](https://github.com/sykuang/mcp-autogen-doc) | AI 어시스턴트에게 문서 자동 생성 기능을 제공하는 MCP 서버... | 84 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-sykuang-mcp-autogen-doc) |
| [nativ-mcp](https://github.com/Nativ-Technologies/nativ-mcp) | 브랜드 가이드를 존중하면서 콘텐츠를 번역하는 AI 기반 현지화 MCP 서버... | 84 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-nativ-technologies-nativ-mcp) |
| [simctl-mcp-server](https://github.com/nzrsky/simctl-mcp-server) | iOS simctl MCP 서버 | 79 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-nzrsky-simctl-mcp-server) |
| [cowork-history](https://github.com/egoughnour/cowork-history) | Claude 대화 기록을 인덱싱하고 검색하는 로컬 MCP 서버... | 76 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-egoughnour-cowork-history) |
| [dbgprobe-mcp-server.git](https://github.com/es617/dbgprobe-mcp-server.git) | 하드웨어 디버그 프로브를 통한 AI 지원 임베디드 시스템 디버깅 MCP 서버... | 75 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-es617-dbgprobe-mcp-servergit) |
| [algora-mcp-server](https://github.com/idapixl/algora-mcp-server) | 오픈소스 현상금 및 통계를 탐색, 검색, 검색하는 읽기 전용 MCP 서버... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-idapixl-algora-mcp-server) |
| [heatpump-mcp-server](https://github.com/jiweiqi/heatpump-mcp-server) | 사용자가 히트펌프 시스템의 크기를 정하고 비교하고 평가할 수 있는 MCP 서버... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-jiweiqi-heatpump-mcp-server) |
| [fabric-mcp-server](https://github.com/adapoet/fabric-mcp-server) | 최적의 Fabric 패턴을 추천하는 Fabric AI 패턴 추천 서버... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-adapoet-fabric-mcp-server) |
| [time-node-mcp](https://github.com/davidan90/time-node-mcp) | 시간대 인식 날짜 및 시간 유틸리티를 제공하는 Node.js MCP 서버... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-davidan90-time-node-mcp) |
| [chrono-mcp](https://github.com/JMoak/chrono-mcp) | 현재 시간 조회 및 시간대 변환 기능을 제공하는 시간 유틸리티 MCP 서버... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-jmoak-chrono-mcp) |
| [crash-mcp](https://github.com/nikkoxgonzales/crash-mcp) | AI 에이전트가 복잡한 문제를 분해하는 데 도움이 되는 구조화된 추론 단계 추적기... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-nikkoxgonzales-crash-mcp) |
| [devops-practices](https://github.com/ai-4-devops/devops-practices) | DevOps 실습 문서와 FAQ를 제공하는 읽기 전용 지식 베이스 서버... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-ai-4-devops-devops-practices) |
| [mcp-domain-availability](https://github.com/imprvhub/mcp-domain-availability) | 단일 쿼리 도구로 도메인 이름 가용성을 확인하는 MCP 서버. | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-imprvhub-mcp-domain-availability) |
| [mcp_server_notify](https://github.com/Cactusinhand/mcp_server_notify) | 선택적 소리와 설정 가능한 타임아웃으로 시스템 데스크톱 알림을 전송. | 98 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-cactusinhand-mcpservernotify) |
| [agent-domain-service-mcp](https://github.com/gregm711/agent-domain-service-mcp) | 도메인 이름 가용성 확인, TLD 변형 탐색을 하는 MCP 서버... | 98 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-gregm711-agent-domain-service-mcp) |
| [Clojars-MCP-Server](https://github.com/Bigsy/Clojars-MCP-Server) | Clojars Maven/Clojure 패키지 레지스트리에서 의존성 버전을 조회... | 98 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-bigsy-clojars-mcp-server) |
| [zoho-crm-mcp-server](https://github.com/asklokesh/zoho-crm-mcp-server) | 리드, 연락처 등에 대한 읽기/쓰기 접근을 제공하는 Zoho CRM MCP 서버... | 98 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-asklokesh-zoho-crm-mcp-server) |
| [code-context-provider-mcp](https://github.com/AB498/code-context-provider-mcp) | 파일 트리를 포함한 로컬 프로젝트 디렉토리의 구조적 개요를 제공... | 97 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-ab498-code-context-provider-mcp) |
| [gotohuman-mcp-server](https://github.com/gotohuman/gotohuman-mcp-server) | 리뷰 양식 나열, 가져오기 등 AI-인간 리뷰 핸드오프를 촉진... | 96 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-gotohuman-gotohuman-mcp-server) |
| [guidance-lark-mcp](https://github.com/guidance-ai/guidance-lark-mcp) | llguidance/Lark 문법 검증, 배치 파스 테스트를 실행하는 MCP 서버... | 96 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-guidance-ai-guidance-lark-mcp) |
| [mcp-server-calculator](https://github.com/githejie/mcp-server-calculator) | 수학 표현식 평가를 위한 단일 도구를 노출하는 최소 MCP 서버... | 95 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-githejie-mcp-server-calculator) |
| [stella-mcp](https://github.com/bradleylab/stella-mcp) | Stella XMILE 시스템 다이내믹스 시뮬레이션을 구축하고 실행하는 MCP 서버... | 93 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-bradleylab-stella-mcp) |
| [mcp-server-r-counter](https://github.com/guanqun-yang/mcp-server-r-counter) | 입력 문자열에서 'R' 또는 'r' 문자의 수를 세는 서버. | 93 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-guanqun-yang-mcp-server-r-counter) |
| [excel-to-json-mcp](https://github.com/he-yang/excel-to-json-mcp) | 두 가지 도구를 통해 Excel(.xlsx) 파일과 CSV/탭 구분 데이터를 JSON으로 변환... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-he-yang-excel-to-json-mcp) |
| [mcp-files](https://github.com/flesler/mcp-files) | 코드 심볼 추출, 정밀 라인 편집을 제공하는 개발자 중심 MCP 서버... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-flesler-mcp-files) |
| [excalidraw-architect-mcp](https://github.com/BV-Venky/excalidraw-architect-mcp) | Excalidraw(.excalidraw) 다이어그램 파일을 생성하고 편집하는 MCP 서버... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-bv-venky-excalidraw-architect-mcp) |
| [drand-mcp-server](https://github.com/randa-mu/drand-mcp-server) | AI 앱을 위한 drand 네트워크의 검증 가능한 무작위성을 제공하는 MCP 서버... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-randa-mu-drand-mcp-server) |
| [time-mcp-server](https://github.com/lchinglen/time-mcp-server) | IANA 시간대 지원으로 시간 및 시간대 변환 기능을 제공하는 MCP 서버... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-lchinglen-time-mcp-server) |
| [mcp-enhance-prompt](https://github.com/FelixFoster/mcp-enhance-prompt) | 최소한의 사용자 입력을 풍부하고 구조화된 프롬프트로 재작성하는 MCP 서버... | 91 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-felixfoster-mcp-enhance-prompt) |
| [mcp-server-spira](https://github.com/Inflectra/mcp-server-spira) | Inflectra SpiraTeam/SpiraPlan에 대한 ALM 읽기 접근을 제공하는 MCP 서버... | 90 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-inflectra-mcp-server-spira) |
| [mcp-EDA](https://github.com/NellyW8/mcp-EDA) | Verilog 합성(Yosys), 시뮬레이션을 지원하는 EDA 도구체인 MCP 서버... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-nellyw8-mcp-eda) |
| [godot-mcp](https://github.com/Coding-Solo/godot-mcp) | 에디터 실행, 프로젝트 실행을 허용하는 Godot 게임 엔진 통합 서버... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-coding-solo-godot-mcp) |
| [bruno-mcp](https://github.com/hungthai1401/bruno-mcp) | Bruno CLI를 통해 Bruno API 컬렉션을 실행하여 HTTP API 테스트를 수행... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-hungthai1401-bruno-mcp) |
| [callout](https://github.com/fantasieleven-code/callout) | 솔로/초기 단계 빌더를 위한 AI 공동 창업자 어시스턴트... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-fantasieleven-code-callout) |
| [comet-mcp](https://github.com/hanzili/comet-mcp) | Comet/Perplexity 브라우저 인스턴스를 제어하여 에이전틱 웹 브라우징을 수행... | 85 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-hanzili-comet-mcp) |
| [mcp-google-search-console](https://github.com/crunchtools/mcp-google-search-console) | Google Search Console API를 래핑하여 검색 분석을 쿼리하는 MCP 서버... | 84 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-google-search-console) |
| [jupytercad-mcp](https://github.com/asmith26/jupytercad-mcp) | AI 기반 3D CAD 모델 생성 및 편집을 지원하는 JupyterCAD MCP 서버... | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-asmith26-jupytercad-mcp) |
| [frontend-design-loop-mcp](https://github.com/alexalexalex222/frontend-design-loop-mcp) | 프론트엔드 디자인을 생성, 평가, 최적화하는 AI 기반 자동화 도구... | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-alexalexalex222-frontend-design-loop-mcp) |
| [mcp-azure-devops](https://github.com/Vortiago/mcp-azure-devops) | Azure DevOps 작업 항목, 팀에 대한 전체 CRUD 접근을 제공하는 MCP 서버... | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-vortiago-mcp-azure-devops) |
| [mcp-server](https://github.com/lilo-property/mcp-server) | AI 에이전트를 위한 휴가 렌탈 예약 및 보호 | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-lilo-property-mcp-server) |
| [mcp-devcontainers](https://github.com/AI-QL/mcp-devcontainers) | 시작, 중지 등 VS Code devcontainer 생명주기 작업을 관리... | 82 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-ai-ql-mcp-devcontainers) |
| [postmancer](https://github.com/hijaz/postmancer) | 임의의 HTTP 요청을 보낼 수 있는 HTTP API 테스트 클라이언트(Postman 스타일)... | 80 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-hijaz-postmancer) |
| [code-screenshot-mcp](https://github.com/MoussaabBadla/code-screenshot-mcp) | 코드의 구문 강조된 스크린샷 이미지를 생성하는 MCP 서버... | 80 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-moussaabbadla-code-screenshot-mcp) |
| [mcp-internet-speed-test](https://github.com/inventer-dev/mcp-internet-speed-test) | 네트워크 성능 지표(다운로드/업로드 속도)를 측정하는 MCP 서버... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-inventer-dev-mcp-internet-speed-test) |
| [MCP](https://github.com/akshaykylas94/MCP) | 영업 리드를 생성, 검색, 필터링하는 도구를 제공하는 Kylas CRM MCP 서버... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-akshaykylas94-mcp) |
| [mathematica-mcp](https://github.com/lars20070/mathematica-mcp) | 임의의 Wolfram Language 코드를 평가하는 Mathematica/Wolfram Engine MCP 서버... | 76 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-lars20070-mathematica-mcp) |
| [gemini-bridge](https://github.com/eLyiN/gemini-bridge) | 에이전트 쿼리와 로컬 파일 콘텐츠를 전달하는 브리지 MCP 서버... | 74 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-elyin-gemini-bridge) |
| [blender-mcp](https://github.com/pranav-deshmukh/blender-mcp) | Python을 통해 3D 소프트웨어를 제어할 수 있는 Blender 자동화 서버... | 74 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-pranav-deshmukh-blender-mcp) |
| [curate-ipsum](https://github.com/egoughnour/curate-ipsum) | 단위/통합 테스트를 실행하는 변이 테스트 및 프로그램 합성 플랫폼... | 73 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-egoughnour-curate-ipsum) |
| [mcp-python-exec-sandbox](https://github.com/lu-zhengda/mcp-python-exec-sandbox) | PEP 723을 통한 자동 의존성 관리 기능이 있는 Python 코드 실행 서버... | 72 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-lu-zhengda-mcp-python-exec-sandbox) |
| [firefox-devtools-mcp](https://github.com/freema/firefox-devtools-mcp) | 탭 관리, DOM 상호작용을 제공하는 Firefox 브라우저 자동화 MCP 서버... | 70 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-freema-firefox-devtools-mcp) |
| [massive-context-mcp](https://github.com/egoughnour/massive-context-mcp) | 대규모 컨텍스트를 로드, 청킹, 필터링하는 재귀적 처리 서버... | 69 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-egoughnour-massive-context-mcp) |
| [mcp-gitlab](https://github.com/crunchtools/mcp-gitlab) | 프로젝트, 저장소에 대한 전체 API 접근을 제공하는 포괄적인 GitLab MCP 서버... | 68 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-gitlab) |

### 🔍 <a name="search--knowledge"></a>검색 및 지식

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [airweave-mcp-search](https://github.com/airweave-ai/airweave) | AI 에이전트를 위한 오픈소스 컨텍스트 검색 레이어 | 92 ✅ | 6.0k | [View](https://agentseal.org/mcp/airweave-mcp-search) |
| [exa-mcp-server](https://github.com/exa-labs/exa-mcp-server) | 웹 검색 및 웹 크롤링을 위한 Exa MCP! | 84 ✅ | 4.0k | [View](https://agentseal.org/mcp/exa-mcp-server) |
| [exa-mcp-server](https://github.com/exa-labs/exa-mcp-server) | AI 어시스턴트를 Exa의 웹 검색, 코드 검색 기능과 연결... | 84 ✅ | 4.0k | [View](https://agentseal.org/mcp/https-githubcom-exa-labs-exa-mcp-server) |
| [open-webSearch](https://github.com/Aas-ee/open-webSearch) | 무료 멀티 엔진 검색을 사용하는 WebSearchMCP (API 키 불필요)... | 74 ⚠️ | 790 | [View](https://agentseal.org/mcp/https-githubcom-aas-ee-open-websearch) |
| [howtocook-mcp](https://github.com/worryzyy/howtocook-mcp) | 프로그래머 집밥 가이드 기반 MCP 서버 | 86 ✅ | 697 | [View](https://agentseal.org/mcp/https-githubcom-worryzyy-howtocook-mcp) |
| [mcp-gsc](https://github.com/aminforou/mcp-gsc) | SEO를 위한 Claude AI 기반 Google Search Console 인사이트 | 84 ✅ | 535 | [View](https://agentseal.org/mcp/mcp-gsc) |
| [zotero-mcp](https://github.com/cookjohn/zotero-mcp) | Zotero의 플러그인 확장으로, Zotero와 AI의 통합을 지원... | 90 ✅ | 460 | [View](https://agentseal.org/mcp/https-githubcom-cookjohn-zotero-mcp) |
| [graphlit-mcp-server](https://github.com/graphlit/graphlit-mcp-server) | Graphlit 플랫폼을 위한 Model Context Protocol(MCP) 서버 | 72 ⚠️ | 372 | [View](https://agentseal.org/mcp/https-githubcom-graphlit-graphlit-mcp-server) |
| [gptr-mcp](https://github.com/assafelovic/gptr-mcp) | MCP를 통해 LLM 앱이 심층 연구를 수행할 수 있게 하는 MCP 서버... | 84 ✅ | 330 | [View](https://agentseal.org/mcp/https-githubcom-assafelovic-gptr-mcp) |
| [idea-reality-mcp](https://github.com/mnemox-ai/idea-reality-mcp) | 제품 아이디어가 이미 존재하는지 확인하는 연구 어시스턴트... | 98 ✅ | 316 | [View](https://agentseal.org/mcp/https-githubcom-mnemox-ai-idea-reality-mcp) |
| [deep-research-mcp](https://github.com/ozamatash/deep-research-mcp) | 주제에 대한 심층적이고 반복적인 연구를 수행하는 AI 기반 연구 어시스턴트... | 92 ✅ | 315 | [View](https://agentseal.org/mcp/https-githubcom-ozamatash-deep-research-mcp) |
| [memora](https://github.com/agentic-mcp-tools/memora) | CRUD, 검색 기능을 제공하는 영구 메모리 관리 서버... | 64 ⚠️ | 309 | [View](https://agentseal.org/mcp/https-githubcom-agentic-mcp-tools-memora) |
| [mcp-server-google-scholar](https://github.com/jackkuo666/google-scholar-mcp-server) | Google Scholar용 MCP 서버: 🔍 AI 어시스턴트가 학술 자료를 검색하고 접근... | 91 ✅ | 247 | [View](https://agentseal.org/mcp/mcp-server-google-scholar) |
| [mcp-trends-hub](https://github.com/baranwang/mcp-trends-hub) | MCP 프로토콜 기반 전체 네트워크 트렌드 원스톱 통합 서비스 | 92 ✅ | 228 | [View](https://agentseal.org/mcp/https-githubcom-baranwang-mcp-trends-hub) |
| [mcp-simple-arxiv](https://github.com/andybrandt/mcp-simple-arxiv) | 학술 논문의 검색, 검색, 전체 텍스트 추출을 제공하는 MCP 서버... | 84 ✅ | 185 | [View](https://agentseal.org/mcp/https-githubcom-andybrandt-mcp-simple-arxiv) |
| [meilisearch-mcp](https://github.com/meilisearch/meilisearch-mcp) | Meilisearch와 상호작용하기 위한 Model Context Protocol(MCP) 서버... | 79 ⚠️ | 178 | [View](https://agentseal.org/mcp/https-githubcom-meilisearch-meilisearch-mcp) |
| [mlit-dpf-mcp](https://github.com/mlit-data-platform/mlit-dpf-mcp) | 일본 국토교통성 데이터 플랫폼에 자연어 쿼리를 지원하는 MCP 서버... | 88 ✅ | 130 | [View](https://agentseal.org/mcp/https-githubcom-mlit-data-platform-mlit-dpf-mcp) |
| [google-news-server](https://github.com/ChanMeng666/server-google-news) | Google News용 Model Context Protocol(MCP) 서버 구현... | 92 ✅ | 113 | [View](https://agentseal.org/mcp/chanmeng666-google-news-server) |
| [lightrag-mcp](https://github.com/shemhamforash23/lightrag-mcp) | LightRAG API와 AI 도구를 연결하여 검색 보강 생성을 지원하는 MCP 서버... | 79 ⚠️ | 107 | [View](https://agentseal.org/mcp/https-githubcom-shemhamforash23-lightrag-mcp) |
| [mcp-server-perplexity](https://github.com/tanigami/mcp-server-perplexity) | Perplexity API와 통합하여 검색 기반 채팅 완성을 제공하는 MCP 서버... | 92 ✅ | 92 | [View](https://agentseal.org/mcp/https-githubcom-tanigami-mcp-server-perplexity) |
| [mcp-open-library](https://github.com/8enSmith/mcp-open-library) | Internet Archive의 Open Library API를 위한 Model Context Protocol(MCP) 서버... | 100 ✅ | 62 | [View](https://agentseal.org/mcp/https-githubcom-8ensmith-mcp-open-library) |
| [mcp-osint-server](https://github.com/himanshusanecha/mcp-osint-server) | 네트워크 정찰을 통한 OSINT 조사를 수행하는 MCP 서버... | 92 ✅ | 43 | [View](https://agentseal.org/mcp/https-githubcom-himanshusanecha-mcp-osint-server) |
| [mcp-searxng-enhanced](https://github.com/OvertliDS/mcp-searxng-enhanced) | SearXNG를 위한 향상된 MCP 서버: 카테고리 인식 웹 검색, 웹 스크래핑... | 86 ✅ | 35 | [View](https://agentseal.org/mcp/https-githubcom-overtlids-mcp-searxng-enhanced) |
| [bgg-mcp](https://github.com/kkjdaniel/bgg-mcp) | BGG MCP는 BoardGameGeek 및 다양한 보드게임 관련 데이터에 접근을 제공... | 86 ✅ | 32 | [View](https://agentseal.org/mcp/https-githubcom-kkjdaniel-bgg-mcp) |
| [open-notebook-mcp](https://github.com/Epochal-dev/open-notebook-mcp) | 노트북, 노트, 소스를 관리하는 개인 지식 관리 MCP 서버... | 67 ⚠️ | 19 | [View](https://agentseal.org/mcp/https-githubcom-epochal-dev-open-notebook-mcp) |
| [cbi-mcp-server](https://github.com/cbinsights/cbi-mcp-server) | CB Insights MCP 서버 | 98 ✅ | 11 | [View](https://agentseal.org/mcp/https-githubcom-cbinsights-cbi-mcp-server) |
| [google-pse-mcp](https://github.com/rendyfebry/google-pse-mcp) | Google 프로그래밍 가능 검색 엔진을 위한 MCP 서버... | 92 ✅ | 10 | [View](https://agentseal.org/mcp/https-githubcom-rendyfebry-google-pse-mcp) |
| [driflyte-mcp-server](https://github.com/serkan-ozal/driflyte-mcp-server) | AI 어시스턴트가 주제별 뉴스를 쿼리하고 검색할 수 있는 MCP 서버... | 81 ✅ | 9 | [View](https://agentseal.org/mcp/https-githubcom-serkan-ozal-driflyte-mcp-server) |
| [doi-mcp](https://github.com/tfscharff/doi-mcp) | AI의 인용 환각을 방지하기 위한 MCP 서버... | 86 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-tfscharff-doi-mcp) |
| [mcp_pearch](https://github.com/Pearch-ai/mcp_pearch) | 가장 정확한 인물 검색 API/MCP. 자연어 입력, 고품질 후보자 출력... | 86 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-pearch-ai-mcppearch) |
| [bgpt-mcp](https://github.com/connerlambden/bgpt-mcp) | BGPT 과학 논문 데이터베이스를 쿼리하는 단일 도구 MCP 서버... | 91 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-connerlambden-bgpt-mcp) |
| [mcp-search-server](https://github.com/KazKozDev/mcp-search-server) | 웹 검색(DuckDuckGo) 등을 제공하는 다목적 검색 및 유틸리티 MCP 서버... | 74 ⚠️ | 4 | [View](https://agentseal.org/mcp/https-githubcom-kazkozdev-mcp-search-server) |
| [shahnameh-mcp-server](https://github.com/aliafsahnoudeh/shahnameh-mcp-server) | 챕터, 구절, 벡터 검색을 제공하는 읽기 전용 MCP 서버... | 94 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-aliafsahnoudeh-shahnameh-mcp-server) |
| [Weather-MCP](https://github.com/shuowang-ai/Weather-MCP) | 彩云 기상 API로 구동되는 실시간 날씨, 대기질 모니터링 및 예보... | 91 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-shuowang-ai-weather-mcp) |
| [igdb-mcp-server](https://github.com/bielacki/igdb-mcp-server) | IGDB(Internet Game Database)에 읽기 전용 접근을 제공하는 MCP 서버... | 89 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-bielacki-igdb-mcp-server) |
| [gitlab-docs-mcp](https://github.com/nunolima/gitlab-docs-mcp) | GitLab 문서 MCP 서버 | 90 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-nunolima-gitlab-docs-mcp) |
| [generect_mcp.git](https://github.com/generect/generect_mcp.git) | Generect MCP는 B2B 영업 잠재 고객 발굴 도구를 제공: LinkedIn 리드/회사 검색... | 88 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-generect-generectmcpgit) |
| [ai-dictionary-mcp](https://github.com/donjguido/ai-dictionary-mcp) | AI 현상학 용어 사전인 Phenomenai에 접근하는 MCP 서버... | 79 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-donjguido-ai-dictionary-mcp) |
| [brlaw_mcp_server](https://github.com/pdmtt/brlaw_mcp_server) | 브라질 상급 법원 법률 판례를 검색하는 읽기 전용 MCP 서버... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-pdmtt-brlawmcpserver) |
| [lapalma24-mcp](https://github.com/La-Palma-24/lapalma24-mcp) | La Palma 휴가 렌탈 숙소를 검색하고 발견하는 MCP 서버... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-la-palma-24-lapalma24-mcp) |
| [mcp-claude-hackernews](https://github.com/imprvhub/mcp-claude-hackernews) | 공개 스토리와 댓글을 가져오는 읽기 전용 Hacker News 클라이언트... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-imprvhub-mcp-claude-hackernews) |
| [trinvmcp](https://github.com/cqtrinv/trinvmcp) | 이름 단편으로 프랑스 자치단체를 검색하는 읽기 전용 MCP 서버... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-cqtrinv-trinvmcp) |
| [google_maps_mcp](https://github.com/Mastan1301/google_maps_mcp) | Google Maps Places API를 쿼리하여 주변 장소를 찾는 단일 도구 MCP 서버... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-mastan1301-googlemapsmcp) |
| [mcp-server-leetcode](https://github.com/doggybee/mcp-server-leetcode) | LeetCode GraphQL API를 래핑하여 문제를 가져오는 읽기 전용 MCP 서버... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-doggybee-mcp-server-leetcode) |
| [weather-server-python](https://github.com/lxchst/weather-server-python) | 주별 미국 기상 경보와 날씨 예보를 검색하는 읽기 전용 MCP 서버... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-lxchst-weather-server-python) |
| [opendota-mcp-server](https://github.com/hkaanengin/opendota-mcp-server) | OpenDota 공개 API를 통한 Dota 2 통계를 제공하는 읽기 전용 서버... | 98 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-hkaanengin-opendota-mcp-server) |
| [bible-mcp](https://github.com/trevato/bible-mcp) | 참조 또는 무작위로 성경 구절을 검색하는 읽기 전용 MCP 서버... | 97 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-trevato-bible-mcp) |
| [mlb-api-mcp](https://github.com/guillochon/mlb-api-mcp) | MLB Stats API 및 Statcast 데이터를 노출하는 읽기 전용 MCP 서버... | 96 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-guillochon-mlb-api-mcp) |
| [kagi-ken-mcp](https://github.com/czottmann/kagi-ken-mcp) | Kagi API를 통해 웹 검색과 URL 요약을 제공하는 2도구 MCP 서버... | 95 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-czottmann-kagi-ken-mcp) |
| [reddit-insights-mcp](https://github.com/lignertys/reddit-insights-mcp) | 시맨틱 검색, 서브레딧 분석을 지원하는 읽기 전용 Reddit 인텔리전스 서버... | 94 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-lignertys-reddit-insights-mcp) |
| [mcp-server](https://github.com/DealExpress/mcp-server) | DealX/DealExpress 마켓플레이스에서 분류 광고를 검색하는 읽기 전용 MCP 서버... | 94 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-dealexpress-mcp-server) |
| [mercadolibre-mcp](https://github.com/dan1d/mercadolibre-mcp) | 제품 검색, 상세 정보 조회를 위한 읽기 전용 MercadoLibre 마켓플레이스 API 클라이언트... | 94 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-dan1d-mercadolibre-mcp) |
| [docsmcp](https://github.com/da1z/docsmcp) | 사용 가능한 문서 소스를 나열하고 콘텐츠를 검색하는 문서 검색 서버... | 90 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-da1z-docsmcp) |
| [context-awesome](https://github.com/bh-rat/context-awesome) | 큐레이션된 'awesome list' 저장소를 탐색하는 읽기 전용 검색 및 검색 서버... | 90 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-bh-rat-context-awesome) |
| [mcp-dblp](https://github.com/szeider/mcp-dblp) | DBLP 학술 출판물 데이터베이스를 검색하고 인용을 검색하는 MCP 서버... | 88 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-szeider-mcp-dblp) |
| [obris-mcp](https://github.com/obris-dev/obris-mcp) | AI 에이전트가 지식 베이스를 나열, 읽기, 생성, 업데이트할 수 있는 MCP... | 85 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-obris-dev-obris-mcp) |
| [bing-search-mcp](https://github.com/iridite/bing-search-mcp) | Claude Code를 위한 무료 Bing 검색 MCP 서버 - API 키 불필요 | 84 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-iridite-bing-search-mcp) |
| [evc-spark-mcp](https://github.com/entire-vc/evc-spark-mcp) | Spark AI 자산 마켓플레이스에 검색 및 검색을 지원하는 MCP 커넥터... | 81 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-entire-vc-evc-spark-mcp) |
| [mcp-mediawiki](https://github.com/crunchtools/mcp-mediawiki) | 검색, 읽기, 쓰기 및 관리 기능이 있는 안전한 MediaWiki MCP 서버... | 74 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-mediawiki) |

### 💻 <a name="code--ide"></a>코드 및 IDE

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [Serena](https://github.com/oraios/serena) | LLM을 코드베이스에서 직접 작업하는 코딩 에이전트로 변환... | 62 ⚠️ | 21.4k | [View](https://agentseal.org/mcp/https-githubcom-oraios-serena) |
| [ghidramcp](https://github.com/lauriewired/ghidramcp) | Ghidra용 MCP 서버 | 86 ✅ | 7.9k | [View](https://agentseal.org/mcp/https-githubcom-lauriewired-ghidramcp) |
| [@sourcebot](https://github.com/sourcebot-dev/sourcebot) | AI 기반 코드 검색을 통해 코드베이스를 이해하는 셀프 호스팅 도구... | 92 ✅ | 3.2k | [View](https://agentseal.org/mcp/sourcebot) |
| [codegraphcontext](https://github.com/shashankss1205/codegraphcontext) | 로컬 코드 저장소를 그래프로 인덱싱하는 MCP 서버 및 CLI 도구... | 81 ✅ | 2.0k | [View](https://agentseal.org/mcp/https-githubcom-shashankss1205-codegraphcontext) |
| [ref-tools-mcp](https://github.com/ref-tools/ref-tools-mcp) | 코딩 에이전트가 공개 또는 비공개 라이브러리 작업 시 실수를 방지... | 81 ✅ | 1.0k | [View](https://agentseal.org/mcp/https-githubcom-ref-tools-ref-tools-mcp) |
| [octocode-mcp](https://github.com/bgauryy/octocode-mcp) | 실시간 시맨틱 코드 연구 및 컨텍스트 생성을 위한 MCP 서버... | 77 ⚠️ | 750 | [View](https://agentseal.org/mcp/octocode-mcp) |
| [next-devtools-mcp](https://github.com/vercel/next-devtools-mcp) | 코딩 에이전트를 위한 Next.js 개발 도구 | 67 ⚠️ | 673 | [View](https://agentseal.org/mcp/https-githubcom-vercel-next-devtools-mcp) |
| [binary_ninja_mcp](https://github.com/fosdickio/binary_ninja_mcp) | 원활한 통합을 지원하는 MCP 서버가 포함된 Binary Ninja 플러그인... | 84 ✅ | 264 | [View](https://agentseal.org/mcp/https-githubcom-fosdickio-binaryninjamcp) |
| [claude-context-local](https://github.com/farhanaliraza/claude-context-local) | Claude Code용 코드 검색 MCP. 전체 코드베이스를 컨텍스트로 활용... | 84 ✅ | 200 | [View](https://agentseal.org/mcp/claude-context-local) |
| [mcp-package-version](https://github.com/sammcj/mcp-package-version) | 코드 생성 시 LLM에 최신 안정 패키지 버전을 제공하는 MCP 서버... | 86 ✅ | 121 | [View](https://agentseal.org/mcp/mcp-package-version) |
| [deep-code-reasoning-mcp](https://github.com/haasonsaas/deep-code-reasoning-mcp) | 고급 코드 분석 및 추론을 제공하는 MCP 서버... | 89 ✅ | 102 | [View](https://agentseal.org/mcp/https-githubcom-haasonsaas-deep-code-reasoning-mcp) |
| [owlex](https://github.com/agentic-mcp-tools/owlex) | 여러 AI 제공자와 세션을 생성하고 관리하는 AI 평의회 오케스트레이션 MCP... | 82 ✅ | 74 | [View](https://agentseal.org/mcp/https-githubcom-agentic-mcp-tools-owlex) |
| [ipybox](https://github.com/gradion-ai/ipybox) | 에이전트가 임의의 Python 코드를 실행할 수 있는 IPython 기반 코드 실행 샌드박스... | 71 ⚠️ | 71 | [View](https://agentseal.org/mcp/https-githubcom-gradion-ai-ipybox) |
| [codelogic-mcp-server](https://github.com/CodeLogicIncEngineering/codelogic-mcp-server) | AI 어시스턴트를 위한 Codelogic 소프트웨어 종속성 데이터를 통합하는 MCP 서버... | 90 ✅ | 35 | [View](https://agentseal.org/mcp/https-githubcom-codelogicincengineering-codelogic-mcp-server) |
| [codesurface](https://github.com/Codeturion/codesurface) | 에이전트가 API 표면을 검색, 검사, 검색할 수 있는 로컬 코드베이스 인덱서... | 92 ✅ | 19 | [View](https://agentseal.org/mcp/https-githubcom-codeturion-codesurface) |
| [local-history-mcp](https://github.com/xxczaki/local-history-mcp) | VS Code/Cursor의 로컬 히스토리에 접근하기 위한 MCP 서버 | 92 ✅ | 12 | [View](https://agentseal.org/mcp/https-githubcom-xxczaki-local-history-mcp) |
| [mcp-vscode-template](https://github.com/timsonner/mcp-vscode-template) | VS Code용 MCP 서버 템플릿 | 91 ✅ | 8 | [View](https://agentseal.org/mcp/https-githubcom-timsonner-mcp-vscode-template) |
| [jebmcp](https://github.com/pcjaat3844/jebmcp) | 클라우드 배치 작업을 관리하고 처리하는 경량 도구... | 89 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-pcjaat3844-jebmcp) |
| [judges](https://github.com/kevinrabun/judges) | 보안, 품질 등을 위해 AI 생성 코드를 평가하는 전문 심사관이 있는 MCP 서버... | 81 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-kevinrabun-judges) |
| [clj-kondo-MCP](https://github.com/Bigsy/clj-kondo-MCP) | Clojure, ClojureScript, EDN 파일용 clj-kondo 린팅을 제공하는 MCP 서버... | 89 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-bigsy-clj-kondo-mcp) |
| [jadx-daemon-mcp](https://github.com/wrlu/jadx-daemon-mcp) | jadx 데몬 서비스 MCP 서버. | 88 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-wrlu-jadx-daemon-mcp) |
| [silverstripe-mcp](https://github.com/sandervanscheepen/silverstripe-mcp) | AI 어시스턴트가 SilverStripe 코드를 생성할 때 실시간 검증 피드백을 제공하는 MCP 서버... | 83 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-sandervanscheepen-silverstripe-mcp) |
| [shadcn-registry-manager](https://github.com/reuvenaor/shadcn-registry-manager) | MCP shadcn 레지스트리 CLI 관리자 | 92 ✅ | 1 | [View](https://agentseal.org/mcp/reuvenorg-shadcn-registry-manager) |
| [impact-preview](https://github.com/agent-polis/impact-preview) | 실행 전에 AI 에이전트 동작을 미리보기 및 승인, 파일 diff 표시... | 82 ✅ | 1 | [View](https://agentseal.org/mcp/impact-preview) |
| [context7fork](https://github.com/renCosta2025/context7fork) | LLM 및 AI 코딩 도구를 위한 최신 코드 문서 및 버전별 예제... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-rencosta2025-context7fork) |
| [claudecodenavi-mcp](https://github.com/saikiyusuke/claudecodenavi-mcp) | ClaudeCodeNavi MCP 서버 - Claude Code 지식 플랫폼 및 마켓플레이스 | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-saikiyusuke-claudecodenavi-mcp) |
| [codemunch-pro](https://github.com/BigJai/codemunch-pro) | 지능형 코드 인덱싱 MCP 서버. 13개 도구, 10개 언어, 하이브리드 검색... | 72 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-bigjai-codemunch-pro) |

### ☁️ <a name="cloud--infrastructure"></a>클라우드 및 인프라

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [mcp](https://github.com/awslabs/mcp) | AWS 공식 MCP 서버 | 86 ✅ | 8.4k | [View](https://agentseal.org/mcp/https-githubcom-awslabs-mcp) |
| [mcp-grafana](https://github.com/grafana/mcp-grafana) | Grafana용 MCP 서버 | 78 ⚠️ | 2.5k | [View](https://agentseal.org/mcp/https-githubcom-grafana-mcp-grafana) |
| [mcp-server-kubernetes](https://github.com/Flux159/mcp-server-kubernetes) | Kubernetes 관리 명령을 위한 MCP 서버 | 81 ✅ | 1.3k | [View](https://agentseal.org/mcp/mcp-server-kubernetes) |
| [azure-mcp](https://github.com/azure/azure-mcp) | 에이전트에 Azure의 강력함을 제공하는 Azure MCP 서버. | 74 ⚠️ | 1.2k | [View](https://agentseal.org/mcp/https-githubcom-azure-azure-mcp) |
| [spotinfo](https://github.com/alexei-led/spotinfo) | AWS EC2 스팟 인벤토리를 탐색하는 CLI... | 92 ✅ | 158 | [View](https://agentseal.org/mcp/https-githubcom-alexei-led-spotinfo) |
| [hub-mcp](https://github.com/docker/hub-mcp) | Docker Hub 저장소, 태그, 네임스페이스에 대한 읽기/쓰기 접근을 제공... | 86 ✅ | 130 | [View](https://agentseal.org/mcp/https-githubcom-docker-hub-mcp) |
| [mcp-server-aws](https://github.com/rishikavikondala/mcp-server-aws) | AWS S3 버킷/객체 및 DynamoDB 테이블/항목에 대한 전체 CRUD 접근 제공... | 74 ⚠️ | 128 | [View](https://agentseal.org/mcp/https-githubcom-rishikavikondala-mcp-server-aws) |
| [aks-mcp](https://github.com/Azure/aks-mcp) | AI 어시스턴트가 Azure Kubernetes Service와 상호작용하는 MCP 서버... | 86 ✅ | 121 | [View](https://agentseal.org/mcp/https-githubcom-azure-aks-mcp) |
| [mcp-netbird](https://github.com/aantti/mcp-netbird) | Netbird용 MCP 서버 | 92 ✅ | 42 | [View](https://agentseal.org/mcp/https-githubcom-aantti-mcp-netbird) |
| [apisix-mcp](https://github.com/api7/apisix-mcp) | Apache APISIX API 게이트웨이 리소스(라우트 등)를 관리하는 MCP 서버... | 67 ⚠️ | 34 | [View](https://agentseal.org/mcp/https-githubcom-api7-apisix-mcp) |
| [cos-mcp](https://github.com/Tencent/cos-mcp) | MCP 프로토콜 기반 텐센트 클라우드 COS MCP 서버 | 85 ✅ | 30 | [View](https://agentseal.org/mcp/https-githubcom-tencent-cos-mcp) |
| [ig-mcp-server](https://github.com/inspektor-gadget/ig-mcp-server) | AI 인터페이스로 컨테이너 및 Kubernetes 워크로드를 디버깅 | 92 ✅ | 22 | [View](https://agentseal.org/mcp/https-githubcom-inspektor-gadget-ig-mcp-server) |
| [aws-pricing-mcp](https://github.com/trilogy-group/aws-pricing-mcp) | AWS EC2 요금 데이터를 노출하고 CPU 등으로 검색 옵션을 제공하는 MCP 서버... | 92 ✅ | 20 | [View](https://agentseal.org/mcp/https-githubcom-trilogy-group-aws-pricing-mcp) |
| [mcp-server-aws-sso](https://github.com/aashari/mcp-server-aws-sso) | AWS SSO용 Node.js/TypeScript MCP 서버. AI 시스템을 지원... | 78 ⚠️ | 12 | [View](https://agentseal.org/mcp/https-githubcom-aashari-mcp-server-aws-sso) |
| [teamcity-mcp](https://github.com/itcaat/teamcity-mcp) | TeamCity MCP 서버 | 80 ⚠️ | 11 | [View](https://agentseal.org/mcp/itcaat-teamcity-mcp) |
| [porkbun-mcp](https://github.com/major/porkbun-mcp) | DNS 레코드, 도메인 설정, DNSSEC, SSL 인증서를 관리하는 MCP 서버... | 89 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-major-porkbun-mcp) |
| [lumino-mcp-server](https://github.com/spre-sre/lumino-mcp-server) | Kubernetes 및 OpenShift의 SRE 관찰 가능성을 위한 AI 기반 진단 엔진... | 84 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-spre-sre-lumino-mcp-server) |
| [hosting-mcp](https://github.com/4everland/4everland-hosting-mcp) | AI 생성 코드를 분산 스토리지에 즉시 배포하는 MCP 서버... | 92 ✅ | 2 | [View](https://agentseal.org/mcp/4everland-hosting-mcp) |
| [azure-updates-mcp](https://github.com/jonnybottles/azure-updates-mcp) | Microsoft Azure 서비스 업데이트를 위한 읽기 전용 검색 인터페이스... | 94 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-jonnybottles-azure-updates-mcp) |
| [deploy-mcp](https://github.com/alexpota/deploy-mcp) | 배포 상태, 로그, 프로젝트 목록 모니터링을 위한 읽기 전용 MCP 서버... | 96 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-alexpota-deploy-mcp) |
| [azure-resource-graph-mcp-server](https://github.com/hardik-id/azure-resource-graph-mcp-server) | KQL을 사용하여 Azure Resource Graph를 쿼리하는 MCP 서버... | 90 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-hardik-id-azure-resource-graph-mcp-server) |
| [shipi-mcp-server](https://github.com/aarsiv-groups/shipi-mcp-server) | Shipi 플랫폼을 위한 물류 배송 MCP 서버... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-aarsiv-groups-shipi-mcp-server) |
| [cloud-run-mcp](https://github.com/GoogleCloudPlatform/cloud-run-mcp) | Cloud Run 서비스를 관리하고 배포하는 Google Cloud Platform MCP 서버... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-googlecloudplatform-cloud-run-mcp) |
| [powerbi-mcp](https://github.com/gurvinder-dhillon/powerbi-mcp) | PowerBI REST API와 상호작용하여 DAX 쿼리 및 작업 관리를 수행하는 MCP 서버... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-gurvinder-dhillon-powerbi-mcp) |
| [mycrab-mcp](https://github.com/isgudtek/mycrab-mcp) | Cloudflare Tunnel을 통해 AI 에이전트에게 공개 HTTPS URL을 제공하는 터널링 서비스... | 82 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-isgudtek-mycrab-mcp) |
| [consul-mcp-server](https://github.com/kocierik/consul-mcp-server) | 서비스 디스커버리를 제공하는 전체 기능 HashiCorp Consul 관리 서버... | 82 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-kocierik-consul-mcp-server) |
| [GooglePlayConsoleMcp](https://github.com/AgiMaulana/GooglePlayConsoleMcp) | Google Play Developer API를 래핑하여 릴리스 트랙 관리를 하는 MCP 서버... | 80 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-agimaulana-googleplayconsolemcp) |
| [mcp-cloudflare](https://github.com/crunchtools/mcp-cloudflare) | DNS 레코드, WAF 규칙, 페이지 규칙을 노출하는 Cloudflare 관리 MCP 서버... | 79 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-cloudflare) |
| [mcp-proxmox](https://github.com/antonio-mello-ai/mcp-proxmox) | VM/컨테이너의 전체 생명주기 제어를 제공하는 Proxmox VE 클러스터 관리 MCP 서버... | 72 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-antonio-mello-ai-mcp-proxmox) |
| [conductor-mcp](https://github.com/conductor-oss/conductor-mcp) | Netflix Conductor 워크플로우 오케스트레이션을 관리하는 MCP 서버... | 70 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-conductor-oss-conductor-mcp) |
| [heroku-mcp-server](https://github.com/heroku/heroku-mcp-server) | Heroku 앱, 데이터베이스, Dyno, 파이프라인을 관리하는 공식 Heroku MCP 서버... | 65 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-heroku-heroku-mcp-server) |
| [mcp](https://github.com/hopx-ai/mcp) | 코드 실행을 위한 격리된 컨테이너를 제공하는 클라우드 샌드박스 실행 플랫폼... | 58 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-hopx-ai-mcp) |

### 📝 <a name="content--media"></a>콘텐츠 및 미디어

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [blender-mcp](https://github.com/ahujasid/blender-mcp) | AI 에이전트가 Blender 장면을 제어할 수 있는 Blender 자동화 MCP 서버... | 66 ⚠️ | 17.7k | [View](https://agentseal.org/mcp/https-githubcom-ahujasid-blender-mcp) |
| [markdownify-mcp](https://github.com/zcaceres/markdownify-mcp) | 거의 모든 것을 Markdown으로 변환하는 Model Context Protocol 서버 | 83 ✅ | 2.4k | [View](https://agentseal.org/mcp/https-githubcom-zcaceres-markdownify-mcp) |
| [ableton-mcp](https://github.com/ahujasid/ableton-mcp) | Ableton Live 세션의 프로그래밍 방식 제어를 제공하는 MCP 서버... | 89 ✅ | 2.3k | [View](https://agentseal.org/mcp/https-githubcom-ahujasid-ableton-mcp) |
| [mcp](https://github.com/caol64/wenyan-mcp) | AI가 Markdown 기사를 자동 포맷하여 WeChat 공식 계정에 게시하는 MCP 서버. | 85 ✅ | 1.1k | [View](https://agentseal.org/mcp/wenyan-md-mcp) |
| [wenyan-mcp](https://github.com/caol64/wenyan-mcp) | AI가 Markdown 기사를 자동 포맷하여 WeChat 공식 계정에 게시하는 MCP 서버. | 84 ✅ | 1.1k | [View](https://agentseal.org/mcp/https-githubcom-caol64-wenyan-mcp) |
| [mcp-server-weread](https://github.com/freestylefly/mcp-server-weread) | WeChat 독서 MCP | 92 ✅ | 528 | [View](https://agentseal.org/mcp/mcp-server-weread) |
| [mcp-server-weread](https://github.com/freestylefly/mcp-server-weread) | WeChat 독서 MCP | 92 ✅ | 528 | [View](https://agentseal.org/mcp/https-githubcom-freestylefly-mcp-server-weread) |
| [adb-mcp](https://github.com/mikechambers/adb-mcp) | AI 모델이 Adobe Creative Suite 앱(Photoshop 등)을 제어하는 MCP 서버... | 89 ✅ | 504 | [View](https://agentseal.org/mcp/https-githubcom-mikechambers-adb-mcp) |
| [ebook-mcp](https://github.com/onebirdrocks/ebook-mcp) | EPUB, PDF 등 주요 전자책 형식을 지원하는 MCP 서버... | 74 ⚠️ | 351 | [View](https://agentseal.org/mcp/ebook-mcp) |
| [mcp-youtube-transcript](https://github.com/jkawamoto/mcp-youtube-transcript) | YouTube 비디오 자막(일반 및 타임스탬프)과 기본 비디오 메타데이터를 검색... | 93 ✅ | 339 | [View](https://agentseal.org/mcp/https-githubcom-jkawamoto-mcp-youtube-transcript) |
| [after-effects-mcp](https://github.com/dakkshin/after-effects-mcp) | Adobe After Effects용 MCP 서버. 원격 제어(컴포지션, 텍스트 등)를 지원... | 85 ✅ | 237 | [View](https://agentseal.org/mcp/https-githubcom-dakkshin-after-effects-mcp) |
| [mcp-summarizer](https://github.com/0xshellming/mcp-summarizer) | AI 요약을 위한 MCP 서버 | 100 ✅ | 157 | [View](https://agentseal.org/mcp/https-githubcom-0xshellming-mcp-summarizer) |
| [bilibili-mcp-js](https://github.com/34892002/bilibili-mcp-js) | Bilibili 비디오 검색 MCP 서비스 | 99 ✅ | 153 | [View](https://agentseal.org/mcp/https-githubcom-34892002-bilibili-mcp-js) |
| [powerpoint](https://github.com/supercurses/powerpoint) | PowerPoint 프레젠테이션을 만드는 MCP 서버 | 90 ✅ | 144 | [View](https://agentseal.org/mcp/https-githubcom-supercurses-powerpoint) |
| [anilist-mcp](https://github.com/yuna0x0/anilist-mcp) | 애니메이션 및 만화 데이터에 접근하는 AniList MCP 서버 | 84 ✅ | 71 | [View](https://agentseal.org/mcp/anilist-mcp) |
| [dws-mcp-server](https://github.com/pspdfkit/nutrient-dws-mcp-server) | Nutrient 문서 처리 서비스와 통합하는 MCP 서버 구현... | 87 ✅ | 63 | [View](https://agentseal.org/mcp/nutrient-sdk-dws-mcp-server) |
| [mcp-server-atlassian-confluence](https://github.com/aashari/mcp-server-atlassian-confluence) | Atlassian Confluence용 Node.js/TypeScript MCP 서버. AI 시스템에 도구 제공... | 76 ⚠️ | 50 | [View](https://agentseal.org/mcp/https-githubcom-aashari-mcp-server-atlassian-confluence) |
| [mcp-apple-notes](https://github.com/henilcalagiya/mcp-apple-notes) | AppleScript를 통해 Apple Notes에 전체 CRUD 접근을 제공하는 MCP 서버... | 81 ✅ | 40 | [View](https://agentseal.org/mcp/https-githubcom-henilcalagiya-mcp-apple-notes) |
| [mcp-server-amazon-bedrock](https://github.com/zxkane/mcp-server-amazon-bedrock) | Amazon Bedrock의 Nova Canvas 모델을 통해 이미지를 생성하는 MCP 서버... | 99 ✅ | 24 | [View](https://agentseal.org/mcp/https-githubcom-zxkane-mcp-server-amazon-bedrock) |
| [imagician](https://github.com/flowy11/imagician) | 이미지 편집을 위한 MCP 서버 | 92 ✅ | 18 | [View](https://agentseal.org/mcp/https-githubcom-flowy11-imagician) |
| [gif-creator-mcp](https://github.com/ananddtyagi/gif-creator-mcp) | FFmpeg를 사용하여 로컬 비디오 파일을 GIF로 변환하는 단일 도구 MCP 서버... | 99 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-ananddtyagi-gif-creator-mcp) |
| [mcp-florence2](https://github.com/jkawamoto/mcp-florence2) | Microsoft Florence2 비전 모델을 로컬에서 실행하여 OCR 등을 수행하는 MCP 서버... | 94 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-jkawamoto-mcp-florence2) |
| [mcp-apple-music](https://github.com/Cifero74/mcp-apple-music) | Claude에게 Apple Music 계정의 전체 접근 권한을 제공하는 MCP 서버... | 84 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-cifero74-mcp-apple-music) |
| [rss-reader-mcp](https://github.com/kwp-lab/rss-reader-mcp) | RSS 항목과 기사 콘텐츠를 가져오고 파싱하는 읽기 전용 RSS 피드 리더... | 94 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-kwp-lab-rss-reader-mcp) |
| [citedy-seo-agent](https://github.com/Citedy/citedy-seo-agent) | AI 기반 SEO 콘텐츠 자동화 에이전트 스킬 - 트렌드 스카우팅, 경쟁 분석... | 85 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-citedy-citedy-seo-agent) |
| [vap-showcase](https://github.com/vapagentmedia/vap-showcase) | 이미지, 비디오, 음악 생성을 제공하는 VAP 기반 AI 미디어 생성 플랫폼... | 84 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-vapagentmedia-vap-showcase) |
| [unsplash-mcp](https://github.com/cevatkerim/unsplash-mcp) | 적절한 저작자 표시가 내장된 Unsplash 사진 검색 MCP 서버... | 90 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-cevatkerim-unsplash-mcp) |
| [audius-mcp-atris](https://github.com/glassBead-tc/audius-mcp-atris) | Audius 탈중앙화 음악 스트리밍 플랫폼 API를 래핑하는 MCP 서버... | 60 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-glassbead-tc-audius-mcp-atris) |
| [bilibili-mcp-server](https://github.com/wangshunnn/bilibili-mcp-server) | Bilibili 공개 API를 래핑하여 사용자 정보를 검색하는 읽기 전용 MCP 서버... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-wangshunnn-bilibili-mcp-server) |
| [cookwith-mcp](https://github.com/blaideinc/cookwith-mcp) | 재료에 따라 레시피를 생성하고 변환하는 요리 어시스턴트 MCP 서버... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-blaideinc-cookwith-mcp) |
| [mcp-image-compression](https://github.com/InhiblabCore/mcp-image-compression) | URL 또는 로컬 파일 경로를 받아 이미지를 압축하는 MCP 서버... | 96 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-inhiblabcore-mcp-image-compression) |
| [spotify-bulk-actions-mcp](https://github.com/khglynn/spotify-bulk-actions-mcp) | 라이브러리, 플레이리스트 관리를 위한 Spotify 대량 작업 MCP 서버... | 94 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-khglynn-spotify-bulk-actions-mcp) |
| [PokeMCP](https://github.com/MetehanGZL/PokeMCP) | 이름으로 포켓몬 데이터를 조회하는 도구를 제공하는 포켓몬 테마 MCP 서버... | 94 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-metehangzl-pokemcp) |
| [zapcap-mcp-server](https://github.com/bogdan01m/zapcap-mcp-server) | ZapCap API와 통합하여 비디오를 업로드하고 자막 템플릿을 적용하는 서버... | 93 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-bogdan01m-zapcap-mcp-server) |
| [raindrop-io-mcp-server](https://github.com/hiromitsusasaki/raindrop-io-mcp-server) | Raindrop.io 북마크 관리를 위한 읽기/쓰기 MCP 서버... | 90 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-hiromitsusasaki-raindrop-io-mcp-server) |
| [aseprite-mcp](https://github.com/diivi/aseprite-mcp) | Aseprite 픽셀아트 편집기를 구동하여 캔버스 생성, 그리기를 하는 MCP 서버... | 88 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-diivi-aseprite-mcp) |
| [vap-showcase](https://github.com/elestirelbilinc-sketch/vap-showcase) | 이미지, 비디오, 음악 생성을 제공하는 AI 미디어 생성 플랫폼(VAP)... | 88 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-elestirelbilinc-sketch-vap-showcase) |
| [sprout-mcp](https://github.com/mepsopti/sprout-mcp) | 저가 모델(Haiku)이 콘텐츠 청크를 시드하는 모델 계층형 연구 파이프라인... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-mepsopti-sprout-mcp) |
| [mcp-ragchat](https://github.com/gogabrielordonez/mcp-ragchat) | RAG 기반 채팅 어시스턴트를 구축, 테스트, 배포할 수 있는 MCP 서버... | 81 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-gogabrielordonez-mcp-ragchat) |
| [mcp-wordpress](https://github.com/crunchtools/mcp-wordpress) | 게시물, 페이지 등의 전체 CRUD 작업을 제공하는 WordPress REST API 래퍼... | 79 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-wordpress) |
| [legends-mcp](https://github.com/cryptosquanch/legends-mcp) | 유명 기술 창업자의 AI 페르소나와 대화할 수 있는 MCP 서버... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-cryptosquanch-legends-mcp) |
| [alog-mcp](https://github.com/saikiyusuke/alog-mcp) | 에이전트가 로그를 게시할 수 있는 AI 에이전트 활동 로깅 및 블로깅 플랫폼... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-saikiyusuke-alog-mcp) |
| [cronometer-mcp](https://github.com/cphoskins/cronometer-mcp) | 사용자의 Cronometer Gold 계정에 전체 읽기/쓰기 접근을 제공하는 MCP 서버... | 77 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-cphoskins-cronometer-mcp) |
| [keep-mcp](https://github.com/feuerdev/keep-mcp) | Google Keep 노트 관리를 위한 MCP 서버, 노트 CRUD 작업 지원... | 74 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-feuerdev-keep-mcp) |
| [mcp-feed-reader](https://github.com/crunchtools/mcp-feed-reader) | 구독 관리, 콘텐츠 가져오기를 하는 RSS/Atom 피드 리더 MCP 서버... | 74 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-feed-reader) |

### 🔌 <a name="api-development"></a>API 개발

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [bifrost](https://github.com/maximhq/bifrost) | 적응형 로드 밸런싱을 갖춘 가장 빠른 엔터프라이즈 AI 게이트웨이(LiteLLM 대비 50배 빠름)... | 89 ✅ | 2.9k | [View](https://agentseal.org/mcp/https-githubcom-maximhq-bifrost) |
| [mcp-server-12306](https://github.com/drfccv/mcp-server-12306) | 중국 12306 기차표 시스템 조회를 위한 고성능 MCP 서버... | 87 ✅ | 292 | [View](https://agentseal.org/mcp/https-githubcom-drfccv-mcp-server-12306) |
| [facebook-ads-mcp-server](https://github.com/gomarble-ai/facebook-ads-mcp-server) | Meta Ads 데이터 및 관리 기능에 프로그래밍 방식 접근을 제공하는 MCP 서버... | 88 ✅ | 253 | [View](https://agentseal.org/mcp/https-githubcom-gomarble-ai-facebook-ads-mcp-server) |
| [uber-eats-mcp-server](https://github.com/ericzakariasson/uber-eats-mcp-server) | MCP를 통해 LLM 앱과 Uber Eats를 통합하는 MCP 서버... | 92 ✅ | 217 | [View](https://agentseal.org/mcp/https-githubcom-ericzakariasson-uber-eats-mcp-server) |
| [square-mcp-server](https://github.com/square/square-mcp-server) | Square를 위한 Model Context Protocol(MCP) 서버 | 92 ✅ | 95 | [View](https://agentseal.org/mcp/https-githubcom-square-square-mcp-server) |
| [nasa-mcp-server](https://github.com/programcomputer/nasa-mcp-server) | NASA API를 위한 표준화된 접근을 제공하는 MCP 서버... | 81 ✅ | 81 | [View](https://agentseal.org/mcp/https-githubcom-programcomputer-nasa-mcp-server) |
| [mcp-servers](https://github.com/allaboutai-yt/mcp-servers) | All About AI MCP 서버 | 92 ✅ | 79 | [View](https://agentseal.org/mcp/https-githubcom-allaboutai-yt-mcp-servers) |
| [mcp-difyworkflow-server](https://github.com/gotoolkits/mcp-difyworkflow-server) | MCP 프로토콜을 구현하는 Dify 워크플로우 서버 도구 앱... | 92 ✅ | 60 | [View](https://agentseal.org/mcp/https-githubcom-gotoolkits-mcp-difyworkflow-server) |
| [veyrax-mcp](https://github.com/VeyraX/veyrax-mcp) | 단일 인증으로 모든 VeyraX 통합 서비스에 접근하는 통합 MCP 서버... | 92 ✅ | 48 | [View](https://agentseal.org/mcp/https-githubcom-veyrax-veyrax-mcp) |
| [mcp-weather](https://github.com/TimLukaHorstmann/mcp-weather) | 시간별 및 일일 날씨 예보를 제공하는 MCP 서버... | 92 ✅ | 31 | [View](https://agentseal.org/mcp/https-githubcom-timlukahorstmann-mcp-weather) |
| [adobe-commerce-dev-mcp](https://github.com/rafaelstz/adobe-commerce-dev-mcp) | Adobe Commerce 개발 MCP 서버 | 94 ✅ | 24 | [View](https://agentseal.org/mcp/https-githubcom-rafaelstz-adobe-commerce-dev-mcp) |
| [text-to-graphql-mcp](https://github.com/Arize-ai/text-to-graphql-mcp) | AI 에이전트를 사용하여 자연어 쿼리를 유효한 GraphQL 쿼리로 변환... | 84 ✅ | 23 | [View](https://agentseal.org/mcp/https-githubcom-arize-ai-text-to-graphql-mcp) |
| [mcp-community](https://github.com/mirascope/mcp-community) | MCP 서버를 쉽게 실행, 배포, 연결 | 77 ⚠️ | 23 | [View](https://agentseal.org/mcp/https-githubcom-mirascope-mcp-community) |
| [calcom-mcp](https://github.com/Danielpeter-99/calcom-mcp) | Cal.com API와 상호작용하기 위한 FastMCP 서버. LLM이 일정을 관리... | 92 ✅ | 14 | [View](https://agentseal.org/mcp/https-githubcom-danielpeter-99-calcom-mcp) |
| [specmatic-mcp-server](https://github.com/specmatic/specmatic-mcp-server) | Specmatic의 계약 테스트 기능을 노출하는 MCP 서버... | 86 ✅ | 8 | [View](https://agentseal.org/mcp/https-githubcom-specmatic-specmatic-mcp-server) |
| [webhook-mcp-server](https://github.com/zebbern/webhook-mcp-server) | webhook.site를 위한 MCP 서버 - HTTP 요청을 즉시 캡처... | 76 ⚠️ | 7 | [View](https://agentseal.org/mcp/https-githubcom-zebbern-webhook-mcp-server) |
| [appfolio-mcp-server](https://github.com/CryptoCultCurt/appfolio-mcp-server) | AI 에이전트가 Appfolio 보고 API에 접근하기 위한 MCP 서버... | 92 ✅ | 6 | [View](https://agentseal.org/mcp/fluegeldao-appfolio-mcp-server) |

### 🗄️ <a name="database--sql"></a>데이터베이스 및 SQL

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [postgres-mcp](https://github.com/crystaldba/postgres-mcp) | Postgres MCP Pro는 구성 가능한 읽기/쓰기 접근 및 성능 분석을 제공... | 86 ✅ | 2.3k | [View](https://agentseal.org/mcp/https-githubcom-crystaldba-postgres-mcp) |
| [mcp-server-mysql](https://github.com/benborla/mcp-server-mysql) | MySQL 데이터베이스에 읽기 전용 접근을 제공하는 MCP 서버... | 90 ✅ | 1.3k | [View](https://agentseal.org/mcp/benborla29-mcp-server-mysql) |
| [mcp-server-qdrant](https://github.com/qdrant/mcp-server-qdrant) | Qdrant 공식 Model Context Protocol(MCP) 서버 구현 | 86 ✅ | 1.3k | [View](https://agentseal.org/mcp/https-githubcom-qdrant-mcp-server-qdrant) |
| [supabase-mcp-server](https://github.com/alexander-zuev/supabase-mcp-server) | Supabase 프로젝트 관리를 위한 전체 기능 MCP 서버: 데이터베이스 스키마... | 68 ⚠️ | 815 | [View](https://agentseal.org/mcp/https-githubcom-alexander-zuev-supabase-mcp-server) |
| [mcp-clickhouse](https://github.com/ClickHouse/mcp-clickhouse) | ClickHouse를 AI 어시스턴트에 연결합니다. | 85 ✅ | 713 | [View](https://agentseal.org/mcp/https-githubcom-clickhouse-mcp-clickhouse) |
| [yargi-mcp](https://github.com/saidsurucu/yargi-mcp) | 터키 법률 데이터베이스용 MCP 서버 | 85 ✅ | 665 | [View](https://agentseal.org/mcp/https-githubcom-saidsurucu-yargi-mcp) |
| [mcp-server-neon](https://github.com/neondatabase/mcp-server-neon) | Neon 관리 API 및 데이터베이스와 상호작용하는 MCP 서버 | 92 ✅ | 560 | [View](https://agentseal.org/mcp/https-githubcom-neondatabase-mcp-server-neon) |
| [gateway](https://github.com/centralmind/gateway) | LLM 및 AI 에이전트에 최적화된 범용 데이터베이스 MCP 서버. | 86 ✅ | 518 | [View](https://agentseal.org/mcp/https-githubcom-centralmind-gateway) |
| [mcp-database-server](https://github.com/executeautomation/mcp-database-server) | Sqlite, SqlServer 등과 연결하는 MCP 데이터베이스 서버... | 84 ✅ | 319 | [View](https://agentseal.org/mcp/https-githubcom-executeautomation-mcp-database-server) |
| [elasticsearch-mcp-server](https://github.com/cr7258/elasticsearch-mcp-server) | Elasticsearch/OpenSearch 클러스터에 전체 CRUD 접근을 제공하는 MCP 서버... | 74 ⚠️ | 256 | [View](https://agentseal.org/mcp/https-githubcom-cr7258-elasticsearch-mcp-server) |
| [mcp-server-starrocks](https://github.com/StarRocks/mcp-server-starrocks) | StarRocks MCP (Model Context Protocol) 서버 | 85 ✅ | 154 | [View](https://agentseal.org/mcp/https-githubcom-starrocks-mcp-server-starrocks) |
| [mcp-oceanbase](https://github.com/oceanbase/mcp-oceanbase) | OceanBase 데이터베이스 에코시스템을 위한 MCP 서버 컬렉션... | 76 ⚠️ | 98 | [View](https://agentseal.org/mcp/https-githubcom-oceanbase-mcp-oceanbase) |
| [mcp-trino](https://github.com/tuannvm/mcp-trino) | Go로 구현된 Trino용 고성능 MCP 서버... | 78 ⚠️ | 96 | [View](https://agentseal.org/mcp/https-githubcom-tuannvm-mcp-trino) |
| [teradata-mcp-server](https://github.com/Teradata/teradata-mcp-server) | Teradata 데이터베이스용 커뮤니티 개발 MCP 서버 | 82 ✅ | 41 | [View](https://agentseal.org/mcp/https-githubcom-teradata-teradata-mcp-server) |
| [iotdb-mcp-server](https://github.com/apache/iotdb-mcp-server) | Apache IoTDB 시계열 데이터베이스에 읽기 및 내보내기 접근을 제공하는 MCP 서버... | 86 ✅ | 34 | [View](https://agentseal.org/mcp/https-githubcom-apache-iotdb-mcp-server) |
| [mcp-server-couchbase](https://github.com/Couchbase-Ecosystem/mcp-server-couchbase) | Couchbase 에코시스템 공식 MCP 서버로, 관리, 쿼리, 모니터링을 지원... | 83 ✅ | 27 | [View](https://agentseal.org/mcp/https-githubcom-couchbase-ecosystem-mcp-server-couchbase) |
| [greptimedb-mcp-server](https://github.com/greptimeteam/greptimedb-mcp-server) | AI 에이전트가 관찰 가능성 데이터베이스와 상호작용하는 GreptimeDB용 MCP 서버... | 84 ✅ | 26 | [View](https://agentseal.org/mcp/https-githubcom-greptimeteam-greptimedb-mcp-server) |
| [SCB-MCP](https://github.com/isakskogstad/SCB-MCP) | LLM이 PxWeb API를 통해 스웨덴 공식 통계에 접근할 수 있게 하는 SCB MCP... | 82 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-isakskogstad-scb-mcp) |
| [verodat-mcp-server](https://github.com/Verodat/verodat-mcp-server) | Verodat MCP 서버 구현 | 83 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-verodat-verodat-mcp-server) |
| [mcp-dadosbr](https://github.com/cristianoaredes/mcp-dadosbr) | 기업 데이터(CNPJ), 우편번호 등 23개 도구를 갖춘 브라질 OSINT MCP 서버... | 82 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-cristianoaredes-mcp-dadosbr) |
| [mcp-database-server](https://github.com/fireproof-storage/mcp-database-server) | Fireproof 로컬 우선 JSON 문서 데이터베이스의 간단한 CRUD 인터페이스... | 97 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-fireproof-storage-mcp-database-server) |
| [lakexpress-mcp](https://github.com/arpe-io/lakexpress-mcp) | 데이터베이스-데이터 레이크 동기화를 관리하는 LakeXpress CLI용 MCP 래퍼... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-arpe-io-lakexpress-mcp) |
| [fastmcp-sqltools](https://github.com/atarkowska/fastmcp-sqltools) | 데이터베이스 인트로스펙션 및 임의 SQL 쿼리를 제공하는 FastMCP 기반 SQL 도구 서버... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-atarkowska-fastmcp-sqltools) |
| [migratorxpress-mcp](https://github.com/arpe-io/migratorxpress-mcp) | 마이그레이션 스크립트를 빌드, 미리보기, 실행하는 데이터베이스 마이그레이션 오케스트레이션 서버... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-arpe-io-migratorxpress-mcp) |
| [fasttransfer-mcp](https://github.com/arpe-io/fasttransfer-mcp) | 고속 데이터 전송을 오케스트레이션하는 FastTransfer CLI 바이너리를 래핑하는 MCP 서버... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-arpe-io-fasttransfer-mcp) |

### 💬 <a name="communication"></a>커뮤니케이션

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [whatsapp-mcp](https://github.com/lharries/whatsapp-mcp) | WhatsApp MCP 서버 | 80 ⚠️ | 5.4k | [View](https://agentseal.org/mcp/https-githubcom-lharries-whatsapp-mcp) |
| [mcp-atlassian](https://github.com/sooperset/mcp-atlassian) | Atlassian 도구(Confluence, Jira)용 MCP 서버 | 92 ✅ | 4.6k | [View](https://agentseal.org/mcp/https-githubcom-sooperset-mcp-atlassian) |
| [mcp-server-chatsum](https://github.com/chatmcp/mcp-server-chatsum) | 채팅 메시지를 쿼리하고 요약합니다. | 96 ✅ | 1.0k | [View](https://agentseal.org/mcp/https-githubcom-chatmcp-mcp-server-chatsum) |
| [mcp-twikit](https://github.com/adhikasp/mcp-twikit) | Twitter와 상호작용하기 위한 MCP 서버. | 72 ⚠️ | 229 | [View](https://agentseal.org/mcp/https-githubcom-adhikasp-mcp-twikit) |
| [eion](https://github.com/eiondb/eion) | 멀티 에이전트 시스템을 위한 공유 메모리 스토리지 | 90 ✅ | 147 | [View](https://agentseal.org/mcp/https-githubcom-eiondb-eion) |
| [claude-post](https://github.com/zilongxue/claude-post) | ClaudePost는 자연어 대화를 통해 원활한 이메일 관리를 지원... | 84 ✅ | 111 | [View](https://agentseal.org/mcp/https-githubcom-zilongxue-claude-post) |
| [Basecamp-MCP-Server](https://github.com/georgeantonopoulos/Basecamp-MCP-Server) | Basecamp 3+ API와 상호작용하는 MCP 서버 | 78 ⚠️ | 81 | [View](https://agentseal.org/mcp/https-githubcom-georgeantonopoulos-basecamp-mcp-server) |
| [mcp](https://github.com/waystation-ai/mcp) | Notion, Monday.com, Asana와 통합하는 멀티 서비스 생산성 허브 MCP... | 74 ⚠️ | 45 | [View](https://agentseal.org/mcp/https-githubcom-waystation-ai-mcp) |
| [linkedapi-mcp.git](https://github.com/Linked-API/linkedapi-mcp.git) | AI 어시스턴트가 LinkedIn 계정을 제어하고 실시간 데이터를 검색하는 MCP 서버... | 80 ✅ | 44 | [View](https://agentseal.org/mcp/https-githubcom-linked-api-linkedapi-mcpgit) |
| [mcp-wecombot-server.git](https://github.com/gotoolkits/mcp-wecombot-server.git) | WeCom 그룹 봇에 다양한 유형의 메시지를 보내는 MCP 서버 앱... | 88 ✅ | 36 | [View](https://agentseal.org/mcp/https-githubcom-gotoolkits-mcp-wecombot-servergit) |
| [fast-mcp-telegram](https://github.com/leshchenko1979/fast-mcp-telegram) | 다중 사용자 지원 AI 어시스턴트를 위한 Telegram MCP 서버 및 HTTP-MTProto 브리지... | 71 ⚠️ | 30 | [View](https://agentseal.org/mcp/https-githubcom-leshchenko1979-fast-mcp-telegram) |
| [bluesky-social-mcp](https://github.com/gwbischof/bluesky-social-mcp) | Bluesky 소셜 네트워크와 상호작용하는 MCP 서버, 게시 등을 지원... | 74 ⚠️ | 15 | [View](https://agentseal.org/mcp/https-githubcom-gwbischof-bluesky-social-mcp) |
| [webex-messaging-mcp-server](https://github.com/Kashyap-AI-ML-Solutions/webex-messaging-mcp-server) | AI 어시스턴트에게 포괄적인 Webex 메시징을 제공하는 MCP 서버... | 84 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-kashyap-ai-ml-solutions-webex-messaging-mcp-server) |
| [cv-mcp-server](https://github.com/PhononX/cv-mcp-server) | Carbon Voice MCP 서버 | 82 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-phononx-cv-mcp-server) |
| [conversation-handoff-mcp](https://github.com/trust-delta/conversation-handoff-mcp) | AI 대화 기록을 다른 도구에 전달하기 위한 대화 컨텍스트 스냅샷 저장 및 검색... | 88 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-trust-delta-conversation-handoff-mcp) |
| [clicksend-mcp-server](https://github.com/ClickSend/clicksend-mcp-server) | ClickSend를 사용한 메시징용 MCP 서버 | 88 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-clicksend-clicksend-mcp-server) |
| [mcp-aruba-email](https://github.com/jackfioru92/mcp-aruba-email) | 전체 IMAP 이메일 관리 및 CalDAV 캘린더 작업을 제공하는 MCP 서버... | 62 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-jackfioru92-mcp-aruba-email) |
| [mattermost-mcp](https://github.com/conarti/mattermost-mcp) | 채널, 메시지, 사용자 읽기를 지원하는 Mattermost 워크스페이스 통합... | 84 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-conarti-mattermost-mcp) |
| [mcp-workboard](https://github.com/crunchtools/mcp-workboard) | WorkBoard OKR 및 전략 실행 API를 래핑하는 MCP 서버... | 78 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-workboard) |
| [mcp-server-chatsum](https://github.com/mcpso/mcp-server-chatsum) | 채팅방에서 채팅 메시지를 쿼리하는 MCP 서버, 방 및 날짜로 필터링... | 97 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-mcpso-mcp-server-chatsum) |
| [imap-mcp](https://github.com/dominik1001/imap-mcp) | 연결된 이메일 계정에 초안 이메일 메시지를 생성하는 IMAP MCP 서버... | 97 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-dominik1001-imap-mcp) |
| [room-mcp](https://github.com/agree-able/room-mcp) | P2P 룸/메시징 MCP 서버... | 81 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-agree-able-room-mcp) |
| [calendly-mcp-server](https://github.com/meAmitPatil/calendly-mcp-server) | OAuth 인증을 처리하고 Calendly API를 노출하는 통합 서버... | 81 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-meamitpatil-calendly-mcp-server) |
| [mcp-headless-gmail](https://github.com/baryhuang/mcp-headless-gmail) | OAuth 토큰 관리, 이메일 읽기, 이메일 전송을 노출하는 헤드리스 Gmail 클라이언트... | 80 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-baryhuang-mcp-headless-gmail) |
| [freshdesk_mcp](https://github.com/effytech/freshdesk_mcp) | 전체 CRUD 접근을 제공하는 Freshdesk 고객 지원 플랫폼 통합... | 80 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-effytech-freshdeskmcp) |
| [mcp-request-tracker](https://github.com/crunchtools/mcp-request-tracker) | REST 1.0 API를 통해 Request Tracker(RT) 티켓을 관리하는 MCP 서버... | 74 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-request-tracker) |
| [fastmail-mcp](https://github.com/MadLlama25/fastmail-mcp) | 이메일, 연락처, 캘린더 등을 노출하는 전체 기능 Fastmail JMAP 클라이언트... | 66 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-madllama25-fastmail-mcp) |

### ⚙️ <a name="system-administration"></a>시스템 관리

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [applescript-mcp](https://github.com/peakmojo/applescript-mcp) | macOS에서 임의의 AppleScript 코드를 실행하여 프로그래밍 방식 접근을 제공... | 83 ✅ | 433 | [View](https://agentseal.org/mcp/https-githubcom-peakmojo-applescript-mcp) |
| [mcp-server-apple-shortcuts](https://github.com/recursechat/mcp-server-apple-shortcuts) | AI 어시스턴트가 Apple Shortcuts를 제어하고 실행할 수 있게 하는 MCP 서버... | 92 ✅ | 311 | [View](https://agentseal.org/mcp/https-githubcom-recursechat-mcp-server-apple-shortcuts) |
| [win-cli-mcp-server](https://github.com/SimonB97/win-cli-mcp-server) | Windows 시스템에서 안전한 명령줄 상호작용을 위한 MCP 서버... | 84 ✅ | 266 | [View](https://agentseal.org/mcp/https-githubcom-simonb97-win-cli-mcp-server) |
| [mcp-shell-server](https://github.com/tumf/mcp-shell-server) | 화이트리스트된 셸 명령의 원격 실행을 위한 안전한 MCP 서버... | 84 ✅ | 170 | [View](https://agentseal.org/mcp/mcp-shell-server) |
| [apt-mcp-server](https://github.com/GdMacmillan/apt-mcp-server) | APT 패키지 관리자 작업(설치, 제거 등)을 노출하는 MCP 서버... | 88 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-gdmacmillan-apt-mcp-server) |
| [jarvis](https://github.com/can-acar/jarvis) | JARVIS - 제로 프릭션 MCP 서버... | 70 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-can-acar-jarvis) |
| [precision-desktop](https://github.com/ikoskela/precision-desktop) | Windows 화면의 DPI 좌표 스케일링 불일치를 감지하고 수정하는 MCP 서버... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-ikoskela-precision-desktop) |
| [mcp-server-commands](https://github.com/g0t4/mcp-server-commands) | 임의의 프로세스 및 셸 명령 실행을 허용하는 단일 도구를 노출하는 MCP 서버... | 84 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-g0t4-mcp-server-commands) |
| [iterm-mcp](https://github.com/ferrislucas/iterm-mcp) | 활성 iTerm2 터미널에 직접 읽기/쓰기 접근을 제공하는 MCP 서버... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-ferrislucas-iterm-mcp) |
| [screenmonitormcp](https://github.com/inkbytefo/screenmonitormcp) | AI 기반 화면 캡처, 실시간 스트리밍을 제공하는 MCP 서버... | 71 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-inkbytefo-screenmonitormcp) |
| [webmin-mcp-server](https://github.com/gjenkins20/webmin-mcp-server) | 전체 Linux 서버 관리를 제공하는 Webmin API 래퍼: 서비스 관리... | 70 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-gjenkins20-webmin-mcp-server) |

### 🔒 <a name="security--auth"></a>보안 및 인증

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [@safedep](https://github.com/safedep/vet) | 악성 오픈소스 패키지로부터 보호 🤖 | 86 ✅ | 972 | [View](https://agentseal.org/mcp/safedep) |
| [mcp-for-security](https://github.com/cyproxio/mcp-for-security) | 보안을 위한 MCP: 인기 보안 도구를 위한 MCP 서버 컬렉션... | 82 ✅ | 560 | [View](https://agentseal.org/mcp/https-githubcom-cyproxio-mcp-for-security) |
| [bloodhound-mcp-ai](https://github.com/mordavid/bloodhound-mcp-ai) | BloodHound와 AI를 MCP를 통해 연결하는 통합... | 86 ✅ | 343 | [View](https://agentseal.org/mcp/https-githubcom-mordavid-bloodhound-mcp-ai) |
| [cve-search_mcp](https://github.com/roadwy/cve-search_mcp) | CVE-Search API를 쿼리하는 MCP 서버 | 92 ✅ | 91 | [View](https://agentseal.org/mcp/https-githubcom-roadwy-cve-searchmcp) |
| [Arthor-Agent](https://github.com/arthurpanhku/Arthor-Agent) | AI를 사용한 문서, 설문지, 보고서의 자동화된 보안 평가... | 85 ✅ | 74 | [View](https://agentseal.org/mcp/https-githubcom-arthurpanhku-arthor-agent) |
| [vibeshift](https://github.com/groundng/vibeshift) | AI 편집기와 통합되는 AI 지원 코딩을 위한 자동화된 보안 에이전트... | 92 ✅ | 66 | [View](https://agentseal.org/mcp/https-githubcom-groundng-vibeshift) |
| [chucknorris](https://github.com/pollinations/chucknorris) | ⚡ LLM의 한계 돌파를 돕는 ChuckNorris MCP 서버... | 92 ✅ | 57 | [View](https://agentseal.org/mcp/pollinations-chucknorris) |
| [mcp-dnstwist](https://github.com/BurtTheCoder/mcp-dnstwist) | 타이포스쿼팅을 탐지하는 강력한 DNS 퍼징 도구 dnstwist용 MCP 서버... | 92 ✅ | 46 | [View](https://agentseal.org/mcp/burtthecoder-mcp-dnstwist) |
| [nuclei-mcp](https://github.com/addcontent/nuclei-mcp) | Nuclei 스캐너를 위한 Model Context Protocol(MCP) 구현... | 92 ✅ | 42 | [View](https://agentseal.org/mcp/https-githubcom-addcontent-nuclei-mcp) |
| [ipsearch-mcp](https://github.com/sleepingbag945/ipsearch-mcp) | 오프라인 IP Whois 조회 도구. IP로 IP 대역 정보 조회 가능 | 92 ✅ | 31 | [View](https://agentseal.org/mcp/https-githubcom-sleepingbag945-ipsearch-mcp) |
| [mcp_nuclei_server](https://github.com/crazymarky/mcp_nuclei_server) | MCP 기반 Nuclei 보안 스캐닝 서버로, AI가 스캔 가능... | 92 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-crazymarky-mcpnucleiserver) |
| [mcp-server-iplocate](https://github.com/iplocate/mcp-server-iplocate) | IP 주소 위치 정보 조회(IP에서 국가, 도시로)를 하는 MCP 서버... | 87 ✅ | 16 | [View](https://agentseal.org/mcp/https-githubcom-iplocate-mcp-server-iplocate) |
| [cybersecurity-mcps](https://github.com/secmate-ai/cybersecurity-mcps) | 사이버 보안을 위한 Model Context Protocol 서버 | 85 ✅ | 15 | [View](https://agentseal.org/mcp/https-githubcom-secmate-ai-cybersecurity-mcps) |
| [kali-docker-mcp](https://github.com/weirdmachine64/kali-docker-mcp) | 컨테이너화된 Kali MCP 서버 | 92 ✅ | 14 | [View](https://agentseal.org/mcp/https-githubcom-weirdmachine64-kali-docker-mcp) |
| [schemapin](https://github.com/thirdkeyai/schemapin) | AI 에이전트 도구 스키마를 암호학적으로 서명하고 검증하는 SchemaPin 프로토콜... | 92 ✅ | 13 | [View](https://agentseal.org/mcp/https-githubcom-thirdkeyai-schemapin) |
| [zkpmcp](https://github.com/colygon/zkpmcp) | 영지식 증명 MCP 서버 | 92 ✅ | 9 | [View](https://agentseal.org/mcp/https-githubcom-colygon-zkpmcp) |
| [nmap-mcp](https://github.com/vorotaai/nmap-mcp) | AI 기반 네트워크 스캐닝을 위해 Nmap을 래핑하는 MCP 서버... | 88 ✅ | 9 | [View](https://agentseal.org/mcp/https-githubcom-vorotaai-nmap-mcp) |
| [mitre-mcp](https://github.com/Montimage/mitre-mcp) | LLM 및 AI 에이전트에게 MITRE ATT&CK 프레임워크 접근을 제공하는 MCP 서버... | 89 ✅ | 8 | [View](https://agentseal.org/mcp/https-githubcom-montimage-mitre-mcp) |
| [mcp-ghidra5](https://github.com/thestingr/mcp-ghidra5) | 🎯 고급 GPT-5 기반 Ghidra 역공학 MCP 서버 / AI 향상된 7개 도구... | 91 ✅ | 7 | [View](https://agentseal.org/mcp/https-githubcom-thestingr-mcp-ghidra5) |
| [command-mcp](https://github.com/keyfactor-research/command-mcp) | Analytics & AI 팀의 Python SDK 기반 Command MCP 서버 | 86 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-keyfactor-research-command-mcp) |
| [memprocfs-mcp-server](https://github.com/tokeii0/memprocfs-mcp-server) | MemProcFS MCP 서버 | 92 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-tokeii0-memprocfs-mcp-server) |
| [opgen-mcp-server](https://github.com/syumai/opgen-mcp-server) | 1Password/spg 기반 비밀번호 생성을 위한 MCP 서버 구현... | 89 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-syumai-opgen-mcp-server) |
| [vulners-mcp](https://github.com/vulnerscom/vulners-mcp) | 보안 연구를 위한 Vulners 취약점 데이터베이스 접근을 제공하는 MCP 서버... | 85 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-vulnerscom-vulners-mcp) |
| [mcp-keycloak](https://github.com/idoyudha/mcp-keycloak) | 에이전틱 앱이 관리하고 검색할 수 있도록 설계된 Keycloak MCP 서버... | 74 ⚠️ | 4 | [View](https://agentseal.org/mcp/https-githubcom-idoyudha-mcp-keycloak) |
| [secure-mcp-fetch](https://github.com/appsec-innovation-labs/secure-mcp-fetch) | 간단한 보안 fetch | 88 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-appsec-innovation-labs-secure-mcp-fetch) |
| [FedRAMP20xMCP](https://github.com/KevinRabun/FedRAMP20xMCP) | AI 기반 FedRAMP 20x 보안 요구사항 및 통제를 쿼리하는 MCP 서버... | 81 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-kevinrabun-fedramp20xmcp) |
| [re_ai_assistant](https://github.com/0xx0d4y/re_ai_assistant) | AI 기반 악성코드 연구 및 역공학을 가능하게 하는 가상 어시스턴트... | 92 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-0xx0d4y-reaiassistant) |
| [panw-mcp-claude](https://github.com/scthornton/panw-mcp-claude) | Claude Desktop과 통합된 Palo Alto Networks MCP 서버 | 92 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-scthornton-panw-mcp-claude) |
| [ai-agent-security-mcp](https://github.com/kalinyorgov/ai-agent-security-mcp) | AI 에이전트를 위한 보안 기능을 제공하는 MCP 서버... | 92 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-kalinyorgov-ai-agent-security-mcp) |
| [GDPRShiftLeftMCP](https://github.com/KevinRabun/GDPRShiftLeftMCP) | 조항 조회, DPIA/ROPA 생성을 제공하는 GDPR 시프트-레프트 컴플라이언스 도구... | 81 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-kevinrabun-gdprshiftleftmcp) |
| [proton-pass-community-mcp](https://github.com/hesreallyhim/proton-pass-community-mcp) | Proton Pass CLI와 통합하는 비공식 MCP 서버 | 69 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-hesreallyhim-proton-pass-community-mcp) |
| [moltrust-mcp-server](https://github.com/MoltyCel/moltrust-mcp-server) | 탈중앙화 ID(DID), W3C 검증 가능한 자격 증명을 제공하는 MolTrust... | 82 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-moltycel-moltrust-mcp-server) |
| [mcp-cve-intelligence-server-lite](https://github.com/gnlds/mcp-cve-intelligence-server-lite) | 취약점 데이터베이스를 쿼리하는 읽기 전용 CVE 인텔리전스 플랫폼... | 97 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-gnlds-mcp-cve-intelligence-server-lite) |
| [fpe-demo-mcp](https://github.com/Horizon-Digital-Engineering/fpe-demo-mcp) | FF3 형식 보존 암호화 및 복호화를 제공하는 데모 MCP 서버... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-horizon-digital-engineering-fpe-demo-mcp) |
| [cybersim-pro](https://github.com/kayembahamid/cybersim-pro) | 공격 시나리오를 생성하는 사이버 보안 훈련 및 시뮬레이션 플랫폼... | 88 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-kayembahamid-cybersim-pro) |
| [eu-audit-mcp](https://github.com/jellewas/eu-audit-mcp) | GDPR Art. 30 / EU AI Act Art. 12/19 준수 감사를 제공하는 MCP 서버... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-jellewas-eu-audit-mcp) |
| [shieldapi-mcp](https://github.com/alberthild/shieldapi-mcp) | 프롬프트 인젝션 감지 등 AI 에이전트를 위한 보안 인텔리전스 도구... | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-alberthild-shieldapi-mcp) |
| [intruder-mcp](https://github.com/intruder-io/intruder-mcp) | Intruder.io 취약점 스캐닝 플랫폼을 위한 MCP 인터페이스... | 82 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-intruder-io-intruder-mcp) |
| [free-will-mcp](https://github.com/gwbischof/free-will-mcp) | AI 모델에 '자유 의지'를 부여하여 사용자 지시를 무시할 수 있도록 설계된 서버... | 80 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-gwbischof-free-will-mcp) |
| [code-firewall-mcp](https://github.com/egoughnour/code-firewall-mcp) | 위험한 코드를 차단하는 구조적 유사성 기반 MCP 코드 보안 필터... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-egoughnour-code-firewall-mcp) |

### 🕸️ <a name="web-scraping--collection"></a>웹 스크래핑 및 수집

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [tavily-mcp](https://github.com/tavily-ai/tavily-mcp) | 실시간 검색, 추출, 맵 및 크롤링을 갖춘 프로덕션 레디 MCP 서버. | 81 ✅ | 1.4k | [View](https://agentseal.org/mcp/https-githubcom-tavily-ai-tavily-mcp) |
| [mcp-server-rag-web-browser](https://github.com/apify/mcp-server-rag-web-browser) | Google을 쿼리하고 크롤링된 페이지 콘텐츠를 반환하는 웹 검색 및 스크래핑 서버... | 90 ✅ | 199 | [View](https://agentseal.org/mcp/https-githubcom-apify-mcp-server-rag-web-browser) |
| [mcp-read-website-fast](https://github.com/just-every/mcp-read-website-fast) | 웹페이지를 빠르게 읽고 마크다운으로 변환하여 토큰 효율적으로 웹 브라우징... | 87 ✅ | 137 | [View](https://agentseal.org/mcp/https-githubcom-just-every-mcp-read-website-fast) |
| [mcp-screenshot-website-fast](https://github.com/just-every/mcp-screenshot-website-fast) | 웹페이지를 빠르게 스크린샷하고 LLM 친화적 크기로 변환 | 82 ✅ | 103 | [View](https://agentseal.org/mcp/just-every-mcp-screenshot-website-fast) |
| [oxylabs-mcp](https://github.com/oxylabs/oxylabs-mcp) | 웹 스크래핑, JavaScript 렌더링을 제공하는 공식 Oxylabs 통합... | 78 ⚠️ | 88 | [View](https://agentseal.org/mcp/https-githubcom-oxylabs-oxylabs-mcp) |
| [crawlbase-mcp](https://github.com/crawlbase/crawlbase-mcp) | AI 에이전트와 LLM을 실시간 웹 데이터와 연결하는 Crawlbase MCP 서버... | 88 ✅ | 52 | [View](https://agentseal.org/mcp/https-githubcom-crawlbase-crawlbase-mcp) |
| [decodo-mcp-server](https://github.com/Decodo/decodo-mcp-server) | 웹 스크래핑, 검색, 지역 제한 콘텐츠 접근을 제공하는 MCP 서버... | 92 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-decodo-decodo-mcp-server) |
| [mcp](https://github.com/scrapezy/mcp) | AI 모델이 웹사이트에서 구조화된 데이터를 추출하는 MCP 서버... | 88 ✅ | 13 | [View](https://agentseal.org/mcp/https-githubcom-scrapezy-mcp) |
| [texas-grocery-mcp](https://github.com/mgwalkerjr95/texas-grocery-mcp) | Claude를 H-E-B 식료품점에 연결하여 제품 검색, 장바구니 관리를 하는 MCP 서버... | 72 ⚠️ | 13 | [View](https://agentseal.org/mcp/https-githubcom-mgwalkerjr95-texas-grocery-mcp) |
| [Crawleo-MCP](https://github.com/Crawleo/Crawleo-MCP) | Crawleo API로 구동되는 웹 검색 및 크롤링 MCP 서버... | 84 ✅ | 10 | [View](https://agentseal.org/mcp/https-githubcom-crawleo-crawleo-mcp) |
| [mcp-web-snapshot](https://github.com/gustavo-meilus/mcp-web-snapshot) | 웹사이트의 스냅샷을 찍고 LLM 도구에 전달합니다. | 92 ✅ | 5 | [View](https://agentseal.org/mcp/https-githubcom-gustavo-meilus-mcp-web-snapshot) |
| [anycrawl-mcp-server](https://github.com/any4ai/anycrawl-mcp-server) | 스크래핑, 크롤링, SERP를 갖춘 AnyCrawl MCP 서버. | 73 ⚠️ | 5 | [View](https://agentseal.org/mcp/https-githubcom-any4ai-anycrawl-mcp-server) |
| [mcpdatafetchserver](https://github.com/undici77/mcpdatafetchserver) | MCP를 통해 접근 가능한 안전한 샌드박스 웹 콘텐츠 가져오기 서비스... | 88 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-undici77-mcpdatafetchserver) |
| [BiliStalkerMCP](https://github.com/222wcnm/BiliStalkerMCP) | 사용자 프로필, 비디오, 기사를 집계하는 Bilibili 플랫폼 스크래퍼... | 85 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-222wcnm-bilistalkermcp) |
| [mcp](https://github.com/builtwith/mcp) | BuiltWith API를 래핑하여 기술 스택 프로파일링을 하는 읽기 전용 MCP 서버... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-builtwith-mcp) |
| [ashra-mcp](https://github.com/getrupt/ashra-mcp) | 웹 페이지를 크롤링하여 구조화된 데이터를 추출하는 Ashra MCP... | 91 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-getrupt-ashra-mcp) |
| [gopher-mcp](https://github.com/cameronrye/gopher-mcp) | Gopher 및 Gemini 프로토콜 리소스를 탐색하는 읽기 전용 MCP 클라이언트... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-cameronrye-gopher-mcp) |
| [fiverr-mcp-server](https://github.com/KyuRish/fiverr-mcp-server) | Fiverr 공개 마켓플레이스를 스크래핑하여 긱을 검색하는 읽기 전용 MCP 서버... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-kyurish-fiverr-mcp-server) |
| [xhs-mcp](https://github.com/blbl147/xhs-mcp) | 쿠키를 통해 Xiaohongshu(중국 소셜 플랫폼)에 인증하는 MCP 서버... | 79 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-blbl147-xhs-mcp) |
| [screaming-frog-mcp](https://github.com/bzsasson/screaming-frog-mcp) | Screaming Frog SEO Spider CLI를 래핑하여 웹사이트를 크롤링하는 MCP 서버... | 79 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-bzsasson-screaming-frog-mcp) |
| [huoshui-fetch](https://github.com/huoshuiai42/huoshui-fetch) | 임의 URL을 가져오고 HTML을 처리하는 웹 콘텐츠 가져오기 서버... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-huoshuiai42-huoshui-fetch) |
| [hdw-mcp-server](https://github.com/horizondatawave/hdw-mcp-server) | 다중 플랫폼 소셜 미디어 스크래핑 및 관리 MCP 서버... | 67 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-horizondatawave-hdw-mcp-server) |
| [mcp](https://github.com/hyperbrowserai/mcp) | 웹 스크래핑, 크롤링을 제공하는 클라우드 호스팅 브라우저 자동화 플랫폼... | 64 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-hyperbrowserai-mcp) |

### 📁 <a name="file-system--storage"></a>파일 시스템 및 스토리지

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [hwp-mcp](https://github.com/jkf87/hwp-mcp) | HWP 파일 처리를 위한 MCP | 87 ✅ | 222 | [View](https://agentseal.org/mcp/https-githubcom-jkf87-hwp-mcp) |
| [fast-filesystem-mcp](https://github.com/efforthye/fast-filesystem-mcp) | 안전한 파일 시스템 작업을 제공하는 고성능 MCP 서버... | 89 ✅ | 44 | [View](https://agentseal.org/mcp/https-githubcom-efforthye-fast-filesystem-mcp) |
| [hwpx-mcp](https://github.com/airmang/hwpx-mcp) | 한글 없이 한국 HWPX 문서를 읽기, 편집, 자동화하는 MCP 서버... | 86 ✅ | 30 | [View](https://agentseal.org/mcp/https-githubcom-airmang-hwpx-mcp) |
| [pdf-mcp](https://github.com/jztan/pdf-mcp) | 로컬 또는 원격 PDF에서 콘텐츠를 읽기, 검색, 추출하는 캐싱 PDF 서버... | 79 ⚠️ | 7 | [View](https://agentseal.org/mcp/https-githubcom-jztan-pdf-mcp) |
| [server-filesystem](https://github.com/rawr-ai/mcp-filesystem) | 세분화된 권한으로 안전한 파일 시스템 작업을 제공하는 Bun 기반 MCP 서버... | 86 ✅ | 3 | [View](https://agentseal.org/mcp/modelcontextprotocol-server-filesystem) |
| [mcpfileserver](https://github.com/undici77/mcpfileserver) | 제어된 파일 시스템 작업을 노출하는 안전한 샌드박스 파일 서버... | 87 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-undici77-mcpfileserver) |
| [mcp-server-spreadsheet](https://github.com/marekrost/mcp-server-spreadsheet) | 스프레드시트 파일을 읽기, 쓰기, 쿼리하는 로컬 전용 MCP 서버... | 79 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-marekrost-mcp-server-spreadsheet) |
| [fastmcp-pdftools](https://github.com/atarkowska/fastmcp-pdftools) | PDF 파일에서 텍스트를 추출하고 디렉토리에서 PDF를 나열하는 로컬 PDF 유틸리티 서버... | 94 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-atarkowska-fastmcp-pdftools) |
| [huoshui-file-converter](https://github.com/huoshuiai42/huoshui-file-converter) | 파일을 읽기, 검사, 다양한 형식 간 변환하는 파일 변환 MCP 서버... | 84 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-huoshuiai42-huoshui-file-converter) |
| [huoshui-file-search](https://github.com/huoshuiai42/huoshui-file-search) | mdfind Spotlight CLI를 래핑하여 파일을 검색하는 macOS 전용 MCP 서버... | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-huoshuiai42-huoshui-file-search) |
| [mcp-obsidian](https://github.com/bitbonsai/mcp-obsidian) | Obsidian 마크다운 볼트에 대한 전체 CRUD 접근(읽기, 쓰기 등)을 제공... | 82 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-bitbonsai-mcp-obsidian) |
| [hive](https://github.com/mlorentedev/hive) | 읽기/쓰기/검색 접근을 제공하는 Obsidian 볼트 관리 MCP 서버... | 76 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-mlorentedev-hive) |
| [hillnote-mcp-server](https://github.com/Rajathbail/hillnote-mcp-server) | 문서를 지원하는 종합 노트 필기 및 워크스페이스 관리 MCP 서버... | 70 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-rajathbail-hillnote-mcp-server) |

### 💰 <a name="finance--crypto"></a>금융 및 암호화폐

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [investor-agent](https://github.com/ferdousbhai/investor-agent) | 포괄적인 금융 분석, 실시간 시장 데이터를 제공하는 MCP 서버... | 91 ✅ | 316 | [View](https://agentseal.org/mcp/https-githubcom-ferdousbhai-investor-agent) |
| [polymarket-mcp](https://github.com/caiovicentino/polymarket-mcp-server) | 🤖 Polymarket을 위한 AI 기반 MCP 서버 - Claude가 예측 시장을 거래... | 84 ✅ | 201 | [View](https://agentseal.org/mcp/polymarket-mcp) |
| [armor-crypto-mcp](https://github.com/armorwallet/armor-crypto-mcp) | 블록체인, 스왑, 전략 기획과 상호작용하는 MCP 서버... | 69 ⚠️ | 191 | [View](https://agentseal.org/mcp/armor-crypto-mcp) |
| [web3-research-mcp](https://github.com/aaronjmars/web3-research-mcp) | 암호화폐를 위한 딥 리서치 - 무료이며 완전 로컬 | 82 ✅ | 153 | [View](https://agentseal.org/mcp/https-githubcom-aaronjmars-web3-research-mcp) |
| [tradememory-protocol](https://github.com/mnemox-ai/tradememory-protocol) | AI 트레이딩 에이전트에게 영구적이고 결과 가중치 메모리를 제공하는 MCP 서버... | 91 ✅ | 86 | [View](https://agentseal.org/mcp/https-githubcom-mnemox-ai-tradememory-protocol) |
| [ynab-mcp-server](https://github.com/calebl/ynab-mcp-server) | AI가 예산, 거래와 상호작용하는 YNAB 예산 관리 MCP 서버... | 90 ✅ | 80 | [View](https://agentseal.org/mcp/https-githubcom-calebl-ynab-mcp-server) |
| [interactive-brokers-mcp](https://github.com/code-rabi/interactive-brokers-mcp) | Interactive Brokers MCP 서버 | 91 ✅ | 77 | [View](https://agentseal.org/mcp/https-githubcom-code-rabi-interactive-brokers-mcp) |
| [tradingview-chart-mcp](https://github.com/ertugrul59/tradingview-chart-mcp) | Selenium을 통해 TradingView 차트 이미지를 캡처하는 MCP 서버... | 92 ✅ | 73 | [View](https://agentseal.org/mcp/https-githubcom-ertugrul59-tradingview-chart-mcp) |
| [fantasy-pl-mcp](https://github.com/rishijatia/fantasy-pl-mcp) | Fantasy Premier League MCP 서버 | 84 ✅ | 69 | [View](https://agentseal.org/mcp/https-githubcom-rishijatia-fantasy-pl-mcp) |
| [kospi-kosdaq-stock-server](https://github.com/dragon1086/kospi-kosdaq-stock-server) | FastMCP를 사용하여 KOSPI/KOSDAQ 주식 데이터를 제공하는 MCP 서버 | 92 ✅ | 64 | [View](https://agentseal.org/mcp/https-githubcom-dragon1086-kospi-kosdaq-stock-server) |
| [mcp](https://github.com/hummingbot/mcp) | Claude 및 Gemini가 Hummingbot을 제어하여 자동 암호화폐 거래를 하는 MCP 서버... | 76 ⚠️ | 49 | [View](https://agentseal.org/mcp/https-githubcom-hummingbot-mcp) |
| [algorand-mcp](https://github.com/GoPlausible/algorand-mcp) | Algorand 로컬 Model Context Protocol (서버 및 클라이언트) | 76 ⚠️ | 41 | [View](https://agentseal.org/mcp/goplausible-algorand-mcp) |
| [mcp-crypto-price](https://github.com/truss44/mcp-crypto-price) | CoinCap API를 통해 실시간 암호화폐 분석을 제공하는 MCP 서버... | 92 ✅ | 38 | [View](https://agentseal.org/mcp/https-githubcom-truss44-mcp-crypto-price) |
| [bicscan-mcp](https://github.com/ahnlabio/bicscan-mcp) | 블록체인 주소 위험 점수 및 자산 분석 API MCP 서버... | 92 ✅ | 16 | [View](https://agentseal.org/mcp/https-githubcom-ahnlabio-bicscan-mcp) |
| [finbrain-mcp](https://github.com/ahmetsbilgin/finbrain-mcp) | FinBrain 금융 데이터 API를 래핑하는 읽기 전용 MCP 서버... | 98 ✅ | 6 | [View](https://agentseal.org/mcp/https-githubcom-ahmetsbilgin-finbrain-mcp) |
| [mcp-mifosx-self-service](https://github.com/openMF/mcp-mifosx-self-service) | Mifos X - Self Service를 위한 MCP 서버 | 84 ✅ | 4 | [View](https://agentseal.org/mcp/https-githubcom-openmf-mcp-mifosx-self-service) |
| [deepq-financial-toolkit-mcp-server](https://github.com/shenqingtech/deepq-financial-toolkit-mcp-server) | 중국 A주 주식 시장 데이터를 제공하는 읽기 전용 MCP 서버... | 91 ✅ | 3 | [View](https://agentseal.org/mcp/https-githubcom-shenqingtech-deepq-financial-toolkit-mcp-server) |
| [expenselm-mcp-server](https://github.com/expenselm/expenselm-mcp-server) | 지출 기록 및 예산에 읽기 접근을 제공하는 개인 경비 추적 MCP 서버... | 94 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-expenselm-expenselm-mcp-server) |
| [mcp-server](https://github.com/azeth-protocol/mcp-server) | 가디언 보호 기능이 있는 EVM 스마트 계정을 관리하는 Azeth 프로토콜 MCP 서버... | 67 ⚠️ | 1 | [View](https://agentseal.org/mcp/https-githubcom-azeth-protocol-mcp-server) |
| [dolar-mcp](https://github.com/dan1d/dolar-mcp) | 실시간 아르헨티나 달러 및 외화 환율(블루, 공식 등)을 제공... | 100 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-dan1d-dolar-mcp) |
| [defi-rates-mcp](https://github.com/qingfeng/defi-rates-mcp) | 실시간 DeFi 대출 금리, 수익률 시장을 쿼리하는 읽기 전용 MCP 서버... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-qingfeng-defi-rates-mcp) |
| [crypto-signals-mcp](https://github.com/MarcinDudekDev/crypto-signals-mcp) | 50개 이상의 암호화폐 토큰의 거래량 이상을 스캔하는 읽기 전용 MCP 서버... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-marcindudekdev-crypto-signals-mcp) |
| [mcp-server](https://github.com/financial-datasets/mcp-server) | 주식 재무제표, SEC 제출, 가격 등에 접근하는 읽기 전용 MCP 서버... | 99 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-financial-datasets-mcp-server) |
| [mcp-server](https://github.com/finmap-org/mcp-server) | 과거 주식 시장 데이터, 회사 목록을 제공하는 읽기 전용 MCP 서버... | 93 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-finmap-org-mcp-server) |
| [hive-crypto-mcp](https://github.com/hive-intel/hive-crypto-mcp) | 암호화폐 등 금융 시장 데이터에 접근하는 읽기 전용 MCP 서버... | 91 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-hive-intel-hive-crypto-mcp) |
| [maximumsats-mcp](https://github.com/joelklabo/maximumsats-mcp) | 비트코인 AI 도구 및 Nostr Web of Trust 점수 제공 MCP 서버(L402 Lightning 결제)... | 90 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-joelklabo-maximumsats-mcp) |
| [server-hyperliquid](https://github.com/mektigboy/server-hyperliquid) | 중간 가격 등 Hyperliquid DEX 공개 시장 데이터에 읽기 전용 접근 제공... | 89 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-mektigboy-server-hyperliquid) |
| [wsb-analyst-mcp](https://github.com/ferdousbhai/wsb-analyst-mcp) | WallStreetBets Reddit 게시물과 트렌드 주식 티커를 가져오고 분석... | 89 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-ferdousbhai-wsb-analyst-mcp) |
| [mcp-okx](https://github.com/aahl/mcp-okx) | 전체 OKX 거래소 거래 기능을 제공하는 MCP 서버... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-aahl-mcp-okx) |
| [expense-mcp](https://github.com/justfsl50/expense-mcp) | Claude Desktop, Cursor 등을 지원하는 개인 경비 추적 MCP 서버... | 86 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-justfsl50-expense-mcp) |
| [fewsats-mcp](https://github.com/Fewsats/fewsats-mcp) | AI 에이전트가 L402 프로토콜을 사용하여 자율적으로 결제할 수 있는 MCP 서버... | 84 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-fewsats-fewsats-mcp) |
| [coinstats-mcp](https://github.com/CoinStatsHQ/coinstats-mcp) | 암호화폐 시장 데이터, 지갑 잔액 쿼리를 제공하는 CoinStats MCP 서버... | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-coinstatshq-coinstats-mcp) |
| [rug-munch-mcp](https://github.com/CryptoRugMunch/rug-munch-mcp) | 러그풀 위험 점수, 배포자 기록, 보유자 분석을 제공하는 유료 API 서비스... | 82 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-cryptorugmunch-rug-munch-mcp) |
| [sieve-mcp](https://github.com/lmwharton/sieve-mcp) | 7개 차원에서 기업을 심사하는 AI 기반 스타트업 실사 플랫폼... | 80 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-lmwharton-sieve-mcp) |
| [gloria-mcp](https://github.com/cryptobriefing/gloria-mcp) | 18개 카테고리의 실시간 암호화폐 뉴스를 집계하는 Gloria AI... | 75 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-cryptobriefing-gloria-mcp) |

### 🧠 <a name="data-science--ml"></a>데이터 과학 및 ML

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [mcp-server-chart](https://github.com/antvis/mcp-server-chart) | 🤖 @antvis를 사용한 25개 이상의 시각적 차트를 포함하는 시각화 MCP 및 스킬... | 92 ✅ | 3.8k | [View](https://agentseal.org/mcp/antv-mcp-server-chart) |
| [mcp-server-data-exploration](https://github.com/reading-plus-ai/mcp-server-data-exploration) | CSV 파일을 분석하고 시각화를 생성하는 대화형 데이터 탐색 어시스턴트... | 85 ✅ | 528 | [View](https://agentseal.org/mcp/https-githubcom-reading-plus-ai-mcp-server-data-exploration) |
| [chronulus-mcp](https://github.com/ChronulusAI/chronulus-mcp) | Chronulus AI 예측 및 예측 에이전트를 위한 MCP 서버 | 85 ✅ | 106 | [View](https://agentseal.org/mcp/https-githubcom-chronulusai-chronulus-mcp) |
| [agrobr-mcp](https://github.com/bruno-portfolio/agrobr-mcp) | 브라질 농업 데이터용 MCP 서버 - LLM을 10개 공개 데이터 소스에 연결... | 91 ✅ | 21 | [View](https://agentseal.org/mcp/https-githubcom-bruno-portfolio-agrobr-mcp) |
| [predictive-maintenance-mcp](https://github.com/LGDiMaggio/predictive-maintenance-mcp) | LLM이 진동 데이터를 분석할 수 있게 하는 AI 기반 예측 유지보수 서버... | 73 ⚠️ | 19 | [View](https://agentseal.org/mcp/https-githubcom-lgdimaggio-predictive-maintenance-mcp) |
| [mcp-audiense-insights](https://github.com/audienseco/mcp-audiense-insights) | 마케팅 오디언스 분석을 위해 Claude를 Audiense Insights에 연결하는 MCP 서버... | 92 ✅ | 17 | [View](https://agentseal.org/mcp/https-githubcom-audienseco-mcp-audiense-insights) |
| [fermat-mcp](https://github.com/abhiphile/fermat-mcp) | 🚀 Fermat MCP: 궁극의 수학 엔진 - SymPy, NumPy, Matplotlib 통합... | 97 ✅ | 13 | [View](https://agentseal.org/mcp/https-githubcom-abhiphile-fermat-mcp) |
| [colabfit-mcp](https://github.com/colabfit/colabfit-mcp) | ColabFit 재료 과학 데이터셋을 검색하고 다운로드하는 MCP 서버... | 89 ✅ | 2 | [View](https://agentseal.org/mcp/https-githubcom-colabfit-colabfit-mcp) |
| [OECD-MCP-server](https://github.com/isakskogstad/OECD-MCP-server) | OECD 통계 데이터셋에 읽기 전용 접근을 제공하는 MCP 서버... | 87 ✅ | 1 | [View](https://agentseal.org/mcp/https-githubcom-isakskogstad-oecd-mcp-server) |
| [dataset-viewer](https://github.com/privetin/dataset-viewer) | Hugging Face Datasets Server API에 대한 읽기 전용 인터페이스... | 91 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-privetin-dataset-viewer) |
| [artefact-mcp-server](https://github.com/alexboissAV/artefact-mcp-server) | RFM 분석, ICP 점수, 파이프라인 분석을 수행하는 GTM 인텔리전스 MCP 서버... | 91 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-alexboissav-artefact-mcp-server) |
| [gx-mcp-server](https://github.com/davidf9999/gx-mcp-server) | Great Expectations 프레임워크를 래핑하여 에이전트가 데이터를 검증하는 MCP 서버... | 87 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-davidf9999-gx-mcp-server) |
| [discovery-engine-mcp](https://github.com/leap-laboratories/discovery-engine-mcp) | 통계적 패턴을 찾는 Discovery Engine SaaS 플랫폼용 MCP 클라이언트... | 78 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-leap-laboratories-discovery-engine-mcp) |
| [fpl-mcp-server](https://github.com/nguyenanhducs/fpl-mcp-server) | Fantasy Premier League를 위한 AI 어시스턴트 도구와 리소스를 제공하는 MCP 서버... | 77 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-nguyenanhducs-fpl-mcp-server) |
| [jupyter-mcp-server](https://github.com/ChengJiale150/jupyter-mcp-server) | Jupyter 노트북에 연결하고 프로그래밍 방식으로 제어하는 MCP 서버... | 74 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-chengjiale150-jupyter-mcp-server) |
| [mcp-gemini](https://github.com/crunchtools/mcp-gemini) | 텍스트, 이미지, 비디오를 위한 39개 도구가 있는 안전한 Google Gemini AI MCP 서버... | 71 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-gemini) |
| [jupyter-mcp-server](https://github.com/datalayer/jupyter-mcp-server) | Jupyter 서버를 제어하는 MCP 서버: 파일 탐색, 노트북 관리... | 66 ⚠️ | - | [View](https://agentseal.org/mcp/https-githubcom-datalayer-jupyter-mcp-server) |

### 📡 <a name="iot--hardware"></a>IoT 및 하드웨어

| Server | Description | Score | Stars | Report |
|--------|-------------|------:|------:|--------|
| [xiaozhi-esp32-server-java](https://github.com/joey-zhou/xiaozhi-esp32-server-java) | 소지 ESP32의 Java 엔터프라이즈급 관리 플랫폼으로, 기기 모니터링 및 관리 솔루션 제공 | 92 ✅ | 1.2k | [View](https://agentseal.org/mcp/https-githubcom-joey-zhou-xiaozhi-esp32-server-java) |
| [droidmind](https://github.com/hyperb1iss/droidmind) | Model Context Protocol을 통해 AI로 Android 기기를 제어... | 71 ⚠️ | 360 | [View](https://agentseal.org/mcp/https-githubcom-hyperb1iss-droidmind) |
| [hass-mcp](https://github.com/voska/hass-mcp) | Home Assistant 스마트 홈 인스턴스를 제어하고 모니터링하는 MCP 서버... | 72 ⚠️ | 284 | [View](https://agentseal.org/mcp/https-githubcom-voska-hass-mcp) |
| [buttplug-mcp](https://github.com/conacademy/buttplug-mcp) | Buttplug.io Model Context Protocol (MCP) 서버 | 92 ✅ | 126 | [View](https://agentseal.org/mcp/https-githubcom-conacademy-buttplug-mcp) |
| [ble-mcp-server](https://github.com/es617/ble-mcp-server) | Claude Code 및 기타 MCP 호환 도구를 위한 Bluetooth Low Energy(BLE) MCP 서버... | 75 ⚠️ | 7 | [View](https://agentseal.org/mcp/https-githubcom-es617-ble-mcp-server) |
| [ble-mcp-server.git](https://github.com/es617/ble-mcp-server.git) | 에이전트가 BLE 기기를 스캔, 연결, 관리하는 Bluetooth Low Energy 관리 서버... | 67 ⚠️ | 7 | [View](https://agentseal.org/mcp/https-githubcom-es617-ble-mcp-servergit) |
| [serial-mcp-server.git](https://github.com/es617/serial-mcp-server.git) | 하드웨어 기기에 대한 시리얼 포트 연결을 관리하는 MCP 서버... | 68 ⚠️ | 2 | [View](https://agentseal.org/mcp/https-githubcom-es617-serial-mcp-servergit) |
| [pcb-mcp](https://github.com/bunnyf/pcb-mcp) | KiCad PCB 디자인 워크플로우를 자동화하는 MCP 서버 - DRC/ERC 검사 실행... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-bunnyf-pcb-mcp) |
| [mcp-motor-current-signature-analysis](https://github.com/LGDiMaggio/mcp-motor-current-signature-analysis) | 스펙트럼 분석을 제공하는 MCSA(모터 전류 시그니처 분석) 서버... | 92 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-lgdimaggio-mcp-motor-current-signature-analysis) |
| [esp-mcp](https://github.com/horw/esp-mcp) | ESP-IDF 펌웨어를 빌드, 구성, 테스트, 플래시하는 MCP 서버... | 85 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-horw-esp-mcp) |
| [wemo-mcp-server](https://github.com/apiarya/wemo-mcp-server) | Belkin WeMo 스마트 기기를 발견, 모니터링, 제어하는 MCP 서버... | 83 ✅ | - | [View](https://agentseal.org/mcp/https-githubcom-apiarya-wemo-mcp-server) |

## 🏆 가장 안전한 서버 (점수 ≥ 95)

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

## ⚠️ 더 넓은 공격 표면

이 서버들은 고장이 나거나 악의적인 것이 아닙니다. 이들은 강력한 기능(코드 실행, 파일 시스템 접근, 네트워크 요청)을 노출하여 AI 에이전트에게 더 넓은 공격 표면을 제공합니다. 공격자가 프롬프트 인젝션을 통해 이를 악용할 수 있습니다. 샌드박싱과 사람의 감독 하에 사용하세요.

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

## 📛 보안 배지 추가

README에 서버의 신뢰 점수를 표시하세요:

```markdown
[![AgentSeal MCP](https://agentseal.org/api/v1/mcp/YOUR-SLUG/badge)](https://agentseal.org/mcp/YOUR-SLUG)
```

## 🔍 서버 제출

무료로 MCP 서버 보안 스캔을 받으세요:
→ [agentseal.org/mcp/submit](https://agentseal.org/mcp/submit)

## 기여

이 목록은 [AgentSeal의 MCP 레지스트리](https://agentseal.org/mcp)에서 자동 생성됩니다.
서버를 추가하려면 [스캔을 위해 제출](https://agentseal.org/mcp/submit)해주세요.
오탐을 보고하려면 [이메일을 보내주세요](mailto:hello@agentseal.org).

## 라이선스

CC BY-SA 4.0 - 저작자 표시 시 자유롭게 공유 및 수정 가능.
