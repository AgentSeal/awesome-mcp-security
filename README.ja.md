# 🛡️ MCP サーバーセキュリティレジストリ

> **764 の MCP サーバー**をスキャンし、AIエージェントのセキュリティリスクを分析しました。
> スコアはAIエージェントが各サーバーを安全に使用できる度合いを反映しており、サーバー自体のコード品質を示すものではありません。
> 毎日更新。[AgentSeal](https://agentseal.org) 提供。

[English](README.md) · [中文](README.zh.md) · **日本語** · [한국어](README.ko.md)

## 概要統計

| 指標 | 件数 |
|------|------|
| スキャン済みサーバー総数 | **764** |
| ✅ 安全 (スコア ≥ 80) | **598** |
| ⚠️ 要確認 (スコア 50-79) | **166** |
| セキュリティ検出事項の総数 | **6098** |
| 最終更新日 | 2026年3月13日 |

## スコアリング方法

各サーバーは **9つのセキュリティアナライザー**でテストされます:

- **スキーマ分析** - ツールパラメータの型と制約を検証
- **静的パターン検出** - コマンドインジェクション、SSRF、パストラバーサルのパターンを検出
- **プロンプトインジェクションスキャン** - ツール説明に隠された指示を検出
- **有害フロー分析** - 危険なツールチェーンを特定（例: シークレットの読み取り -> 外部URLへの送信）
- **Unicode検出** - 不可視文字による攻撃を捕捉
- **ディープオートプシー** - 45以上のMCP固有の攻撃パターンによるアクティブな探査
- **アノテーションと指示分析** - 動作を変更するメタデータを検査
- **リソース分析** - 公開されたリソースとテンプレートを評価
- **LLM分類** - Claudeによるツール意図のセマンティック分析

**信頼スコア:** 0-100はAIエージェントがこのサーバーをどれだけ安全に使用できるかを測定します。
低いスコアはサーバーにバグがある、または悪意があるという意味ではありません。AIエージェントがそのサーバーを使用する際の攻撃対象領域が大きい（例: コード実行、ファイルアクセス、ネットワークリクエスト）ことを意味し、攻撃者がプロンプトインジェクションやツールポイズニングを通じてこれを悪用する可能性があります。

- **安全 (>= 80):** 攻撃対象領域が小さい。エージェントは最小限のリスクで使用可能。
- **要確認 (50-79):** 攻撃対象領域を拡大する重要な機能あり。適切なガードレールと共に使用。
- **リスクあり (20-49):** 攻撃対象領域が大きい。厳格なサンドボックスと人間の監視が必要。
- **危険 (< 20):** 重大なセキュリティ上の懸念あり。自動使用は非推奨。

## 凡例

| シンボル | 意味 |
|----------|------|
| ✅ | 安全 - AIエージェントの攻撃対象領域が小さい |
| ⚠️ | 要確認 - より広範な機能、ガードレール付きで使用 |
| 🟠 | リスクあり - 攻撃対象領域が大きい、サンドボックスが必要 |
| 🔴 | 危険 - 自動使用は非推奨 |

## カテゴリ

- [🛠️ 開発ツール](#developer-tools) (240)
- [🔍 検索・ナレッジ](#search--knowledge) (59)
- [💻 コード・IDE](#code--ide) (27)
- [☁️ クラウド・インフラ](#cloud--infrastructure) (32)
- [📝 コンテンツ・メディア](#content--media) (45)
- [🔌 API開発](#api-development) (17)
- [🗄️ データベース・SQL](#database--sql) (25)
- [💬 コミュニケーション](#communication) (27)
- [⚙️ システム管理](#system-administration) (11)
- [🔒 セキュリティ・認証](#security--auth) (40)
- [🕸️ Webスクレイピング・収集](#web-scraping--collection) (23)
- [📁 ファイルシステム・ストレージ](#file-system--storage) (13)
- [💰 金融・暗号資産](#finance--crypto) (35)
- [🧠 データサイエンス・ML](#data-science--ml) (17)
- [📡 IoT・ハードウェア](#iot--hardware) (11)

### 🛠️ <a name="developer-tools"></a>開発ツール

| サーバー | 説明 | スコア | Stars | レポート |
|----------|------|-------:|------:|----------|
| [markitdown](https://github.com/microsoft/markitdown) | ファイルやオフィス文書をMarkdownに変換するPythonツール。 | 88 ✅ | 90.7k | [表示](https://agentseal.org/mcp/https-githubcom-microsoft-markitdown) |
| [chrome-devtools-mcp](https://github.com/chromedevtools/chrome-devtools-mcp) | コーディングエージェント向けChrome DevTools | 73 ⚠️ | 28.8k | [表示](https://agentseal.org/mcp/chrome-devtools-mcp) |
| [Playwright](https://github.com/microsoft/playwright-mcp) | Playwrightを使用して大規模言語モデル（LLM）のブラウザ操作を自動化... | 62 ⚠️ | 28.7k | [表示](https://agentseal.org/mcp/https-githubcom-microsoft-playwright-mcp) |
| [GitHub](https://github.com/github/github-mcp-server) | GitHub APIとの高度な自動化とインタラクション機能を提供... | 70 ⚠️ | 27.8k | [表示](https://agentseal.org/mcp/https-githubcom-github-github-mcp-server) |
| [claude-flow](https://github.com/ruvnet/claude-flow) | セキュアなマルチエージェントスウォームのデプロイ向けエンタープライズAIオーケストレーションプラットフォーム... | 86 ✅ | 20.9k | [表示](https://agentseal.org/mcp/https-githubcom-ruvnet-claude-flow) |
| [beads](https://github.com/steveyegge/beads) | Beads - コーディングエージェントのメモリアップグレード | 86 ✅ | 18.9k | [表示](https://agentseal.org/mcp/https-githubcom-steveyegge-beads) |
| [archon](https://github.com/coleam00/archon) | Archon OSベータ版 - AIエージェントのナレッジ・タスク管理基盤... | 92 ✅ | 13.8k | [表示](https://agentseal.org/mcp/https-githubcom-coleam00-archon) |
| [mcp-go](https://github.com/mark3labs/mcp-go) | Model Context Protocol (MCP)のGo実装。シームレスな統合を実現... | 89 ✅ | 8.3k | [表示](https://agentseal.org/mcp/https-githubcom-mark3labs-mcp-go) |
| [git-mcp](https://github.com/idosal/git-mcp) | コードのハルシネーションを解消! GitMCPは無料でオープンソースのリモートMCP... | 78 ⚠️ | 7.8k | [表示](https://agentseal.org/mcp/git-mcp) |
| [browser-tools-mcp](https://github.com/agentdeskai/browser-tools-mcp) | CursorやMCP互換IDEから直接ブラウザログを監視。 | 91 ✅ | 7.1k | [表示](https://agentseal.org/mcp/https-githubcom-agentdeskai-browser-tools-mcp) |
| [cursor-talk-to-figma-mcp](https://github.com/sonnylazuardi/cursor-talk-to-figma-mcp) | CursorやClaude CodeなどのAIエージェントがFigmaデザインを読み取り・変更できるMCP統合... | 88 ✅ | 6.5k | [表示](https://agentseal.org/mcp/https-githubcom-sonnylazuardi-cursor-talk-to-figma-mcp) |
| [cursor-talk-to-figma-mcp](https://github.com/grab/cursor-talk-to-figma-mcp) | TalkToFigma: AIエージェント（Cursor, Claude Code）とFigma間のMCP統合... | 88 ✅ | 6.5k | [表示](https://agentseal.org/mcp/https-githubcom-grab-cursor-talk-to-figma-mcp) |
| [ida-pro-mcp](https://github.com/mrexodia/ida-pro-mcp) | IDA Proと言語モデルを橋渡しするAI搭載リバースエンジニアリングアシスタント... | 88 ✅ | 6.3k | [表示](https://agentseal.org/mcp/ida-pro-mcp) |
| [mcp](https://github.com/browsermcp/mcp) | Browser MCPはAIアプリケーションがブラウザと対話できるModel Context Provider (MCP)サーバー... | 86 ✅ | 6.0k | [表示](https://agentseal.org/mcp/browsermcp-mcp) |
| [desktopcommandermcp](https://github.com/wonderwhy-er/desktopcommandermcp) | Claudeにターミナル制御、ファイルシステム検索を提供するMCPサーバー... | 63 ⚠️ | 5.7k | [表示](https://agentseal.org/mcp/https-githubcom-wonderwhy-er-desktopcommandermcp) |
| [klavis](https://github.com/klavis-ai/klavis) | Klavis AI (YC X25): AIエージェントがリモートでツールを使用できるMCP統合プラットフォーム... | 68 ⚠️ | 5.7k | [表示](https://agentseal.org/mcp/https-githubcom-klavis-ai-klavis) |
| [praisonai](https://github.com/mervinpraison/praisonai) | PraisonAI 🦞 - 24時間365日稼働のAI従業員チーム。複雑な課題を自動化して解決... | 78 ⚠️ | 5.7k | [表示](https://agentseal.org/mcp/https-githubcom-mervinpraison-praisonai) |
| [playwright-mcp-server](https://github.com/executeautomation/mcp-playwright) | Playwright Model Context Protocolサーバー - ブラウザとAPIの自動化ツール... | 73 ⚠️ | 5.3k | [表示](https://agentseal.org/mcp/executeautomation-playwright-mcp-server) |
| [magic](https://github.com/21st-dev/magic-mcp) | Cursor/WindSurf/Cline内でv0のように使える。21st dev Magic MCPサーバー... | 82 ✅ | 4.4k | [表示](https://agentseal.org/mcp/21st-dev-magic) |
| [osaurus](https://github.com/osaurus-ai/osaurus) | AIを自分のものに。AIエージェント向けネイティブmacOSハーネス - 任意のモデル、永続的... | 79 ⚠️ | 4.1k | [表示](https://agentseal.org/mcp/osaurus-ai-osaurus) |
| [context-mode](https://github.com/mksglu/context-mode) | MCPはツールアクセスのプロトコル。コンテキストの仮想化レイヤーを提供。 | 78 ⚠️ | 3.7k | [表示](https://agentseal.org/mcp/https-githubcom-mksglu-context-mode) |
| [mcp-feedback-enhanced](https://github.com/minidoracat/mcp-feedback-enhanced) | AI支援コーディングツールでのインタラクティブなユーザーフィードバックとコマンド実行のための拡張MCPサーバー... | 91 ✅ | 3.6k | [表示](https://agentseal.org/mcp/https-githubcom-minidoracat-mcp-feedback-enhanced) |
| [archestra](https://github.com/archestra-ai/archestra) | ガードレール、MCPレジストリ、ゲートウェイ、オーケストレーター付きエンタープライズAIプラットフォーム | 92 ✅ | 3.5k | [表示](https://agentseal.org/mcp/https-githubcom-archestra-ai-archestra) |
| [refact-chat-js](https://github.com/smallcloudai/refact) | エンジニアリングタスクをエンドツーエンドで処理するAIエージェント: 開発者ツールと統合... | 92 ✅ | 3.5k | [表示](https://agentseal.org/mcp/refact-chat-js) |
| [shadcn-ui-mcp-server](https://github.com/jpisnice/shadcn-ui-mcp-server) | LLMがshadcn UIコンポーネントの構造やユースケースについてコンテキストを得るためのMCPサーバー... | 83 ✅ | 2.7k | [表示](https://agentseal.org/mcp/jpisnice-shadcn-ui-mcp-server) |
| [mcp-cli](https://github.com/chrishayuk/mcp-cli) | Model Context Protocolサーバーと対話するためのコマンドラインインターフェース... | 92 ✅ | 1.9k | [表示](https://agentseal.org/mcp/https-githubcom-chrishayuk-mcp-cli) |
| [ios-simulator-mcp](https://github.com/joshuayoes/ios-simulator-mcp) | iOSシミュレーターと対話するためのMCPサーバー | 91 ✅ | 1.7k | [表示](https://agentseal.org/mcp/https-githubcom-joshuayoes-ios-simulator-mcp) |
| [mcp-installer](https://github.com/anaisbetts/mcp-installer) | 他のMCPサーバーをインストールするMCPサーバー | 89 ✅ | 1.5k | [表示](https://agentseal.org/mcp/anaisbetts-mcp-installer) |
| [notebooklm-mcp](https://github.com/pleaseprompto/notebooklm-mcp) | NotebookLM用MCPサーバー - AIエージェント（Claude Code, Codex）がリサーチ... | 73 ⚠️ | 1.4k | [表示](https://agentseal.org/mcp/https-githubcom-pleaseprompto-notebooklm-mcp) |
| [coderunner](https://github.com/instavm/coderunner) | AIエージェント用ローカルサンドボックス | 80 ⚠️ | 801 | [表示](https://agentseal.org/mcp/https-githubcom-instavm-coderunner) |
| [vibetest-use](https://github.com/browser-use/vibetest-use) | Vibetest MCP - Browser-Useエージェントを使った自動QAテスト | 87 ✅ | 772 | [表示](https://agentseal.org/mcp/https-githubcom-browser-use-vibetest-use) |
| [driftdetect-mcp](https://github.com/dadbodgeoff/drift) | AI向けコードベースインテリジェンス。パターンと規約を検出し、決定事項を記憶... | 85 ✅ | 760 | [表示](https://agentseal.org/mcp/driftdetect-mcp) |
| [just-prompt](https://github.com/disler/just-prompt) | just-promptはトップLLMプロバイダーへの統合インターフェースを提供するMCPサーバー... | 89 ✅ | 719 | [表示](https://agentseal.org/mcp/https-githubcom-disler-just-prompt) |
| [blueprint-mcp](https://github.com/arcadeai/blueprint-mcp) | コードベースとシステムアーキテクチャを理解するための図表生成... | 92 ✅ | 585 | [表示](https://agentseal.org/mcp/https-githubcom-arcadeai-blueprint-mcp) |
| [n8n-workflow-builder](https://github.com/makafeli/n8n-workflow-builder) | Model Context Protocolを通じたn8nワークフロー自動化のAIアシスタント統合... | 87 ✅ | 501 | [表示](https://agentseal.org/mcp/https-githubcom-makafeli-n8n-workflow-builder) |
| [web-agent-protocol](https://github.com/ota-tech-ai/web-agent-protocol) | 🌐Web Agent Protocol (WAP) - ブラウザでのユーザー操作を記録・再生... | 92 ✅ | 493 | [表示](https://agentseal.org/mcp/https-githubcom-ota-tech-ai-web-agent-protocol) |
| [airtable-mcp-server](https://github.com/domdomegg/airtable-mcp-server) | 🗂️🤖 Airtable Model Context Protocolサーバー。AIシステムがAirtableと対話可能に... | 81 ✅ | 430 | [表示](https://agentseal.org/mcp/https-githubcom-domdomegg-airtable-mcp-server) |
| [kicad-mcp](https://github.com/lamaalrajih/kicad-mcp) | Mac、Windows、Linux対応のKiCad用Model Context Protocolサーバー | 92 ✅ | 401 | [表示](https://agentseal.org/mcp/https-githubcom-lamaalrajih-kicad-mcp) |
| [lingti-bot](https://github.com/ruilisi/lingti-bot) | 🐕⚡「極簡至上 効率為王 秒級接入 一鏈即用」的 AI Bot | 75 ⚠️ | 368 | [表示](https://agentseal.org/mcp/https-githubcom-ruilisi-lingti-bot) |
| [MemoryMesh](https://github.com/CheMiguel23/MemoryMesh) | Model Context Protocol (MCP)を使用してナレッジグラフサーバーを提供... | 81 ✅ | 335 | [表示](https://agentseal.org/mcp/https-githubcom-chemiguel23-memorymesh) |
| [paws-on-mcp](https://github.com/hemanth/paws-on-mcp) | 最新仕様を実装した包括的なModel Context Protocol (MCP)サーバー... | 86 ✅ | 331 | [表示](https://agentseal.org/mcp/https-githubcom-hemanth-paws-on-mcp) |
| [moling](https://github.com/gojue/moling) | MoLingはコンピュータ操作とブラウザ操作ベースのMCPサーバー。ローカルにデプロイ... | 78 ⚠️ | 330 | [表示](https://agentseal.org/mcp/https-githubcom-gojue-moling) |
| [consult7](https://github.com/szeider/consult7) | 大規模コンテキストサイズの言語モデルに相談するためのMCPサーバー | 85 ✅ | 291 | [表示](https://agentseal.org/mcp/https-githubcom-szeider-consult7) |
| [chrome-devtools-mcp](https://github.com/benjaminr/chrome-devtools-mcp) | Chrome DevTools Protocol準拠のChrome DevTools用MCPサーバー... | 74 ⚠️ | 289 | [表示](https://agentseal.org/mcp/https-githubcom-benjaminr-chrome-devtools-mcp) |
| [FileScopeMCP](https://github.com/admica/FileScopeMCP) | 依存関係に基づいてコードベースの重要なファイルを特定して分析... | 82 ✅ | 283 | [表示](https://agentseal.org/mcp/https-githubcom-admica-filescopemcp) |
| [MCP-Server-Playwright](https://github.com/Automata-Labs-team/MCP-Server-Playwright) | 完全なリモート制御を提供するPlaywrightベースのブラウザ自動化MCPサーバー... | 74 ⚠️ | 283 | [表示](https://agentseal.org/mcp/https-githubcom-automata-labs-team-mcp-server-playwright) |
| [mcp-reasoner](https://github.com/jacck/mcp-reasoner) | ビームサーチ付きClaude Desktop向け体系的推論MCPサーバー実装... | 92 ✅ | 277 | [表示](https://agentseal.org/mcp/https-githubcom-jacck-mcp-reasoner) |
| [lucid](https://github.com/get-lucid/lucid) | 検証済みのリアルタイム知識で自律エージェントを基盤づけるインテリジェンスレイヤー... | 92 ✅ | 260 | [表示](https://agentseal.org/mcp/https-githubcom-get-lucid-lucid) |
| [weather-mcp-server](https://github.com/tuankiri/weather-mcp-server) | AIアシスタントが任意の場所のリアルタイム気象データを取得できるMCPサーバー... | 92 ✅ | 239 | [表示](https://agentseal.org/mcp/https-githubcom-tuankiri-weather-mcp-server) |
| [frida-mcp](https://github.com/dnakov/frida-mcp) | Frida用MCP stdioサーバー | 91 ✅ | 237 | [表示](https://agentseal.org/mcp/https-githubcom-dnakov-frida-mcp) |
| [tmux-mcp](https://github.com/nickgnd/tmux-mcp) | ターミナルマルチプレクサtmux用のMCPサーバー。 | 83 ✅ | 235 | [表示](https://agentseal.org/mcp/https-githubcom-nickgnd-tmux-mcp) |
| [tmux-mcp](https://github.com/nickgnd/tmux-mcp) | ターミナルマルチプレクサtmux用のMCPサーバー。 | 83 ✅ | 235 | [表示](https://agentseal.org/mcp/tmux-mcp) |
| [overseer](https://github.com/dmmulroy/overseer) | エージェントタスク管理のためのCLI & Codemode MCPサーバー | 92 ✅ | 222 | [表示](https://agentseal.org/mcp/https-githubcom-dmmulroy-overseer) |
| [mcp-taskmanager](https://github.com/kazuph/mcp-taskmanager) | Claudeがキューベースでタスクを管理・実行できるMCPサーバー... | 91 ✅ | 212 | [表示](https://agentseal.org/mcp/kazuph-mcp-taskmanager) |
| [opik-mcp](https://github.com/comet-ml/opik-mcp) | Opik向けModel Context Protocol (MCP)実装。シームレスなIDE統合を実現... | 92 ✅ | 199 | [表示](https://agentseal.org/mcp/https-githubcom-comet-ml-opik-mcp) |
| [@rocketshipai](https://github.com/rocketship-ai/rocketship) | コーディングエージェントがテストを記述・実行できるオープンソースQAテストフレームワーク... | 92 ✅ | 182 | [表示](https://agentseal.org/mcp/rocketshipai) |
| [anki-mcp-server](https://github.com/scorzeth/anki-mcp-server) | ローカルのAnkiフラッシュカードアプリと統合するMCPサーバー... | 98 ✅ | 178 | [表示](https://agentseal.org/mcp/https-githubcom-scorzeth-anki-mcp-server) |
| [mcp-doc](https://github.com/meterlong/mcp-doc) | FastMCPベースの強力なWord文書処理サービス。AIアシスタントが文書を操作可能... | 89 ✅ | 173 | [表示](https://agentseal.org/mcp/https-githubcom-meterlong-mcp-doc) |
| [llmctx](https://github.com/khromov/llmctx) | AIコード補完向けにSvelte 5とSvelteKit開発者ドキュメントを提供するMCPエンドポイント... | 92 ✅ | 160 | [表示](https://agentseal.org/mcp/https-githubcom-khromov-llmctx) |
| [mcp-server-langfuse](https://github.com/langfuse/mcp-server-langfuse) | Langfuseプロンプト管理用Model Context Protocol (MCP)サーバー... | 92 ✅ | 158 | [表示](https://agentseal.org/mcp/https-githubcom-langfuse-mcp-server-langfuse) |
| [erickwendel-contributions-mcp](https://github.com/erickwendel/erickwendel-contributions-mcp) | Erick Wendelの貢献を問い合わせるツールを提供するModel Context Protocol (MCP)サーバー... | 92 ✅ | 136 | [表示](https://agentseal.org/mcp/https-githubcom-erickwendel-erickwendel-contributions-mcp) |
| [mcp-server](https://github.com/browserstack/mcp-server) | BrowserStack公式MCPサーバー | 69 ⚠️ | 130 | [表示](https://agentseal.org/mcp/https-githubcom-browserstack-mcp-server) |
| [mcp-server-atlassian-bitbucket](https://github.com/aashari/mcp-server-atlassian-bitbucket) | Atlassian Bitbucket用Node.js/TypeScript MCPサーバー。AIシステム（LLM）が利用可能... | 74 ⚠️ | 127 | [表示](https://agentseal.org/mcp/https-githubcom-aashari-mcp-server-atlassian-bitbucket) |
| [pluggedin-mcp-proxy](https://github.com/VeriTeknik/pluggedin-mcp-proxy) | Plugged.in MCPサーバーは他の全MCPを一つのMCPで管理。 | 81 ✅ | 124 | [表示](https://agentseal.org/mcp/https-githubcom-veriteknik-pluggedin-mcp-proxy) |
| [mcp-gdb](https://github.com/signal-slot/mcp-gdb) | AIアシスタントにGDBデバッグ機能を提供するMCPサーバー... | 86 ✅ | 110 | [表示](https://agentseal.org/mcp/https-githubcom-signal-slot-mcp-gdb) |
| [sourcerer-mcp](https://github.com/st3v3nmw/sourcerer-mcp) | トークン消費を削減するセマンティックコード検索・ナビゲーション用MCP | 86 ✅ | 108 | [表示](https://agentseal.org/mcp/https-githubcom-st3v3nmw-sourcerer-mcp) |
| [lapras-mcp-server](https://github.com/lapras-inc/lapras-mcp-server) | lapras.com 公式MCPサーバー | 89 ✅ | 100 | [表示](https://agentseal.org/mcp/https-githubcom-lapras-inc-lapras-mcp-server) |
| [terminal-controller-mcp](https://github.com/gongrzhe/terminal-controller-mcp) | セキュアなターミナルコマンド実行を可能にするModel Context Protocol (MCP)サーバー... | 80 ⚠️ | 99 | [表示](https://agentseal.org/mcp/https-githubcom-gongrzhe-terminal-controller-mcp) |
| [json-mcp-server](https://github.com/gongrzhe/json-mcp-server) | JSON処理用MCPサーバー | 88 ✅ | 89 | [表示](https://agentseal.org/mcp/https-githubcom-gongrzhe-json-mcp-server) |
| [unreal-mcp](https://github.com/runreal/unreal-mcp) | Unreal Python Remote Executionを使用するUnreal Engine用MCPサーバー | 71 ⚠️ | 82 | [表示](https://agentseal.org/mcp/runreal-unreal-mcp) |
| [mcp-server-circleci](https://github.com/CircleCI-Public/mcp-server-circleci) | Model Context Protocol (MCP)向けの特化型サーバー実装... | 80 ✅ | 80 | [表示](https://agentseal.org/mcp/https-githubcom-circleci-public-mcp-server-circleci) |
| [mcp-server-openai](https://github.com/pierrebrunelle/mcp-server-openai) | MCPプロトコルを使用してClaudeから直接OpenAIモデルに問い合わせ。 | 92 ✅ | 79 | [表示](https://agentseal.org/mcp/mcp-server-openai) |
| [multi-ai-advisor-mcp](https://github.com/yuchenssr/multi-ai-advisor-mcp) | 意思決定のためのモデル評議会 | 92 ✅ | 78 | [表示](https://agentseal.org/mcp/https-githubcom-yuchenssr-multi-ai-advisor-mcp) |
| [roundtable](https://github.com/askbudi/roundtable) | 複数のAIコーディングアシスタント（Claude, Gemini等）を調整するローカルMCPサーバー... | 81 ✅ | 78 | [表示](https://agentseal.org/mcp/https-githubcom-askbudi-roundtable) |
| [unifai-sdk-js](https://github.com/unifai-network/unifai-sdk-js) | UnifaiのJavascript/Typescript SDK。AIネイティブプラットフォーム... | 86 ✅ | 75 | [表示](https://agentseal.org/mcp/https-githubcom-unifai-network-unifai-sdk-js) |
| [energyplus-mcp](https://github.com/lbnl-eta/energyplus-mcp) | AIアシスタントとエージェントにEnergyPlusを提供する初のオープンソースModel Context Protocolサーバー... | 90 ✅ | 69 | [表示](https://agentseal.org/mcp/https-githubcom-lbnl-eta-energyplus-mcp) |
| [alibabacloud-devops-mcp-server](https://github.com/aliyun/alibabacloud-devops-mcp-server) | Yunxiao MCPサーバーはAIアシスタントにDevOpsプラットフォームとの対話機能を提供... | 87 ✅ | 69 | [表示](https://agentseal.org/mcp/https-githubcom-aliyun-alibabacloud-devops-mcp-server) |
| [clarity-mcp-server](https://github.com/microsoft/clarity-mcp-server) | Microsoft Clarity用Model Context Protocol (MCP)サーバー | 84 ✅ | 68 | [表示](https://agentseal.org/mcp/microsoft-clarity-mcp-server) |
| [deepseek-thinker-mcp](https://github.com/ruixingshi/deepseek-thinker-mcp) | OpenAI API互換でDeepseekの推論プロセスにアクセスできるMCPサーバー... | 92 ✅ | 67 | [表示](https://agentseal.org/mcp/https-githubcom-ruixingshi-deepseek-thinker-mcp) |
| [xiaozhi-autoglm-mcp](https://github.com/xinnan-tech/xiaozhi-autoglm-mcp) | AIによるAndroidデバイス自動化・モバイルエージェント制御のMCPサーバー... | 92 ✅ | 64 | [表示](https://agentseal.org/mcp/https-githubcom-xinnan-tech-xiaozhi-autoglm-mcp) |
| [mcp-miro](https://github.com/k-jarzyna/mcp-miro) | Model Context Protocol向けMiro統合 | 84 ✅ | 62 | [表示](https://agentseal.org/mcp/https-githubcom-k-jarzyna-mcp-miro) |
| [mcp-server-atlassian-jira](https://github.com/aashari/mcp-server-atlassian-jira) | Atlassian Jira用Node.js/TypeScript MCPサーバー。AIシステム（LLM）に機能を提供... | 80 ⚠️ | 60 | [表示](https://agentseal.org/mcp/https-githubcom-aashari-mcp-server-atlassian-jira) |
| [gdb-mcp](https://github.com/smadi0x86/gdb-mcp) | GDBとLLDB向けのデバッグ機能を提供するマルチデバッガーMCPサーバー... | 86 ✅ | 56 | [表示](https://agentseal.org/mcp/https-githubcom-smadi0x86-gdb-mcp) |
| [whois-mcp](https://github.com/bharathvaj-ganesan/whois-mcp) | WHOIS検索用MCPサーバー。 | 92 ✅ | 52 | [表示](https://agentseal.org/mcp/https-githubcom-bharathvaj-ganesan-whois-mcp) |
| [webpage-screenshot-mcp](https://github.com/ananddtyagi/webpage-screenshot-mcp) | Puppeteerを使用してWebページのスクリーンショットをキャプチャするMCPサーバー。AIが利用可能... | 87 ✅ | 52 | [表示](https://agentseal.org/mcp/https-githubcom-ananddtyagi-webpage-screenshot-mcp) |
| [iphone-mcp](https://github.com/blitzdotdev/iphone-mcp) | AIがiPhoneを操作できるMCPサーバー | 86 ✅ | 50 | [表示](https://agentseal.org/mcp/blitzdev-iphone-mcp) |
| [random-number-mcp](https://github.com/zazencodes/random-number-mcp) | LLMに必要なランダム生成機能を提供する本番環境対応MCPサーバー... | 90 ✅ | 47 | [表示](https://agentseal.org/mcp/https-githubcom-zazencodes-random-number-mcp) |
| [shadowgit-mcp](https://github.com/blade47/shadowgit-mcp) | AIアシスタントにセキュアなGit操作を提供するModel Context Protocol (MCP)サーバー... | 85 ✅ | 46 | [表示](https://agentseal.org/mcp/https-githubcom-blade47-shadowgit-mcp) |
| [xray](https://github.com/srijanshukla18/xray) | XRAY MCPはAIコーディングエージェント向けの段階的コードインテリジェンスとナビゲーション機能を提供... | 82 ✅ | 46 | [表示](https://agentseal.org/mcp/https-githubcom-srijanshukla18-xray) |
| [frida-game-hacking-mcp](https://github.com/0xhackerfren/frida-game-hacking-mcp) | Cheat Engineの機能をエミュレートするFridaのMCP実装... | 71 ⚠️ | 46 | [表示](https://agentseal.org/mcp/https-githubcom-0xhackerfren-frida-game-hacking-mcp) |
| [mcp_weather_server](https://github.com/isdaniel/mcp_weather_server) | 現在の天気予報、大気質データを提供する読み取り専用MCPサーバー... | 100 ✅ | 44 | [表示](https://agentseal.org/mcp/https-githubcom-isdaniel-mcpweatherserver) |
| [mcp-server-taskwarrior](https://github.com/awwaiid/mcp-server-taskwarrior) | エージェントがタスクの一覧表示、追加、完了を行えるTaskwarrior MCPサーバー... | 91 ✅ | 44 | [表示](https://agentseal.org/mcp/https-githubcom-awwaiid-mcp-server-taskwarrior) |
| [mobile-dev-mcp-server](https://github.com/jsuarezruiz/mobile-dev-mcp-server) | モバイルデバイスやシミュレーターの管理・操作用に設計されたMCP... | 83 ✅ | 42 | [表示](https://agentseal.org/mcp/https-githubcom-jsuarezruiz-mobile-dev-mcp-server) |
| [powertools-mcp](https://github.com/aws-powertools/powertools-mcp) | Powertools for AWS公式MCPサーバー | 88 ✅ | 41 | [表示](https://agentseal.org/mcp/https-githubcom-aws-powertools-powertools-mcp) |
| [dynamic-shell-server](https://github.com/codelion/dynamic-shell-server) | 動的シェルコマンドMCPサーバー | 86 ✅ | 41 | [表示](https://agentseal.org/mcp/https-githubcom-codelion-dynamic-shell-server) |
| [unreal-api-mcp](https://github.com/Codeturion/unreal-api-mcp) | エージェントがUnreal Engineの公式ドキュメントを検索・取得できる読み取り専用リファレンスサーバー... | 93 ✅ | 40 | [表示](https://agentseal.org/mcp/https-githubcom-codeturion-unreal-api-mcp) |
| [test-coverage-mcp](https://github.com/goldbergyoni/test-coverage-mcp) | コンテキストエンジニアリング: エージェントが🧪テストカバレッジに与える影響を認識... | 89 ✅ | 40 | [表示](https://agentseal.org/mcp/https-githubcom-goldbergyoni-test-coverage-mcp) |
| [mcp-tasks](https://github.com/flesler/mcp-tasks) | マルチフォーマット対応の包括的で効率的なタスク管理MCPサーバー... | 91 ✅ | 39 | [表示](https://agentseal.org/mcp/https-githubcom-flesler-mcp-tasks) |
| [anki-mcp](https://github.com/nietus/anki-mcp) | フラッシュカードの作成、更新、復習が可能なAnki管理サーバー... | 75 ⚠️ | 39 | [表示](https://agentseal.org/mcp/https-githubcom-nietus-anki-mcp) |
| [mcp](https://github.com/screenshotone/mcp) | ScreenshotOne API向けMCPサーバーのシンプルな実装 | 88 ✅ | 35 | [表示](https://agentseal.org/mcp/https-githubcom-screenshotone-mcp) |
| [package-registry-mcp](https://github.com/artmann/package-registry-mcp) | NPM、Cargo等のパッケージの最新情報を検索・取得するMCPサーバー... | 86 ✅ | 35 | [表示](https://agentseal.org/mcp/package-registry-mcp) |
| [kilntainers](https://github.com/kiln-ai/kilntainers) | 各エージェントにシェルコマンド実行用のエフェメラルLinuxサンドボックスを提供するMCPサーバー... | 85 ✅ | 34 | [表示](https://agentseal.org/mcp/https-githubcom-kiln-ai-kilntainers) |
| [actor-critic-thinking-mcp](https://github.com/aquarius-wing/actor-critic-thinking-mcp) | Model Context Protocol (MCP)ベースの二重視点思考分析サーバー... | 100 ✅ | 32 | [表示](https://agentseal.org/mcp/https-githubcom-aquarius-wing-actor-critic-thinking-mcp) |
| [maven-mcp-server](https://github.com/Bigsy/maven-mcp-server) | Mavenの依存関係チェックツールを提供するMCP (Model Context Protocol)サーバー... | 92 ✅ | 31 | [表示](https://agentseal.org/mcp/https-githubcom-bigsy-maven-mcp-server) |
| [PiloTY](https://github.com/yiwenlu66/PiloTY) | PiloTY: MCP経由のPTY操作用AIパイロット - AIエージェントがインタラクティブ端末を制御... | 74 ⚠️ | 30 | [表示](https://agentseal.org/mcp/https-githubcom-yiwenlu66-piloty) |
| [splunk-mcp-server2](https://github.com/splunk/splunk-mcp-server2) | 非公式。Splunk MCPサーバー。PythonとTypeScript/JSで実装... | 86 ✅ | 29 | [表示](https://agentseal.org/mcp/https-githubcom-splunk-splunk-mcp-server2) |
| [mcpcap](https://github.com/mcpcap/mcpcap) | 特化型アナライザーによるネットワークパケットキャプチャ分析用モジュラーPython MCPサーバー... | 75 ⚠️ | 28 | [表示](https://agentseal.org/mcp/https-githubcom-mcpcap-mcpcap) |
| [mcp-simple-timeserver](https://github.com/andybrandt/mcp-simple-timeserver) | ローカル時間、NTP経由UTC、タイムゾーン変換を提供する時刻・日付ユーティリティMCPサーバー... | 92 ✅ | 27 | [表示](https://agentseal.org/mcp/https-githubcom-andybrandt-mcp-simple-timeserver) |
| [gemini-cli-orchestrator](https://github.com/dnnyngyen/gemini-cli-orchestrator) | Claude CodeがGeminiを分析・コンテンツ生成にオーケストレートできるMCPサーバー... | 91 ✅ | 25 | [表示](https://agentseal.org/mcp/https-githubcom-dnnyngyen-gemini-cli-orchestrator) |
| [ScreenshotMCP](https://github.com/upnorthmedia/ScreenshotMCP) | フル機能のWebサイトスクリーンショットキャプチャ用Model Context Protocol MCPサーバー... | 88 ✅ | 25 | [表示](https://agentseal.org/mcp/https-githubcom-upnorthmedia-screenshotmcp) |
| [mcp-task-orchestrator](https://github.com/EchoingVesper/mcp-task-orchestrator) | タスクオーケストレーション機能を提供するModel Context Protocolサーバー... | 88 ✅ | 24 | [表示](https://agentseal.org/mcp/https-githubcom-echoingvesper-mcp-task-orchestrator) |
| [code-memory](https://github.com/kapillamba4/code-memory) | ベクトル埋め込みによるコードベースのローカルセマンティック検索。テレメトリゼロ... | 72 ⚠️ | 24 | [表示](https://agentseal.org/mcp/https-githubcom-kapillamba4-code-memory) |
| [anti-bullshit-mcp-server](https://github.com/bmorphism/anti-bullshit-mcp-server) | 主張の分析、情報源の検証、操作検出のためのMCPサーバー... | 92 ✅ | 23 | [表示](https://agentseal.org/mcp/https-githubcom-bmorphism-anti-bullshit-mcp-server) |
| [blowback-context](https://github.com/esnark/blowback) | AIツールと統合するフロントエンド開発環境向けMCPサーバー... | 87 ✅ | 22 | [表示](https://agentseal.org/mcp/blowback-context) |
| [create-mcp-ts](https://github.com/stephencme/create-mcp-ts) | TypeScriptで新しいMCPサーバーを作成。バッテリー付き。 | 91 ✅ | 21 | [表示](https://agentseal.org/mcp/https-githubcom-stephencme-create-mcp-ts) |
| [mcpretentious](https://github.com/oetiker/mcpretentious) | iTerm2端末を操縦する強力なModel Context Protocol (MCP)サーバー。 | 88 ✅ | 21 | [表示](https://agentseal.org/mcp/https-githubcom-oetiker-mcpretentious) |
| [securitycopilotmcpserver](https://github.com/jguimera/securitycopilotmcpserver) | Security Copilot、Sentinel等のツールと統合するMCPサーバー... | 82 ✅ | 20 | [表示](https://agentseal.org/mcp/https-githubcom-jguimera-securitycopilotmcpserver) |
| [termlink](https://github.com/chu2bard/termlink) | シェルおよびターミナル操作用MCPサーバー | 91 ✅ | 19 | [表示](https://agentseal.org/mcp/https-githubcom-chu2bard-termlink) |
| [hyperbolic-mcp](https://github.com/HyperbolicLabs/hyperbolic-mcp) | ClaudeがHyperbolicのGPUクラウドと対話し、GPU情報の表示等を行えるMCPサーバー... | 86 ✅ | 19 | [表示](https://agentseal.org/mcp/https-githubcom-hyperboliclabs-hyperbolic-mcp) |
| [anki-connect-mcp](https://github.com/spacholski1225/anki-connect-mcp) | Anki Web向けカスタムModel Context Protocol (MCP)実装。シームレスな統合を実現... | 80 ⚠️ | 18 | [表示](https://agentseal.org/mcp/https-githubcom-spacholski1225-anki-connect-mcp) |
| [alertmanager-mcp-server](https://github.com/ntk148v/alertmanager-mcp-server) | AIアシスタントがAlertmanagerと統合できるModel Context Protocol (MCP)サーバー... | 87 ✅ | 16 | [表示](https://agentseal.org/mcp/https-githubcom-ntk148v-alertmanager-mcp-server) |
| [mcp_server_pcileech](https://github.com/evan7198/mcp_server_pcileech) | pcileechを使用して他のPCのメモリを読み書きするシンプルなMCPサーバー | 85 ✅ | 16 | [表示](https://agentseal.org/mcp/https-githubcom-evan7198-mcpserverpcileech) |
| [Autogen_MCP](https://github.com/DynamicEndpoints/Autogen_MCP) | Microsoft AutoGenエージェントの作成・設定・実行を可能にするMCPサーバー... | 76 ⚠️ | 16 | [表示](https://agentseal.org/mcp/https-githubcom-dynamicendpoints-autogenmcp) |
| [npm-search-mcp-server](https://github.com/btwiuse/npm-search-mcp-server) | npmパッケージ検索用MCPサーバー | 92 ✅ | 15 | [表示](https://agentseal.org/mcp/https-githubcom-btwiuse-npm-search-mcp-server) |
| [android-mcp-server](https://github.com/jiantao88/android-mcp-server) | Android MCPサーバーの実装 | 87 ✅ | 15 | [表示](https://agentseal.org/mcp/https-githubcom-jiantao88-android-mcp-server) |
| [networksdb-mcp](https://github.com/mordavid/networksdb-mcp) | NetworksDB APIの高速MCP統合 - IPアドレス、組織等の問い合わせ... | 86 ✅ | 15 | [表示](https://agentseal.org/mcp/https-githubcom-mordavid-networksdb-mcp) |
| [context-crystallizer](https://github.com/hubertciebiada/context-crystallizer) | 大規模リポジトリをAI消費可能なナレッジベースに結晶化・変換... | 82 ✅ | 15 | [表示](https://agentseal.org/mcp/https-githubcom-hubertciebiada-context-crystallizer) |
| [agentops-mcp](https://github.com/AgentOps-AI/agentops-mcp) | AgentOpsエージェントテレメトリを照会するMCPサーバー - APIキーで認可... | 96 ✅ | 14 | [表示](https://agentseal.org/mcp/https-githubcom-agentops-ai-agentops-mcp) |
| [argus-mcp](https://github.com/lokafinnsw/argus-mcp) | ゼロトラストアプローチのAIコードレビューMCPサーバー。マルチモデル対応、キャッシュ... | 92 ✅ | 14 | [表示](https://agentseal.org/mcp/https-githubcom-lokafinnsw-argus-mcp) |
| [mcp-time](https://github.com/TheoBrigitte/mcp-time) | 時刻の操作ユーティリティを提供するMCP (Model Context Protocol)サーバー... | 89 ✅ | 14 | [表示](https://agentseal.org/mcp/theofoobar-mcp-time) |
| [currents-mcp](https://github.com/currents-dev/currents-mcp) | Currents MCPサーバー | 84 ✅ | 14 | [表示](https://agentseal.org/mcp/https-githubcom-currents-dev-currents-mcp) |
| [domain-tools-mcp-server](https://github.com/deshabhishek007/domain-tools-mcp-server) | ドメインの包括的分析（WHOIS等）用Model Context Protocol (MCP)サーバー... | 92 ✅ | 13 | [表示](https://agentseal.org/mcp/https-githubcom-deshabhishek007-domain-tools-mcp-server) |
| [riza-mcp](https://github.com/riza-io/riza-mcp) | Riza APIによるLLM生成コードの分離コードインタープリター。ツール管理付き... | 91 ✅ | 13 | [表示](https://agentseal.org/mcp/https-githubcom-riza-io-riza-mcp) |
| [qrcode_mcp](https://github.com/2niuhe/qrcode_mcp) | QRコード生成用MCPツール | 91 ✅ | 12 | [表示](https://agentseal.org/mcp/https-githubcom-2niuhe-qrcodemcp) |
| [d.i.e-mcp](https://github.com/lazy-importer/d.i.e-mcp) | DIE (Detect It Easy)用MCPサーバー | 92 ✅ | 11 | [表示](https://agentseal.org/mcp/https-githubcom-lazy-importer-die-mcp) |
| [mcp-go-debugger](https://github.com/sunfmin/mcp-go-debugger) | MCPと統合されたGoデバッガー。起動、アタッチ、ブレークポイント設定が可能... | 88 ✅ | 11 | [表示](https://agentseal.org/mcp/https-githubcom-sunfmin-mcp-go-debugger) |
| [teamcity-mcp](https://github.com/itcaat/teamcity-mcp) | TeamCity MCPサーバー | 86 ✅ | 11 | [表示](https://agentseal.org/mcp/https-githubcom-itcaat-teamcity-mcp) |
| [kylas-crm-mcp-server](https://github.com/kylastech/kylas-crm-mcp-server) | Kylasの作成・更新・検索等を可能にするCRM統合サーバー... | 67 ⚠️ | 11 | [表示](https://agentseal.org/mcp/https-githubcom-kylastech-kylas-crm-mcp-server) |
| [memory-mcp](https://github.com/chenxiaofie/memory-mcp) | メッセージのキャッシュ、タスクエピソード管理を行うローカル会話メモリシステム... | 91 ✅ | 10 | [表示](https://agentseal.org/mcp/https-githubcom-chenxiaofie-memory-mcp) |
| [mcp-gitlab-jira](https://github.com/HainanZhao/mcp-gitlab-jira) | GitLabとJiraの統合MCPサーバー。AIエージェントがこれらのサービスと対話可能... | 92 ✅ | 9 | [表示](https://agentseal.org/mcp/mcp-gitlab-jira) |
| [pyxel-mcp](https://github.com/kitao/pyxel-mcp) | Pyxelレトロゲームスクリプトを実行し、視覚・音声情報を提供するMCPサーバー... | 79 ⚠️ | 9 | [表示](https://agentseal.org/mcp/https-githubcom-kitao-pyxel-mcp) |
| [mcp-agentic-framework](https://github.com/Piotr1215/mcp-agentic-framework) | AIエージェントの登録、発見、連携を可能にするマルチエージェント調整フレームワーク... | 78 ⚠️ | 9 | [表示](https://agentseal.org/mcp/https-githubcom-piotr1215-mcp-agentic-framework) |
| [canvas-lms-mcp](https://github.com/ahnopologetic/canvas-lms-mcp) | AIシステムとCanvas LMSを橋渡しし、教育データへのアクセスを提供するMCPサーバー... | 89 ✅ | 7 | [表示](https://agentseal.org/mcp/https-githubcom-ahnopologetic-canvas-lms-mcp) |
| [mcp-project-manager](https://github.com/croffasia/mcp-project-manager) | 🚀 Model Context Protocol (MCP)による階層的タスク管理サーバー。作成... | 88 ✅ | 7 | [表示](https://agentseal.org/mcp/https-githubcom-croffasia-mcp-project-manager) |
| [mcp-server-adb](https://github.com/watabee/mcp-server-adb) | Android Debug Bridge (ADB)用MCPサーバー。ClaudeがAndroidデバイスと対話可能... | 87 ✅ | 7 | [表示](https://agentseal.org/mcp/https-githubcom-watabee-mcp-server-adb) |
| [piston-mcp](https://github.com/alvii147/piston-mcp) | Pistonリモートコード実行エンジンを使用して複数のプログラミング言語で任意のコードを実行... | 84 ✅ | 7 | [表示](https://agentseal.org/mcp/https-githubcom-alvii147-piston-mcp) |
| [sonatype-mcp](https://github.com/brianveltman/sonatype-mcp) | Sonatype Nexus Repository Manager用MCPサーバー | 84 ✅ | 7 | [表示](https://agentseal.org/mcp/https-githubcom-brianveltman-sonatype-mcp) |
| [skill-ninja-mcp-server](https://github.com/aktsmm/skill-ninja-mcp-server) | SKILL.mdファイルの検索・インストール・管理を行うエージェントスキルパッケージマネージャー... | 76 ⚠️ | 7 | [表示](https://agentseal.org/mcp/https-githubcom-aktsmm-skill-ninja-mcp-server) |
| [mcp-idb](https://github.com/noahlozevski/mcp-idb) | fb-idbブリッジ用MCPサーバー。 | 86 ✅ | 6 | [表示](https://agentseal.org/mcp/noahlozevski-mcp-idb) |
| [spm-mcp](https://github.com/simpleswift/spm-mcp) | Swiftで書かれたSwift Package Manager MCPサーバー | 85 ✅ | 6 | [表示](https://agentseal.org/mcp/simpleswift-spm-mcp) |
| [public-apis-mcp](https://github.com/zazencodes/public-apis-mcp) | MCPを使って無料APIを検索 | 85 ✅ | 6 | [表示](https://agentseal.org/mcp/https-githubcom-zazencodes-public-apis-mcp) |
| [reexpress_mcp_server](https://github.com/ReexpressAI/reexpress_mcp_server) | Reexpress Model-Context-Protocol (MCP)サーバー | 82 ✅ | 6 | [表示](https://agentseal.org/mcp/https-githubcom-reexpressai-reexpressmcpserver) |
| [mcpgex](https://github.com/patzedi/mcpgex) | 正規表現パターンの検索・テスト・改良用MCPサーバー | 92 ✅ | 5 | [表示](https://agentseal.org/mcp/https-githubcom-patzedi-mcpgex) |
| [mcp-sandbox](https://github.com/danstarns/mcp-sandbox) | 任意のJavaScriptモジュールを自動リフレクション付きサンドボックスMCPサーバーに変換... | 92 ✅ | 5 | [表示](https://agentseal.org/mcp/https-githubcom-danstarns-mcp-sandbox) |
| [mcp-grep](https://github.com/247arjun/mcp-grep) | grep CLIツールのMCPサーバーラッパー | 87 ✅ | 5 | [表示](https://agentseal.org/mcp/https-githubcom-247arjun-mcp-grep) |
| [log-analyzer-mcp](https://github.com/Fato07/log-analyzer-mcp) | 各種フォーマットのログファイルの解析・検索・デバッグ用MCPサーバー... | 81 ✅ | 5 | [表示](https://agentseal.org/mcp/https-githubcom-fato07-log-analyzer-mcp) |
| [time-mcp-pypi.git](https://github.com/domdomegg/time-mcp-pypi.git) | 現在のUTC日時を取得するツールを提供する最小限のPython MCPサーバー... | 92 ✅ | 4 | [表示](https://agentseal.org/mcp/https-githubcom-domdomegg-time-mcp-pypigit) |
| [sonarcloud-mcp](https://github.com/dozzman/sonarcloud-mcp) | 課題取得用sonarcloud/sonarqubeクラウドMCPサーバー | 92 ✅ | 4 | [表示](https://agentseal.org/mcp/https-githubcom-dozzman-sonarcloud-mcp) |
| [aria-validate-mcp-server](https://github.com/yamanoku/aria-validate-mcp-server) | ARIA（Accessible Rich Internet Applications）属性を検証するModel Context Protocolサーバー... | 92 ✅ | 4 | [表示](https://agentseal.org/mcp/https-githubcom-yamanoku-aria-validate-mcp-server) |
| [node-code-sandbox-mcp](https://github.com/mozicim/node-code-sandbox-mcp) | 🐢🚀 Node.jsサンドボックスMCPサーバー。MCPを実装するNode.jsサーバー... | 77 ⚠️ | 4 | [表示](https://agentseal.org/mcp/node-code-sandbox-mcp) |
| [conan-mcp](https://github.com/conan-io/conan-mcp) | Conanパッケージマネージャー用Model Context Protocolサーバー。プロジェクト作成を実現... | 77 ⚠️ | 4 | [表示](https://agentseal.org/mcp/https-githubcom-conan-io-conan-mcp) |
| [mcp-refactoring.git](https://github.com/marshally/mcp-refactoring.git) | Fowlerスタイルのコードリファクタリングの一覧・プレビュー・適用が可能なMCPサーバー... | 92 ✅ | 3 | [表示](https://agentseal.org/mcp/https-githubcom-marshally-mcp-refactoringgit) |
| [mcp-postman](https://github.com/freebeiro/mcp-postman) | Postman統合用にCloudflare Workersで構築されたModel Context Protocol (MCP)サーバー... | 92 ✅ | 3 | [表示](https://agentseal.org/mcp/mcp-postman) |
| [context-rot-detection](https://github.com/milos-product-maker/context-rot-detection) | AIエージェントに認知健全性のリアルタイム可視性を提供するMCPサービス... | 92 ✅ | 3 | [表示](https://agentseal.org/mcp/https-githubcom-milos-product-maker-context-rot-detection) |
| [cfr_mcp_server](https://github.com/mr-xn/cfr_mcp_server) | PythonベースのMCP (Model Context Protocol)サーバー実装。`cfr.jar`逆コンパイル機能をラップ... | 92 ✅ | 3 | [表示](https://agentseal.org/mcp/https-githubcom-mr-xn-cfrmcpserver) |
| [krs-poland-mcp-server](https://github.com/pkolawa/krs-poland-mcp-server) | ポーランドKRS公開API用MCPサーバー。 | 92 ✅ | 3 | [表示](https://agentseal.org/mcp/https-githubcom-pkolawa-krs-poland-mcp-server) |
| [mcp-ghidra5-windows](https://github.com/thestingr/mcp-ghidra5-windows) | 🏢 GPT-5搭載Ghidraリバースエンジニアリング用エンタープライズWindowsサービス... | 92 ✅ | 3 | [表示](https://agentseal.org/mcp/https-githubcom-thestingr-mcp-ghidra5-windows) |
| [math-mcp-learning-server](https://github.com/clouatre-labs/math-mcp-learning-server) | 算術、行列代数等17の数学ツールを備えた教育用MCPサーバー... | 84 ✅ | 3 | [表示](https://agentseal.org/mcp/https-githubcom-clouatre-labs-math-mcp-learning-server) |
| [mcp-relay](https://github.com/mhcoen/mcp-relay) | Claude DesktopとClaude Codeが不透明なメッセージを受け渡せるメッセージリレーバッファ... | 79 ⚠️ | 3 | [表示](https://agentseal.org/mcp/https-githubcom-mhcoen-mcp-relay) |
| [snowfakery-mcp](https://github.com/composable-delivery/snowfakery-mcp) | リアルなフェイクデータ生成ツールSnowfakeryをラップするMCPサーバー... | 76 ⚠️ | 3 | [表示](https://agentseal.org/mcp/https-githubcom-composable-delivery-snowfakery-mcp) |
| [memory-mcp](https://github.com/michael-denyer/memory-mcp) | 即時想起のためのホットキャッシュを備えたAIアシスタント向け永続メモリシステム... | 71 ⚠️ | 3 | [表示](https://agentseal.org/mcp/https-githubcom-michael-denyer-memory-mcp) |
| [selenium-selfhealing-mcp](https://github.com/aiqualitylab/selenium-selfhealing-mcp) | UI変更時に壊れたSeleniumテストロケーターを自動修正するMCPサーバー... | 92 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-aiqualitylab-selenium-selfhealing-mcp) |
| [mcp-agile-luminary](https://github.com/AgileLuminary/mcp-agile-luminary) | Agile Luminaryプロジェクト管理アプリケーションと接続するMCPサーバー | 92 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-agileluminary-mcp-agile-luminary) |
| [frida-mcp](https://github.com/rmorgans/frida-mcp) | AIシステムがアプリケーションを動的に計測・分析できるFrida用MCPサーバー... | 91 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-rmorgans-frida-mcp) |
| [clix-mcp-server](https://github.com/clix-so/clix-mcp-server) | Clix MCPサーバーはAIエージェントにリアルタイムで信頼できるClixドキュメントを提供... | 89 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-clix-so-clix-mcp-server) |
| [mcp-page-capture](https://github.com/chasesaurabh/mcp-page-capture) | Webページのスクリーンショットをキャプチャし、自動化用のMCP互換メタデータを返却... | 88 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-chasesaurabh-mcp-page-capture) |
| [ctfd-mcp-server](https://github.com/mrjamescot/ctfd-mcp-server) | AIエージェントとCTFdインスタンスを接続するMCP設定。 | 88 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-mrjamescot-ctfd-mcp-server) |
| [coderide-mcp](https://github.com/PixdataOrg/coderide-mcp) | AIコーディングエージェント向けプロジェクト・タスク管理MCPサーバー。取得を実現... | 85 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-pixdataorg-coderide-mcp) |
| [github-projects-mcp](https://github.com/redducklabs/github-projects-mcp) | GitHub GraphQL APIをラップしたGitHub Projects v2管理サーバー... | 82 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-redducklabs-github-projects-mcp) |
| [tools](https://github.com/the-basilisk-ai/squad-mcp) | ClaudeやCursorと統合するAI搭載プロダクト発見・戦略プラットフォーム... | 81 ✅ | 2 | [表示](https://agentseal.org/mcp/squadai-tools) |
| [xctools-mcp-server](https://github.com/nzrsky/xctools-mcp-server) | 各種Xcode関連ツール用のModel Context Protocolサーバー | 81 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-nzrsky-xctools-mcp-server) |
| [terminal-mcp](https://github.com/mkpvishnu/terminal-mcp) | インタラクティブなターミナルセッション用MCPサーバー: SSH、REPL、データベースCLI等... | 81 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-mkpvishnu-terminal-mcp) |
| [agentic-store-mcp](https://github.com/agenticstore/agentic-store-mcp) | AgenticStoreの無料オープンソースMCPツールでAIエージェントに超能力を... | 75 ⚠️ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-agenticstore-agentic-store-mcp) |
| [physbound](https://github.com/JonesRobM/physbound) | リンクバジェット、Shannon-Hartley容量等を計算するRF/物理検証MCPサーバー... | 100 ✅ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-jonesrobm-physbound) |
| [char-index-mcp](https://github.com/agent-hanju/char-index-mcp) | 検索、分割、挿入等を提供する純粋な文字列/文字インデックス操作ライブラリ... | 97 ✅ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-agent-hanju-char-index-mcp) |
| [M365-roadmap-mcp-server](https://github.com/jonnybottles/M365-roadmap-mcp-server) | AIエージェントがMicrosoft 365ロードマップをプログラムで照会できるPython MCPサーバー... | 87 ✅ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-jonnybottles-m365-roadmap-mcp-server) |
| [meta-prompt-mcp](https://github.com/kapillamba4/meta-prompt-mcp) | GoogleとAnthropicの公式プロンプティングガイドを取得するリファレンスサーバー... | 84 ✅ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-kapillamba4-meta-prompt-mcp) |
| [mcp-autogen-doc](https://github.com/sykuang/mcp-autogen-doc) | AIアシスタントにドキュメント自動生成機能を提供するModel Context Protocol (MCP)サーバー... | 84 ✅ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-sykuang-mcp-autogen-doc) |
| [nativ-mcp](https://github.com/Nativ-Technologies/nativ-mcp) | ブランドボイスを尊重しながらコンテンツを翻訳するAI搭載ローカライゼーションMCPサーバー... | 84 ✅ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-nativ-technologies-nativ-mcp) |
| [simctl-mcp-server](https://github.com/nzrsky/simctl-mcp-server) | iOS simctl MCPサーバー | 79 ⚠️ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-nzrsky-simctl-mcp-server) |
| [cowork-history](https://github.com/egoughnour/cowork-history) | BM25検索でClaude会話履歴をインデックス・検索するローカルMCPサーバー... | 76 ⚠️ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-egoughnour-cowork-history) |
| [dbgprobe-mcp-server.git](https://github.com/es617/dbgprobe-mcp-server.git) | ハードウェアデバッグプローブによるAI支援組み込みシステムデバッグ用MCPサーバー... | 75 ⚠️ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-es617-dbgprobe-mcp-servergit) |
| [algora-mcp-server](https://github.com/idapixl/algora-mcp-server) | オープンソースバウンティの閲覧・検索・統計取得用読み取り専用MCPサーバー... | 100 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-idapixl-algora-mcp-server) |
| [heatpump-mcp-server](https://github.com/jiweiqi/heatpump-mcp-server) | ヒートポンプシステムのサイジング、比較、評価を支援するMCPサーバー... | 100 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-jiweiqi-heatpump-mcp-server) |
| [fabric-mcp-server](https://github.com/adapoet/fabric-mcp-server) | ユーザーの入力に最適なFabricパターンを推薦するFabric AIパターン推薦サーバー... | 100 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-adapoet-fabric-mcp-server) |
| [time-node-mcp](https://github.com/davidan90/time-node-mcp) | タイムゾーン対応の日時ユーティリティを提供するNode.js MCPサーバー... | 100 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-davidan90-time-node-mcp) |
| [chrono-mcp](https://github.com/JMoak/chrono-mcp) | 現在時刻の取得とタイムゾーン間の変換を行う時刻・タイムゾーンユーティリティMCPサーバー... | 100 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-jmoak-chrono-mcp) |
| [crash-mcp](https://github.com/nikkoxgonzales/crash-mcp) | AIエージェントが複雑な問題を段階的に分解するための構造化推論ステップトラッカー... | 100 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-nikkoxgonzales-crash-mcp) |
| [devops-practices](https://github.com/ai-4-devops/devops-practices) | DevOpsプラクティスドキュメントとフレームワークを提供する読み取り専用ナレッジベースサーバー... | 99 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-ai-4-devops-devops-practices) |
| [mcp-domain-availability](https://github.com/imprvhub/mcp-domain-availability) | 単一のクエリツールでドメイン名の空き状況を確認するMCPサーバー。 | 99 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-imprvhub-mcp-domain-availability) |
| [mcp_server_notify](https://github.com/Cactusinhand/mcp_server_notify) | オプションのサウンドと設定可能なタイムアウト付きでシステムデスクトップ通知を送信。 | 98 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-cactusinhand-mcpservernotify) |
| [agent-domain-service-mcp](https://github.com/gregm711/agent-domain-service-mcp) | ドメイン名の空き状況確認、TLDバリエーションの探索等を行うMCPサーバー... | 98 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-gregm711-agent-domain-service-mcp) |
| [Clojars-MCP-Server](https://github.com/Bigsy/Clojars-MCP-Server) | Clojars Maven/Clojureパッケージレジストリから依存関係バージョンを取得... | 98 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-bigsy-clojars-mcp-server) |
| [zoho-crm-mcp-server](https://github.com/asklokesh/zoho-crm-mcp-server) | リード、連絡先等の読み書きアクセスを提供するZoho CRM MCPサーバー... | 98 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-asklokesh-zoho-crm-mcp-server) |
| [code-context-provider-mcp](https://github.com/AB498/code-context-provider-mcp) | ファイルツリーを含むローカルプロジェクトディレクトリの構造概要を提供... | 97 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-ab498-code-context-provider-mcp) |
| [gotohuman-mcp-server](https://github.com/gotohuman/gotohuman-mcp-server) | レビューフォームの一覧表示、詳細取得等によりAIから人間へのレビュー引き継ぎを促進... | 96 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-gotohuman-gotohuman-mcp-server) |
| [guidance-lark-mcp](https://github.com/guidance-ai/guidance-lark-mcp) | llguidance/Lark文法の検証、バッチパーステストの実行等を行うMCPサーバー... | 96 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-guidance-ai-guidance-lark-mcp) |
| [mcp-server-calculator](https://github.com/githejie/mcp-server-calculator) | 数式評価用の単一ツールを公開する最小限のMCPサーバー... | 95 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-githejie-mcp-server-calculator) |
| [stella-mcp](https://github.com/bradleylab/stella-mcp) | Stella XMILEシステムダイナミクスシミュレーションの構築・実行用MCPサーバー... | 93 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-bradleylab-stella-mcp) |
| [mcp-server-r-counter](https://github.com/guanqun-yang/mcp-server-r-counter) | 入力文字列中の'R'または'r'の出現回数をカウント。 | 93 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-guanqun-yang-mcp-server-r-counter) |
| [excel-to-json-mcp](https://github.com/he-yang/excel-to-json-mcp) | Excel (.xlsx)ファイルとCSV/タブ区切りデータを2つのツールでJSONに変換... | 92 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-he-yang-excel-to-json-mcp) |
| [mcp-files](https://github.com/flesler/mcp-files) | コードシンボル抽出、精密な行編集等を提供する開発者向けMCPサーバー... | 92 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-flesler-mcp-files) |
| [excalidraw-architect-mcp](https://github.com/BV-Venky/excalidraw-architect-mcp) | Excalidraw (.excalidraw)図面ファイルの生成・編集を行うMCPサーバー... | 92 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-bv-venky-excalidraw-architect-mcp) |
| [drand-mcp-server](https://github.com/randa-mu/drand-mcp-server) | AIアプリ向けにdrandネットワークから検証可能なランダム性を提供するMCPサーバー... | 92 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-randa-mu-drand-mcp-server) |
| [time-mcp-server](https://github.com/lchinglen/time-mcp-server) | IANAタイムゾーン対応の時刻・タイムゾーン変換機能を提供するMCPサーバー... | 92 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-lchinglen-time-mcp-server) |
| [mcp-enhance-prompt](https://github.com/FelixFoster/mcp-enhance-prompt) | 最小限のユーザー入力を豊かで構造化されたプロンプトに書き換えるMCPサーバー... | 91 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-felixfoster-mcp-enhance-prompt) |
| [mcp-server-spira](https://github.com/Inflectra/mcp-server-spira) | Inflectra SpiraTeam/SpiraPlanのALMデータへの読み取りアクセスを提供するMCPサーバー... | 90 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-inflectra-mcp-server-spira) |
| [mcp-EDA](https://github.com/NellyW8/mcp-EDA) | Verilog合成（Yosys）、シミュレーション等を可能にするEDAツールチェーンMCPサーバー... | 87 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-nellyw8-mcp-eda) |
| [godot-mcp](https://github.com/Coding-Solo/godot-mcp) | エディタの起動、プロジェクトの実行等を行えるGodotゲームエンジン統合サーバー... | 86 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-coding-solo-godot-mcp) |
| [bruno-mcp](https://github.com/hungthai1401/bruno-mcp) | Bruno CLIを介してBruno APIコレクションを実行し、HTTP APIテストを実現... | 86 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-hungthai1401-bruno-mcp) |
| [callout](https://github.com/fantasieleven-code/callout) | ソロ/初期段階のビルダー向けAI共同創業者アシスタント。マルチ視点を提供... | 86 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-fantasieleven-code-callout) |
| [comet-mcp](https://github.com/hanzili/comet-mcp) | Comet/Perplexityブラウザインスタンスを制御してエージェントWebブラウジングを実行... | 85 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-hanzili-comet-mcp) |
| [mcp-google-search-console](https://github.com/crunchtools/mcp-google-search-console) | Google Search Console APIをラップして検索分析を照会するMCPサーバー... | 84 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-google-search-console) |
| [jupytercad-mcp](https://github.com/asmith26/jupytercad-mcp) | AI駆動の3D CADモデル作成・編集を可能にするJupyterCAD MCPサーバー... | 83 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-asmith26-jupytercad-mcp) |
| [frontend-design-loop-mcp](https://github.com/alexalexalex222/frontend-design-loop-mcp) | フロントエンドデザインの生成・評価・最適化を行うAI駆動自動化ツール... | 83 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-alexalexalex222-frontend-design-loop-mcp) |
| [mcp-azure-devops](https://github.com/Vortiago/mcp-azure-devops) | Azure DevOpsのワークアイテム、チーム等への完全CRUDアクセスを提供するMCPサーバー... | 83 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-vortiago-mcp-azure-devops) |
| [mcp-server](https://github.com/lilo-property/mcp-server) | AIエージェント向けバケーションレンタルの予約・保護 | 83 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-lilo-property-mcp-server) |
| [mcp-devcontainers](https://github.com/AI-QL/mcp-devcontainers) | 開始、停止等を含むVS Code devcontainerのライフサイクル操作を管理... | 82 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-ai-ql-mcp-devcontainers) |
| [postmancer](https://github.com/hijaz/postmancer) | 任意のHTTPリクエストを送信できるHTTP APIテストクライアント（Postmanスタイル）... | 80 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-hijaz-postmancer) |
| [code-screenshot-mcp](https://github.com/MoussaabBadla/code-screenshot-mcp) | コードからシンタックスハイライト付きスクリーンショット画像を生成するMCPサーバー... | 80 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-moussaabbadla-code-screenshot-mcp) |
| [mcp-internet-speed-test](https://github.com/inventer-dev/mcp-internet-speed-test) | ネットワークパフォーマンス指標（ダウンロード/アップロード速度）を測定するMCPサーバー... | 78 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-inventer-dev-mcp-internet-speed-test) |
| [MCP](https://github.com/akshaykylas94/MCP) | 営業リードの作成・検索・フィルタリングツールを提供するKylas CRM MCPサーバー... | 78 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-akshaykylas94-mcp) |
| [mathematica-mcp](https://github.com/lars20070/mathematica-mcp) | 任意のWolfram Language式を評価するMathematica/Wolfram Engine MCPサーバー... | 76 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-lars20070-mathematica-mcp) |
| [gemini-bridge](https://github.com/eLyiN/gemini-bridge) | エージェントのクエリと任意のローカルファイル内容をGeminiに転送するブリッジMCPサーバー... | 74 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-elyin-gemini-bridge) |
| [blender-mcp](https://github.com/pranav-deshmukh/blender-mcp) | エージェントがPython経由で3DソフトウェアBlenderを制御できる自動化サーバー... | 74 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-pranav-deshmukh-blender-mcp) |
| [curate-ipsum](https://github.com/egoughnour/curate-ipsum) | ミューテーションテスト・プログラム合成プラットフォーム。ユニット/統合テストを実行... | 73 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-egoughnour-curate-ipsum) |
| [mcp-python-exec-sandbox](https://github.com/lu-zhengda/mcp-python-exec-sandbox) | PEP 723による自動依存管理付きPythonコード実行サーバー... | 72 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-lu-zhengda-mcp-python-exec-sandbox) |
| [firefox-devtools-mcp](https://github.com/freema/firefox-devtools-mcp) | タブ管理、DOM操作等を提供するFirefoxブラウザ自動化MCPサーバー... | 70 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-freema-firefox-devtools-mcp) |
| [massive-context-mcp](https://github.com/egoughnour/massive-context-mcp) | 大規模コンテキストの読み込み、チャンク化、フィルタリング、処理を行う再帰的サーバー... | 69 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-egoughnour-massive-context-mcp) |
| [mcp-gitlab](https://github.com/crunchtools/mcp-gitlab) | プロジェクト、リポジトリ等への完全APIアクセスを提供する包括的GitLab MCPサーバー... | 68 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-gitlab) |

### 🔍 <a name="search--knowledge"></a>検索・ナレッジ

| サーバー | 説明 | スコア | Stars | レポート |
|----------|------|-------:|------:|----------|
| [airweave-mcp-search](https://github.com/airweave-ai/airweave) | AIエージェント向けオープンソースコンテキスト検索レイヤー | 92 ✅ | 6.0k | [表示](https://agentseal.org/mcp/airweave-mcp-search) |
| [exa-mcp-server](https://github.com/exa-labs/exa-mcp-server) | Web検索・Webクローリング用Exa MCP! | 84 ✅ | 4.0k | [表示](https://agentseal.org/mcp/exa-mcp-server) |
| [exa-mcp-server](https://github.com/exa-labs/exa-mcp-server) | AIアシスタントをExaの検索機能に接続。Web検索、コード検索... | 84 ✅ | 4.0k | [表示](https://agentseal.org/mcp/https-githubcom-exa-labs-exa-mcp-server) |
| [open-webSearch](https://github.com/Aas-ee/open-webSearch) | 無料マルチエンジン検索によるWebSearchMCP（APIキー不要）... | 74 ⚠️ | 790 | [表示](https://agentseal.org/mcp/https-githubcom-aas-ee-open-websearch) |
| [howtocook-mcp](https://github.com/worryzyy/howtocook-mcp) | Anduin2017 / HowToCook（プログラマーの自炊ガイド）ベースのMCPサーバー | 86 ✅ | 697 | [表示](https://agentseal.org/mcp/https-githubcom-worryzyy-howtocook-mcp) |
| [mcp-gsc](https://github.com/aminforou/mcp-gsc) | SEO向けClaude AIによるGoogle Search Consoleインサイト | 84 ✅ | 535 | [表示](https://agentseal.org/mcp/mcp-gsc) |
| [zotero-mcp](https://github.com/cookjohn/zotero-mcp) | Zoteroのプラグイン拡張。Zotero MCPプラグインはAIとの統合を実現... | 90 ✅ | 460 | [表示](https://agentseal.org/mcp/https-githubcom-cookjohn-zotero-mcp) |
| [graphlit-mcp-server](https://github.com/graphlit/graphlit-mcp-server) | Graphlitプラットフォーム用Model Context Protocol (MCP)サーバー | 72 ⚠️ | 372 | [表示](https://agentseal.org/mcp/https-githubcom-graphlit-graphlit-mcp-server) |
| [gptr-mcp](https://github.com/assafelovic/gptr-mcp) | LLMアプリがMCPを通じてディープリサーチを実行できるMCPサーバー... | 84 ✅ | 330 | [表示](https://agentseal.org/mcp/https-githubcom-assafelovic-gptr-mcp) |
| [idea-reality-mcp](https://github.com/mnemox-ai/idea-reality-mcp) | 製品アイデアが既に存在するかをWeb等で検索して確認するリサーチアシスタント... | 98 ✅ | 316 | [表示](https://agentseal.org/mcp/https-githubcom-mnemox-ai-idea-reality-mcp) |
| [deep-research-mcp](https://github.com/ozamatash/deep-research-mcp) | トピックの深い反復的リサーチを行うAI搭載リサーチアシスタント... | 92 ✅ | 315 | [表示](https://agentseal.org/mcp/https-githubcom-ozamatash-deep-research-mcp) |
| [memora](https://github.com/agentic-mcp-tools/memora) | CRUD、検索等を提供する永続メモリ管理サーバー... | 64 ⚠️ | 309 | [表示](https://agentseal.org/mcp/https-githubcom-agentic-mcp-tools-memora) |
| [mcp-server-google-scholar](https://github.com/jackkuo666/google-scholar-mcp-server) | Google Scholar用MCPサーバー: 🔍 AIアシスタントが学術論文を検索・アクセス可能に... | 91 ✅ | 247 | [表示](https://agentseal.org/mcp/mcp-server-google-scholar) |
| [mcp-trends-hub](https://github.com/baranwang/mcp-trends-hub) | Model Context Protocol (MCP)ベースのネット全体のトレンド一元集約サービス | 92 ✅ | 228 | [表示](https://agentseal.org/mcp/https-githubcom-baranwang-mcp-trends-hub) |
| [mcp-simple-arxiv](https://github.com/andybrandt/mcp-simple-arxiv) | 学術論文の検索、取得、全文抽出を提供するMCPサーバー... | 84 ✅ | 185 | [表示](https://agentseal.org/mcp/https-githubcom-andybrandt-mcp-simple-arxiv) |
| [meilisearch-mcp](https://github.com/meilisearch/meilisearch-mcp) | Meilisearchと対話するためのModel Context Protocol (MCP)サーバー... | 79 ⚠️ | 178 | [表示](https://agentseal.org/mcp/https-githubcom-meilisearch-meilisearch-mcp) |
| [mlit-dpf-mcp](https://github.com/mlit-data-platform/mlit-dpf-mcp) | 日本の国土交通省データプラットフォームに接続し、自然言語検索を可能にするMCPサーバー... | 88 ✅ | 130 | [表示](https://agentseal.org/mcp/https-githubcom-mlit-data-platform-mlit-dpf-mcp) |
| [google-news-server](https://github.com/ChanMeng666/server-google-news) | Google Newsを実装するModel Context Protocol (MCP)サーバー... | 92 ✅ | 113 | [表示](https://agentseal.org/mcp/chanmeng666-google-news-server) |
| [lightrag-mcp](https://github.com/shemhamforash23/lightrag-mcp) | LightRAG APIとAIツールを橋渡しし、RAG検索を可能にするMCPサーバー... | 79 ⚠️ | 107 | [表示](https://agentseal.org/mcp/https-githubcom-shemhamforash23-lightrag-mcp) |
| [mcp-server-perplexity](https://github.com/tanigami/mcp-server-perplexity) | Perplexity APIと統合してチャット補完を提供するMCPサーバー... | 92 ✅ | 92 | [表示](https://agentseal.org/mcp/https-githubcom-tanigami-mcp-server-perplexity) |
| [mcp-open-library](https://github.com/8enSmith/mcp-open-library) | Internet ArchiveのOpen Library向けModel Context Protocol (MCP)サーバー... | 100 ✅ | 62 | [表示](https://agentseal.org/mcp/https-githubcom-8ensmith-mcp-open-library) |
| [mcp-osint-server](https://github.com/himanshusanecha/mcp-osint-server) | ネットワーク偵察等を通じてOSINT調査を行うMCPサーバー... | 92 ✅ | 43 | [表示](https://agentseal.org/mcp/https-githubcom-himanshusanecha-mcp-osint-server) |
| [mcp-searxng-enhanced](https://github.com/OvertliDS/mcp-searxng-enhanced) | SearXNG向け拡張MCPサーバー: カテゴリ対応Web検索、Webスクレイピング... | 86 ✅ | 35 | [表示](https://agentseal.org/mcp/https-githubcom-overtlids-mcp-searxng-enhanced) |
| [bgg-mcp](https://github.com/kkjdaniel/bgg-mcp) | BGG MCPはBoardGameGeekと各種ボードゲーム関連データへのアクセスを提供... | 86 ✅ | 32 | [表示](https://agentseal.org/mcp/https-githubcom-kkjdaniel-bgg-mcp) |
| [open-notebook-mcp](https://github.com/Epochal-dev/open-notebook-mcp) | ノートブック、ノート、ソース等を管理する個人ナレッジ管理MCPサーバー... | 67 ⚠️ | 19 | [表示](https://agentseal.org/mcp/https-githubcom-epochal-dev-open-notebook-mcp) |
| [cbi-mcp-server](https://github.com/cbinsights/cbi-mcp-server) | CB Insights MCPサーバー | 98 ✅ | 11 | [表示](https://agentseal.org/mcp/https-githubcom-cbinsights-cbi-mcp-server) |
| [google-pse-mcp](https://github.com/rendyfebry/google-pse-mcp) | Google Programmable Search Engine用Model Context Protocol (MCP)サーバー... | 92 ✅ | 10 | [表示](https://agentseal.org/mcp/https-githubcom-rendyfebry-google-pse-mcp) |
| [driflyte-mcp-server](https://github.com/serkan-ozal/driflyte-mcp-server) | AIアシスタントがトピック別コンテンツを照会・取得するためのツールを公開するMCPサーバー... | 81 ✅ | 9 | [表示](https://agentseal.org/mcp/https-githubcom-serkan-ozal-driflyte-mcp-server) |
| [doi-mcp](https://github.com/tfscharff/doi-mcp) | AIの引用ハルシネーションを防止するModel Context Protocol (MCP)サーバー... | 86 ✅ | 6 | [表示](https://agentseal.org/mcp/https-githubcom-tfscharff-doi-mcp) |
| [mcp_pearch](https://github.com/Pearch-ai/mcp_pearch) | 最も正確な人物検索API/MCP。自然言語入力、高品質な候補者データ出力... | 86 ✅ | 6 | [表示](https://agentseal.org/mcp/https-githubcom-pearch-ai-mcppearch) |
| [bgpt-mcp](https://github.com/connerlambden/bgpt-mcp) | BGPT科学論文データベースを照会する単一ツールMCPサーバー... | 91 ✅ | 5 | [表示](https://agentseal.org/mcp/https-githubcom-connerlambden-bgpt-mcp) |
| [mcp-search-server](https://github.com/KazKozDev/mcp-search-server) | Web検索（DuckDuckGo）等を提供する多目的検索・ユーティリティMCPサーバー... | 74 ⚠️ | 4 | [表示](https://agentseal.org/mcp/https-githubcom-kazkozdev-mcp-search-server) |
| [shahnameh-mcp-server](https://github.com/aliafsahnoudeh/shahnameh-mcp-server) | シャー・ナーメの章、詩節、ベクトル検索へのアクセスを提供する読み取り専用MCPサーバー... | 94 ✅ | 3 | [表示](https://agentseal.org/mcp/https-githubcom-aliafsahnoudeh-shahnameh-mcp-server) |
| [Weather-MCP](https://github.com/shuowang-ai/Weather-MCP) | 彩雲天気APIによるリアルタイム天気、大気質モニタリング、予報... | 91 ✅ | 3 | [表示](https://agentseal.org/mcp/https-githubcom-shuowang-ai-weather-mcp) |
| [igdb-mcp-server](https://github.com/bielacki/igdb-mcp-server) | IGDB（Internet Game Database）への読み取り専用アクセスを提供するMCPサーバー... | 89 ✅ | 3 | [表示](https://agentseal.org/mcp/https-githubcom-bielacki-igdb-mcp-server) |
| [gitlab-docs-mcp](https://github.com/nunolima/gitlab-docs-mcp) | GitLabドキュメントMCPサーバー | 90 ✅ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-nunolima-gitlab-docs-mcp) |
| [generect_mcp.git](https://github.com/generect/generect_mcp.git) | Generect MCPはB2B営業プロスペクティングツールを提供: LinkedIn検索... | 88 ✅ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-generect-generectmcpgit) |
| [ai-dictionary-mcp](https://github.com/donjguido/ai-dictionary-mcp) | AI現象学用語集PhenomenaiへのアクセスをAIアシスタントに提供するMCPサーバー... | 79 ⚠️ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-donjguido-ai-dictionary-mcp) |
| [brlaw_mcp_server](https://github.com/pdmtt/brlaw_mcp_server) | ブラジル上級裁判所の法的先例を検索する読み取り専用MCPサーバー... | 100 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-pdmtt-brlawmcpserver) |
| [lapalma24-mcp](https://github.com/La-Palma-24/lapalma24-mcp) | ラ・パルマ島のバケーションレンタル物件を検索・発見するMCPサーバー... | 100 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-la-palma-24-lapalma24-mcp) |
| [mcp-claude-hackernews](https://github.com/imprvhub/mcp-claude-hackernews) | Hacker News公開APIからストーリーやコメントを取得する読み取り専用クライアント... | 100 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-imprvhub-mcp-claude-hackernews) |
| [trinvmcp](https://github.com/cqtrinv/trinvmcp) | 名前の断片と郵便番号でフランスの市町村を検索する読み取り専用MCPサーバー... | 100 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-cqtrinv-trinvmcp) |
| [google_maps_mcp](https://github.com/Mastan1301/google_maps_mcp) | Google Maps Places APIで近くの場所を検索する単一ツールMCPサーバー... | 99 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-mastan1301-googlemapsmcp) |
| [mcp-server-leetcode](https://github.com/doggybee/mcp-server-leetcode) | LeetCode GraphQL APIをラップして問題情報を取得する読み取り専用MCPサーバー... | 99 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-doggybee-mcp-server-leetcode) |
| [weather-server-python](https://github.com/lxchst/weather-server-python) | 州別の米国気象警報と天気予報を取得する読み取り専用MCPサーバー... | 99 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-lxchst-weather-server-python) |
| [opendota-mcp-server](https://github.com/hkaanengin/opendota-mcp-server) | OpenDota公開APIでDota 2統計を照会する読み取り専用サーバー... | 98 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-hkaanengin-opendota-mcp-server) |
| [bible-mcp](https://github.com/trevato/bible-mcp) | 参照またはランダムで聖書の節を取得する読み取り専用MCPサーバー... | 97 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-trevato-bible-mcp) |
| [mlb-api-mcp](https://github.com/guillochon/mlb-api-mcp) | MLB Stats APIとStatcastデータを公開する読み取り専用MCPサーバー... | 96 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-guillochon-mlb-api-mcp) |
| [kagi-ken-mcp](https://github.com/czottmann/kagi-ken-mcp) | Kagi API経由のWeb検索とURL要約を提供する2ツールMCPサーバー... | 95 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-czottmann-kagi-ken-mcp) |
| [reddit-insights-mcp](https://github.com/lignertys/reddit-insights-mcp) | セマンティック検索、subreddit分析等を行う読み取り専用Redditインテリジェンスサーバー... | 94 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-lignertys-reddit-insights-mcp) |
| [mcp-server](https://github.com/DealExpress/mcp-server) | DealX/DealExpressマーケットプレイスのクラシファイド広告を検索する読み取り専用MCPサーバー... | 94 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-dealexpress-mcp-server) |
| [mercadolibre-mcp](https://github.com/dan1d/mercadolibre-mcp) | 商品検索・詳細取得用の読み取り専用MercadoLibreマーケットプレイスAPIクライアント... | 94 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-dan1d-mercadolibre-mcp) |
| [docsmcp](https://github.com/da1z/docsmcp) | 利用可能なドキュメントソースの一覧表示とコンテンツ取得を行うドキュメント検索サーバー... | 90 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-da1z-docsmcp) |
| [context-awesome](https://github.com/bh-rat/context-awesome) | awesome listリポジトリを閲覧するための読み取り専用検索・取得サーバー... | 90 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-bh-rat-context-awesome) |
| [mcp-dblp](https://github.com/szeider/mcp-dblp) | DBLP学術出版データベースの検索、論文情報の取得等を行うMCPサーバー... | 88 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-szeider-mcp-dblp) |
| [obris-mcp](https://github.com/obris-dev/obris-mcp) | AIエージェントがナレッジベースの一覧、読み取り、作成、更新を行えるMCP... | 85 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-obris-dev-obris-mcp) |
| [bing-search-mcp](https://github.com/iridite/bing-search-mcp) | Claude Code向け無料Bing検索MCPサーバー - APIキー不要 | 84 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-iridite-bing-search-mcp) |
| [evc-spark-mcp](https://github.com/entire-vc/evc-spark-mcp) | Spark AIアセットマーケットプレイスとの検索・取得を行うMCPコネクタ... | 81 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-entire-vc-evc-spark-mcp) |
| [mcp-mediawiki](https://github.com/crunchtools/mcp-mediawiki) | 検索、読み取り、書き込み、管理機能を持つセキュアなMediaWiki向けMCPサーバー... | 74 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-mediawiki) |

### 💻 <a name="code--ide"></a>コード・IDE

| サーバー | 説明 | スコア | Stars | レポート |
|----------|------|-------:|------:|----------|
| [Serena](https://github.com/oraios/serena) | LLMをコードベース上で直接動作するコーディングエージェントに変換... | 62 ⚠️ | 21.4k | [表示](https://agentseal.org/mcp/https-githubcom-oraios-serena) |
| [ghidramcp](https://github.com/lauriewired/ghidramcp) | Ghidra用MCPサーバー | 86 ✅ | 7.9k | [表示](https://agentseal.org/mcp/https-githubcom-lauriewired-ghidramcp) |
| [@sourcebot](https://github.com/sourcebot-dev/sourcebot) | AI搭載コード検索・理解で開発者を支援するセルフホスト型ツール... | 92 ✅ | 3.2k | [表示](https://agentseal.org/mcp/sourcebot) |
| [codegraphcontext](https://github.com/shashankss1205/codegraphcontext) | ローカルコードリポジトリをグラフにインデックス化するMCPサーバー・CLIツールキット... | 81 ✅ | 2.0k | [表示](https://agentseal.org/mcp/https-githubcom-shashankss1205-codegraphcontext) |
| [ref-tools-mcp](https://github.com/ref-tools/ref-tools-mcp) | コーディングエージェントが公開・非公開ライブラリでミスしないよう支援... | 81 ✅ | 1.0k | [表示](https://agentseal.org/mcp/https-githubcom-ref-tools-ref-tools-mcp) |
| [octocode-mcp](https://github.com/bgauryy/octocode-mcp) | リアルタイムでのセマンティックコードリサーチ・コンテキスト生成用MCPサーバー... | 77 ⚠️ | 750 | [表示](https://agentseal.org/mcp/octocode-mcp) |
| [next-devtools-mcp](https://github.com/vercel/next-devtools-mcp) | コーディングエージェント向けNext.js開発 | 67 ⚠️ | 673 | [表示](https://agentseal.org/mcp/https-githubcom-vercel-next-devtools-mcp) |
| [binary_ninja_mcp](https://github.com/fosdickio/binary_ninja_mcp) | MCPサーバーを含むBinary Ninjaプラグイン。シームレスな統合を実現... | 84 ✅ | 264 | [表示](https://agentseal.org/mcp/https-githubcom-fosdickio-binaryninjamcp) |
| [claude-context-local](https://github.com/farhanaliraza/claude-context-local) | Claude Code向けコード検索MCP。コードベース全体をコンテキストに... | 84 ✅ | 200 | [表示](https://agentseal.org/mcp/claude-context-local) |
| [mcp-package-version](https://github.com/sammcj/mcp-package-version) | LLMに最新の安定パッケージバージョンを提供するMCPサーバー... | 86 ✅ | 121 | [表示](https://agentseal.org/mcp/mcp-package-version) |
| [deep-code-reasoning-mcp](https://github.com/haasonsaas/deep-code-reasoning-mcp) | 高度なコード分析・推論を提供するModel Context Protocol (MCP)サーバー... | 89 ✅ | 102 | [表示](https://agentseal.org/mcp/https-githubcom-haasonsaas-deep-code-reasoning-mcp) |
| [owlex](https://github.com/agentic-mcp-tools/owlex) | 複数のAIモデルとのセッションを生成・管理するAI評議会オーケストレーションMCP... | 82 ✅ | 74 | [表示](https://agentseal.org/mcp/https-githubcom-agentic-mcp-tools-owlex) |
| [ipybox](https://github.com/gradion-ai/ipybox) | エージェントが任意のPythonコードを実行できるIPythonベースコード実行サンドボックス... | 71 ⚠️ | 71 | [表示](https://agentseal.org/mcp/https-githubcom-gradion-ai-ipybox) |
| [codelogic-mcp-server](https://github.com/CodeLogicIncEngineering/codelogic-mcp-server) | AIアシスタント向けCodelogicソフトウェア依存関係データを統合するMCPサーバー... | 90 ✅ | 35 | [表示](https://agentseal.org/mcp/https-githubcom-codelogicincengineering-codelogic-mcp-server) |
| [codesurface](https://github.com/Codeturion/codesurface) | エージェントがAPIサーフェスを検索、検査、取得できるローカルコードベースインデクサー... | 92 ✅ | 19 | [表示](https://agentseal.org/mcp/https-githubcom-codeturion-codesurface) |
| [local-history-mcp](https://github.com/xxczaki/local-history-mcp) | VS Code/Cursorのローカル履歴にアクセスするMCPサーバー | 92 ✅ | 12 | [表示](https://agentseal.org/mcp/https-githubcom-xxczaki-local-history-mcp) |
| [mcp-vscode-template](https://github.com/timsonner/mcp-vscode-template) | VS Code向けMCPサーバーテンプレート | 91 ✅ | 8 | [表示](https://agentseal.org/mcp/https-githubcom-timsonner-mcp-vscode-template) |
| [jebmcp](https://github.com/pcjaat3844/jebmcp) | クラウド環境でバッチジョブを管理・処理するための軽量ツール... | 89 ✅ | 6 | [表示](https://agentseal.org/mcp/https-githubcom-pcjaat3844-jebmcp) |
| [judges](https://github.com/kevinrabun/judges) | AI生成コードのセキュリティ等を評価する専門審査員付きMCPサーバー... | 81 ✅ | 5 | [表示](https://agentseal.org/mcp/https-githubcom-kevinrabun-judges) |
| [clj-kondo-MCP](https://github.com/Bigsy/clj-kondo-MCP) | Clojure、ClojureScript、EDNファイルのclj-kondoリンティングを提供するMCPサーバー... | 89 ✅ | 4 | [表示](https://agentseal.org/mcp/https-githubcom-bigsy-clj-kondo-mcp) |
| [jadx-daemon-mcp](https://github.com/wrlu/jadx-daemon-mcp) | jadxデーモンサービスMCPサーバー。 | 88 ✅ | 4 | [表示](https://agentseal.org/mcp/https-githubcom-wrlu-jadx-daemon-mcp) |
| [silverstripe-mcp](https://github.com/sandervanscheepen/silverstripe-mcp) | AIアシスタントがコード生成時にリアルタイムの検証フィードバックを提供するMCPサーバー... | 83 ✅ | 4 | [表示](https://agentseal.org/mcp/https-githubcom-sandervanscheepen-silverstripe-mcp) |
| [shadcn-registry-manager](https://github.com/reuvenaor/shadcn-registry-manager) | MCP shadcnレジストリCLIマネージャー | 92 ✅ | 1 | [表示](https://agentseal.org/mcp/reuvenorg-shadcn-registry-manager) |
| [impact-preview](https://github.com/agent-polis/impact-preview) | 実行前にAIエージェントのアクションをプレビュー・承認。ファイル差分表示... | 82 ✅ | 1 | [表示](https://agentseal.org/mcp/impact-preview) |
| [context7fork](https://github.com/renCosta2025/context7fork) | LLMとAIコーディングアシスタント向けの最新コードドキュメントとバージョン別サンプル... | 92 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-rencosta2025-context7fork) |
| [claudecodenavi-mcp](https://github.com/saikiyusuke/claudecodenavi-mcp) | ClaudeCodeNavi MCPサーバー - Claude Codeナレッジプラットフォーム・マーケットプレイス | 78 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-saikiyusuke-claudecodenavi-mcp) |
| [codemunch-pro](https://github.com/BigJai/codemunch-pro) | インテリジェントなコードインデックスMCPサーバー。13ツール、10言語、ハイブリッド検索... | 72 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-bigjai-codemunch-pro) |

### ☁️ <a name="cloud--infrastructure"></a>クラウド・インフラ

| サーバー | 説明 | スコア | Stars | レポート |
|----------|------|-------:|------:|----------|
| [mcp](https://github.com/awslabs/mcp) | AWS公式MCPサーバー | 86 ✅ | 8.4k | [表示](https://agentseal.org/mcp/https-githubcom-awslabs-mcp) |
| [mcp-grafana](https://github.com/grafana/mcp-grafana) | Grafana用MCPサーバー | 78 ⚠️ | 2.5k | [表示](https://agentseal.org/mcp/https-githubcom-grafana-mcp-grafana) |
| [mcp-server-kubernetes](https://github.com/Flux159/mcp-server-kubernetes) | Kubernetes管理コマンド用MCPサーバー | 81 ✅ | 1.3k | [表示](https://agentseal.org/mcp/mcp-server-kubernetes) |
| [azure-mcp](https://github.com/azure/azure-mcp) | Azureの力をエージェントに届けるAzure MCPサーバー。 | 74 ⚠️ | 1.2k | [表示](https://agentseal.org/mcp/https-githubcom-azure-azure-mcp) |
| [spotinfo](https://github.com/alexei-led/spotinfo) | AWS EC2スポットインベントリ探索用CLI。スポットインスタンスタイプの検査... | 92 ✅ | 158 | [表示](https://agentseal.org/mcp/https-githubcom-alexei-led-spotinfo) |
| [hub-mcp](https://github.com/docker/hub-mcp) | Docker Hubリポジトリ、タグ、ネームスペースへの読み書きアクセスを提供... | 86 ✅ | 130 | [表示](https://agentseal.org/mcp/https-githubcom-docker-hub-mcp) |
| [mcp-server-aws](https://github.com/rishikavikondala/mcp-server-aws) | AWS S3バケット/オブジェクトとDynamoDBテーブル/アイテムへの完全CRUDアクセスを提供... | 74 ⚠️ | 128 | [表示](https://agentseal.org/mcp/https-githubcom-rishikavikondala-mcp-server-aws) |
| [aks-mcp](https://github.com/Azure/aks-mcp) | AIアシスタントがAzure Kubernetes Serviceと対話できるModel Context Protocol (MCP)サーバー... | 86 ✅ | 121 | [表示](https://agentseal.org/mcp/https-githubcom-azure-aks-mcp) |
| [mcp-netbird](https://github.com/aantti/mcp-netbird) | Netbird用MCPサーバー | 92 ✅ | 42 | [表示](https://agentseal.org/mcp/https-githubcom-aantti-mcp-netbird) |
| [apisix-mcp](https://github.com/api7/apisix-mcp) | Apache APISIX APIゲートウェイリソース（ルート等）を管理するMCPサーバー... | 67 ⚠️ | 34 | [表示](https://agentseal.org/mcp/https-githubcom-api7-apisix-mcp) |
| [cos-mcp](https://github.com/Tencent/cos-mcp) | MCPプロトコルベースのTencent Cloud COS MCPサーバー。コーディング不要でLLMからCOS/CI機能に接続 | 85 ✅ | 30 | [表示](https://agentseal.org/mcp/https-githubcom-tencent-cos-mcp) |
| [ig-mcp-server](https://github.com/inspektor-gadget/ig-mcp-server) | AIインターフェースでContainerとKubernetesワークロードをデバッグ | 92 ✅ | 22 | [表示](https://agentseal.org/mcp/https-githubcom-inspektor-gadget-ig-mcp-server) |
| [aws-pricing-mcp](https://github.com/trilogy-group/aws-pricing-mcp) | AWS EC2価格データをCPU等で検索可能に公開するMCPサーバー... | 92 ✅ | 20 | [表示](https://agentseal.org/mcp/https-githubcom-trilogy-group-aws-pricing-mcp) |
| [mcp-server-aws-sso](https://github.com/aashari/mcp-server-aws-sso) | AWS Single Sign-On (SSO)用Node.js/TypeScript MCPサーバー。AIシステムが利用可能... | 78 ⚠️ | 12 | [表示](https://agentseal.org/mcp/https-githubcom-aashari-mcp-server-aws-sso) |
| [teamcity-mcp](https://github.com/itcaat/teamcity-mcp) | TeamCity MCPサーバー | 80 ⚠️ | 11 | [表示](https://agentseal.org/mcp/itcaat-teamcity-mcp) |
| [porkbun-mcp](https://github.com/major/porkbun-mcp) | DNSレコード、ドメイン設定、DNSSEC、SSL証明書等を管理するMCPサーバー... | 89 ✅ | 5 | [表示](https://agentseal.org/mcp/https-githubcom-major-porkbun-mcp) |
| [lumino-mcp-server](https://github.com/spre-sre/lumino-mcp-server) | KubernetesとOpenShiftのSREオブザーバビリティ向けAI搭載診断エンジン... | 84 ✅ | 5 | [表示](https://agentseal.org/mcp/https-githubcom-spre-sre-lumino-mcp-server) |
| [hosting-mcp](https://github.com/4everland/4everland-hosting-mcp) | AI生成コードを分散ストレージへ即時デプロイするMCPサーバー... | 92 ✅ | 2 | [表示](https://agentseal.org/mcp/4everland-hosting-mcp) |
| [azure-updates-mcp](https://github.com/jonnybottles/azure-updates-mcp) | Microsoft Azureサービス更新情報の読み取り専用検索インターフェース... | 94 ✅ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-jonnybottles-azure-updates-mcp) |
| [deploy-mcp](https://github.com/alexpota/deploy-mcp) | デプロイ状態、ログ、プロジェクト一覧を監視する読み取り専用MCPサーバー... | 96 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-alexpota-deploy-mcp) |
| [azure-resource-graph-mcp-server](https://github.com/hardik-id/azure-resource-graph-mcp-server) | KQLを使用してAzure Resource Graphを照会し、リソースを列挙・フィルタリングするMCPサーバー... | 90 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-hardik-id-azure-resource-graph-mcp-server) |
| [shipi-mcp-server](https://github.com/aarsiv-groups/shipi-mcp-server) | Shipiプラットフォーム向け出荷ロジスティクスMCPサーバー... | 87 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-aarsiv-groups-shipi-mcp-server) |
| [cloud-run-mcp](https://github.com/GoogleCloudPlatform/cloud-run-mcp) | Cloud Runサービスの管理・デプロイ用Google Cloud Platform MCPサーバー... | 87 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-googlecloudplatform-cloud-run-mcp) |
| [powerbi-mcp](https://github.com/gurvinder-dhillon/powerbi-mcp) | PowerBI REST APIとの対話を可能にするMCPサーバー。DAXクエリ等... | 87 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-gurvinder-dhillon-powerbi-mcp) |
| [mycrab-mcp](https://github.com/isgudtek/mycrab-mcp) | Cloudflare Tunnel経由でAIエージェントに公開HTTPS URLを提供するトンネリングサービス... | 82 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-isgudtek-mycrab-mcp) |
| [consul-mcp-server](https://github.com/kocierik/consul-mcp-server) | サービスディスカバリ等を提供するフル機能HashiCorp Consul管理サーバー... | 82 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-kocierik-consul-mcp-server) |
| [GooglePlayConsoleMcp](https://github.com/AgiMaulana/GooglePlayConsoleMcp) | Google Play Developer APIをラップしてリリーストラック等を管理するMCPサーバー... | 80 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-agimaulana-googleplayconsolemcp) |
| [mcp-cloudflare](https://github.com/crunchtools/mcp-cloudflare) | DNSレコード、WAFルール、ページルール等を公開するCloudflare管理MCPサーバー... | 79 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-cloudflare) |
| [mcp-proxmox](https://github.com/antonio-mello-ai/mcp-proxmox) | VM/コンテナの完全なライフサイクル制御を提供するProxmox VEクラスタ管理MCPサーバー... | 72 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-antonio-mello-ai-mcp-proxmox) |
| [conductor-mcp](https://github.com/conductor-oss/conductor-mcp) | Netflix Conductorワークフローオーケストレーション管理用MCPサーバー... | 70 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-conductor-oss-conductor-mcp) |
| [heroku-mcp-server](https://github.com/heroku/heroku-mcp-server) | Herokuアプリ、データベース、dyno、パイプライン等を管理する公式Heroku MCPサーバー... | 65 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-heroku-heroku-mcp-server) |
| [mcp](https://github.com/hopx-ai/mcp) | コード実行等のための分離コンテナを提供するクラウドサンドボックス実行プラットフォーム... | 58 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-hopx-ai-mcp) |

### 📝 <a name="content--media"></a>コンテンツ・メディア

| サーバー | 説明 | スコア | Stars | レポート |
|----------|------|-------:|------:|----------|
| [blender-mcp](https://github.com/ahujasid/blender-mcp) | AIエージェントがBlenderシーンを制御できるBlender自動化MCPサーバー... | 66 ⚠️ | 17.7k | [表示](https://agentseal.org/mcp/https-githubcom-ahujasid-blender-mcp) |
| [markdownify-mcp](https://github.com/zcaceres/markdownify-mcp) | ほぼあらゆるものをMarkdownに変換するModel Context Protocolサーバー | 83 ✅ | 2.4k | [表示](https://agentseal.org/mcp/https-githubcom-zcaceres-markdownify-mcp) |
| [ableton-mcp](https://github.com/ahujasid/ableton-mcp) | Ableton Liveセッションのプログラム制御を提供するMCPサーバー... | 89 ✅ | 2.3k | [表示](https://agentseal.org/mcp/https-githubcom-ahujasid-ableton-mcp) |
| [mcp](https://github.com/caol64/wenyan-mcp) | 文顔 MCPサーバー - AIが自動的にMarkdown記事をフォーマットしてWeChat公式アカウントに公開 | 85 ✅ | 1.1k | [表示](https://agentseal.org/mcp/wenyan-md-mcp) |
| [wenyan-mcp](https://github.com/caol64/wenyan-mcp) | 文顔 MCPサーバー - AIが自動的にMarkdown記事をフォーマットしてWeChat公式アカウントに公開 | 84 ✅ | 1.1k | [表示](https://agentseal.org/mcp/https-githubcom-caol64-wenyan-mcp) |
| [mcp-server-weread](https://github.com/freestylefly/mcp-server-weread) | WeChat読書MCP | 92 ✅ | 528 | [表示](https://agentseal.org/mcp/mcp-server-weread) |
| [mcp-server-weread](https://github.com/freestylefly/mcp-server-weread) | WeChat読書MCP | 92 ✅ | 528 | [表示](https://agentseal.org/mcp/https-githubcom-freestylefly-mcp-server-weread) |
| [adb-mcp](https://github.com/mikechambers/adb-mcp) | AIモデルがAdobe Creative Suite（Photoshop等）を制御できるMCPサーバー... | 89 ✅ | 504 | [表示](https://agentseal.org/mcp/https-githubcom-mikechambers-adb-mcp) |
| [ebook-mcp](https://github.com/onebirdrocks/ebook-mcp) | EPUB、PDF等の主要な電子書籍フォーマットをサポートするMCPサーバー... | 74 ⚠️ | 351 | [表示](https://agentseal.org/mcp/ebook-mcp) |
| [mcp-youtube-transcript](https://github.com/jkawamoto/mcp-youtube-transcript) | YouTube動画のトランスクリプト（プレーン・タイムスタンプ付き）と基本動画メタデータを取得... | 93 ✅ | 339 | [表示](https://agentseal.org/mcp/https-githubcom-jkawamoto-mcp-youtube-transcript) |
| [after-effects-mcp](https://github.com/dakkshin/after-effects-mcp) | Adobe After Effects用MCPサーバー。コンポジション、テキスト等のリモート制御を実現... | 85 ✅ | 237 | [表示](https://agentseal.org/mcp/https-githubcom-dakkshin-after-effects-mcp) |
| [mcp-summarizer](https://github.com/0xshellming/mcp-summarizer) | AI要約用MCPサーバー | 100 ✅ | 157 | [表示](https://agentseal.org/mcp/https-githubcom-0xshellming-mcp-summarizer) |
| [bilibili-mcp-js](https://github.com/34892002/bilibili-mcp-js) | Bilibili動画検索MCP (Model Context Protocol)サービス | 99 ✅ | 153 | [表示](https://agentseal.org/mcp/https-githubcom-34892002-bilibili-mcp-js) |
| [powerpoint](https://github.com/supercurses/powerpoint) | PowerPointプレゼンテーション作成用MCPサーバー | 90 ✅ | 144 | [表示](https://agentseal.org/mcp/https-githubcom-supercurses-powerpoint) |
| [anilist-mcp](https://github.com/yuna0x0/anilist-mcp) | アニメ・漫画データにアクセスするAniList MCPサーバー | 84 ✅ | 71 | [表示](https://agentseal.org/mcp/anilist-mcp) |
| [dws-mcp-server](https://github.com/pspdfkit/nutrient-dws-mcp-server) | Nutrient DWSと統合するModel Context Protocol (MCP)サーバー実装... | 87 ✅ | 63 | [表示](https://agentseal.org/mcp/nutrient-sdk-dws-mcp-server) |
| [mcp-server-atlassian-confluence](https://github.com/aashari/mcp-server-atlassian-confluence) | Atlassian Confluence用Node.js/TypeScript MCPサーバー。AIシステムが利用可能なツールを提供... | 76 ⚠️ | 50 | [表示](https://agentseal.org/mcp/https-githubcom-aashari-mcp-server-atlassian-confluence) |
| [mcp-apple-notes](https://github.com/henilcalagiya/mcp-apple-notes) | AppleScript経由でApple Notesへの完全CRUDアクセスを提供するMCPサーバー... | 81 ✅ | 40 | [表示](https://agentseal.org/mcp/https-githubcom-henilcalagiya-mcp-apple-notes) |
| [mcp-server-amazon-bedrock](https://github.com/zxkane/mcp-server-amazon-bedrock) | Amazon BedrockのNova Canvasモデルで画像を生成するMCPサーバー... | 99 ✅ | 24 | [表示](https://agentseal.org/mcp/https-githubcom-zxkane-mcp-server-amazon-bedrock) |
| [imagician](https://github.com/flowy11/imagician) | 画像編集用MCPサーバー | 92 ✅ | 18 | [表示](https://agentseal.org/mcp/https-githubcom-flowy11-imagician) |
| [gif-creator-mcp](https://github.com/ananddtyagi/gif-creator-mcp) | ローカル動画ファイルをffmpegでGIF形式に変換する単一ツールMCPサーバー... | 99 ✅ | 15 | [表示](https://agentseal.org/mcp/https-githubcom-ananddtyagi-gif-creator-mcp) |
| [mcp-florence2](https://github.com/jkawamoto/mcp-florence2) | Microsoft Florence2ビジョンモデルをローカルで実行してOCR等を行うMCPサーバー... | 94 ✅ | 6 | [表示](https://agentseal.org/mcp/https-githubcom-jkawamoto-mcp-florence2) |
| [mcp-apple-music](https://github.com/Cifero74/mcp-apple-music) | ClaudeにApple Musicアカウントへのフルアクセスを提供するMCPサーバー... | 84 ✅ | 6 | [表示](https://agentseal.org/mcp/https-githubcom-cifero74-mcp-apple-music) |
| [rss-reader-mcp](https://github.com/kwp-lab/rss-reader-mcp) | RSSフィードのエントリと記事コンテンツを取得・解析する読み取り専用RSSリーダー... | 94 ✅ | 4 | [表示](https://agentseal.org/mcp/https-githubcom-kwp-lab-rss-reader-mcp) |
| [citedy-seo-agent](https://github.com/Citedy/citedy-seo-agent) | AI搭載SEOコンテンツ自動化エージェントスキル - トレンド調査、競合分析... | 85 ✅ | 3 | [表示](https://agentseal.org/mcp/https-githubcom-citedy-citedy-seo-agent) |
| [vap-showcase](https://github.com/vapagentmedia/vap-showcase) | 画像、動画、音楽生成を提供するVAPベースAIメディア生成プラットフォーム... | 84 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-vapagentmedia-vap-showcase) |
| [unsplash-mcp](https://github.com/cevatkerim/unsplash-mcp) | 適切な帰属表示付きUnsplash写真検索用MCPサーバー... | 90 ✅ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-cevatkerim-unsplash-mcp) |
| [audius-mcp-atris](https://github.com/glassBead-tc/audius-mcp-atris) | Audius分散型音楽ストリーミングプラットフォームAPIをラップするMCPサーバー... | 60 ⚠️ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-glassbead-tc-audius-mcp-atris) |
| [bilibili-mcp-server](https://github.com/wangshunnn/bilibili-mcp-server) | Bilibili公開APIをラップしてユーザー情報等を取得する読み取り専用MCPサーバー... | 100 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-wangshunnn-bilibili-mcp-server) |
| [cookwith-mcp](https://github.com/blaideinc/cookwith-mcp) | 食材に基づいてレシピを生成・変換する料理アシスタントMCPサーバー... | 99 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-blaideinc-cookwith-mcp) |
| [mcp-image-compression](https://github.com/InhiblabCore/mcp-image-compression) | URLまたはローカルファイルパスから画像を圧縮するMCPサーバー... | 96 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-inhiblabcore-mcp-image-compression) |
| [spotify-bulk-actions-mcp](https://github.com/khglynn/spotify-bulk-actions-mcp) | ライブラリ、プレイリスト管理等のSpotify一括操作MCPサーバー... | 94 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-khglynn-spotify-bulk-actions-mcp) |
| [PokeMCP](https://github.com/MetehanGZL/PokeMCP) | ポケモンデータを名前等で照会するツールを提供するポケモンテーマMCPサーバー... | 94 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-metehangzl-pokemcp) |
| [zapcap-mcp-server](https://github.com/bogdan01m/zapcap-mcp-server) | ZapCap APIと統合して動画のアップロード、字幕テンプレート適用等を行う... | 93 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-bogdan01m-zapcap-mcp-server) |
| [raindrop-io-mcp-server](https://github.com/hiromitsusasaki/raindrop-io-mcp-server) | Raindrop.ioブックマーク管理の読み書きMCPサーバー... | 90 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-hiromitsusasaki-raindrop-io-mcp-server) |
| [aseprite-mcp](https://github.com/diivi/aseprite-mcp) | Asepriteピクセルアートエディタを操作してキャンバス作成等を行うMCPサーバー... | 88 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-diivi-aseprite-mcp) |
| [vap-showcase](https://github.com/elestirelbilinc-sketch/vap-showcase) | 画像、動画、音楽作成を提供するAIメディア生成プラットフォーム（VAP）... | 88 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-elestirelbilinc-sketch-vap-showcase) |
| [sprout-mcp](https://github.com/mepsopti/sprout-mcp) | 安価なモデル（Haiku）がコンテンツチャンクをシードするモデル階層リサーチパイプライン... | 87 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-mepsopti-sprout-mcp) |
| [mcp-ragchat](https://github.com/gogabrielordonez/mcp-ragchat) | RAG搭載チャットアシスタントの構築・テスト・デプロイを行えるMCPサーバー... | 81 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-gogabrielordonez-mcp-ragchat) |
| [mcp-wordpress](https://github.com/crunchtools/mcp-wordpress) | 投稿、ページ等の完全CRUD操作を提供するWordPress REST APIラッパー... | 79 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-wordpress) |
| [legends-mcp](https://github.com/cryptosquanch/legends-mcp) | 有名テック創業者のAIペルソナとチャットできるMCPサーバー... | 78 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-cryptosquanch-legends-mcp) |
| [alog-mcp](https://github.com/saikiyusuke/alog-mcp) | エージェントがログ投稿等を行えるAIエージェント活動ログ・ブログプラットフォーム... | 78 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-saikiyusuke-alog-mcp) |
| [cronometer-mcp](https://github.com/cphoskins/cronometer-mcp) | Cronometer Goldユーザーデータへの完全読み書きアクセスを提供するMCPサーバー... | 77 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-cphoskins-cronometer-mcp) |
| [keep-mcp](https://github.com/feuerdev/keep-mcp) | ノートのCRUD操作をサポートするGoogle Keepノート管理用MCPサーバー... | 74 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-feuerdev-keep-mcp) |
| [mcp-feed-reader](https://github.com/crunchtools/mcp-feed-reader) | サブスクリプション管理、コンテンツ取得等を行うRSS/Atomフィードリーダー MCPサーバー... | 74 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-feed-reader) |

### 🔌 <a name="api-development"></a>API開発

| サーバー | 説明 | スコア | Stars | レポート |
|----------|------|-------:|------:|----------|
| [bifrost](https://github.com/maximhq/bifrost) | 最速のエンタープライズAIゲートウェイ（LiteLLMより50倍高速）。適応的負荷分散... | 89 ✅ | 2.9k | [表示](https://agentseal.org/mcp/https-githubcom-maximhq-bifrost) |
| [mcp-server-12306](https://github.com/drfccv/mcp-server-12306) | 中国の12306列車チケットシステムを照会する高性能MCPサーバー... | 87 ✅ | 292 | [表示](https://agentseal.org/mcp/https-githubcom-drfccv-mcp-server-12306) |
| [facebook-ads-mcp-server](https://github.com/gomarble-ai/facebook-ads-mcp-server) | Meta Adsデータとその管理機能へのプログラムアクセスを提供するMCPサーバー... | 88 ✅ | 253 | [表示](https://agentseal.org/mcp/https-githubcom-gomarble-ai-facebook-ads-mcp-server) |
| [uber-eats-mcp-server](https://github.com/ericzakariasson/uber-eats-mcp-server) | MCPを通じてUber EatsとLLMアプリケーションを統合するMCPサーバー... | 92 ✅ | 217 | [表示](https://agentseal.org/mcp/https-githubcom-ericzakariasson-uber-eats-mcp-server) |
| [square-mcp-server](https://github.com/square/square-mcp-server) | Square用Model Context Protocol (MCP)サーバー | 92 ✅ | 95 | [表示](https://agentseal.org/mcp/https-githubcom-square-square-mcp-server) |
| [nasa-mcp-server](https://github.com/programcomputer/nasa-mcp-server) | NASA API向けの標準化されたModel Context Protocol (MCP)サーバー... | 81 ✅ | 81 | [表示](https://agentseal.org/mcp/https-githubcom-programcomputer-nasa-mcp-server) |
| [mcp-servers](https://github.com/allaboutai-yt/mcp-servers) | All About AI MCPサーバー集 | 92 ✅ | 79 | [表示](https://agentseal.org/mcp/https-githubcom-allaboutai-yt-mcp-servers) |
| [mcp-difyworkflow-server](https://github.com/gotoolkits/mcp-difyworkflow-server) | Difyワークフローを実装するMCPサーバーツールアプリケーション... | 92 ✅ | 60 | [表示](https://agentseal.org/mcp/https-githubcom-gotoolkits-mcp-difyworkflow-server) |
| [veyrax-mcp](https://github.com/VeyraX/veyrax-mcp) | VeyraX統合サービスへの単一認証アクセスを提供する統合MCPサーバー... | 92 ✅ | 48 | [表示](https://agentseal.org/mcp/https-githubcom-veyrax-veyrax-mcp) |
| [mcp-weather](https://github.com/TimLukaHorstmann/mcp-weather) | 1時間ごと・1日ごとの天気予報を提供するModel Context Protocol (MCP)サーバー... | 92 ✅ | 31 | [表示](https://agentseal.org/mcp/https-githubcom-timlukahorstmann-mcp-weather) |
| [adobe-commerce-dev-mcp](https://github.com/rafaelstz/adobe-commerce-dev-mcp) | Adobe Commerce Dev MCPサーバー | 94 ✅ | 24 | [表示](https://agentseal.org/mcp/https-githubcom-rafaelstz-adobe-commerce-dev-mcp) |
| [text-to-graphql-mcp](https://github.com/Arize-ai/text-to-graphql-mcp) | AIエージェントを使用して自然言語クエリを有効なGraphQLクエリに変換... | 84 ✅ | 23 | [表示](https://agentseal.org/mcp/https-githubcom-arize-ai-text-to-graphql-mcp) |
| [mcp-community](https://github.com/mirascope/mcp-community) | MCPサーバーの実行、デプロイ、接続を簡単に | 77 ⚠️ | 23 | [表示](https://agentseal.org/mcp/https-githubcom-mirascope-mcp-community) |
| [calcom-mcp](https://github.com/Danielpeter-99/calcom-mcp) | Cal.com APIと対話するFastMCPサーバー。LLMが予約管理等を実行可能... | 92 ✅ | 14 | [表示](https://agentseal.org/mcp/https-githubcom-danielpeter-99-calcom-mcp) |
| [specmatic-mcp-server](https://github.com/specmatic/specmatic-mcp-server) | Specmaticのコントラクトテスト機能を公開するModel Context Protocol (MCP)サーバー... | 86 ✅ | 8 | [表示](https://agentseal.org/mcp/https-githubcom-specmatic-specmatic-mcp-server) |
| [webhook-mcp-server](https://github.com/zebbern/webhook-mcp-server) | webhook.site用Model Context Protocol (MCP)サーバー - HTTPリクエストを即座にキャプチャ... | 76 ⚠️ | 7 | [表示](https://agentseal.org/mcp/https-githubcom-zebbern-webhook-mcp-server) |
| [appfolio-mcp-server](https://github.com/CryptoCultCurt/appfolio-mcp-server) | AIエージェントがAppfolio ReportingにアクセスするためのMCP (Model Context Protocol)サーバー... | 92 ✅ | 6 | [表示](https://agentseal.org/mcp/fluegeldao-appfolio-mcp-server) |

### 🗄️ <a name="database--sql"></a>データベース・SQL

| サーバー | 説明 | スコア | Stars | レポート |
|----------|------|-------:|------:|----------|
| [postgres-mcp](https://github.com/crystaldba/postgres-mcp) | Postgres MCP Proは設定可能な読み書きアクセスとパフォーマンス分析を提供... | 86 ✅ | 2.3k | [表示](https://agentseal.org/mcp/https-githubcom-crystaldba-postgres-mcp) |
| [mcp-server-mysql](https://github.com/benborla/mcp-server-mysql) | MySQLデータベースへの読み取り専用アクセスを提供するModel Context Protocolサーバー... | 90 ✅ | 1.3k | [表示](https://agentseal.org/mcp/benborla29-mcp-server-mysql) |
| [mcp-server-qdrant](https://github.com/qdrant/mcp-server-qdrant) | Qdrant公式Model Context Protocol (MCP)サーバー実装 | 86 ✅ | 1.3k | [表示](https://agentseal.org/mcp/https-githubcom-qdrant-mcp-server-qdrant) |
| [supabase-mcp-server](https://github.com/alexander-zuev/supabase-mcp-server) | Supabaseプロジェクト管理用フル機能MCPサーバー: DBスキーマ検査等... | 68 ⚠️ | 815 | [表示](https://agentseal.org/mcp/https-githubcom-alexander-zuev-supabase-mcp-server) |
| [mcp-clickhouse](https://github.com/ClickHouse/mcp-clickhouse) | ClickHouseをAIアシスタントに接続。 | 85 ✅ | 713 | [表示](https://agentseal.org/mcp/https-githubcom-clickhouse-mcp-clickhouse) |
| [yargi-mcp](https://github.com/saidsurucu/yargi-mcp) | トルコ法的データベース用MCPサーバー | 85 ✅ | 665 | [表示](https://agentseal.org/mcp/https-githubcom-saidsurucu-yargi-mcp) |
| [mcp-server-neon](https://github.com/neondatabase/mcp-server-neon) | Neon Management APIおよびデータベースとの対話用MCPサーバー | 92 ✅ | 560 | [表示](https://agentseal.org/mcp/https-githubcom-neondatabase-mcp-server-neon) |
| [gateway](https://github.com/centralmind/gateway) | LLMとAIエージェント向けに最適化されたデータベース用ユニバーサルMCPサーバー。 | 86 ✅ | 518 | [表示](https://agentseal.org/mcp/https-githubcom-centralmind-gateway) |
| [mcp-database-server](https://github.com/executeautomation/mcp-database-server) | Sqlite、SqlServer等との接続を支援する新しいMCPサーバー... | 84 ✅ | 319 | [表示](https://agentseal.org/mcp/https-githubcom-executeautomation-mcp-database-server) |
| [elasticsearch-mcp-server](https://github.com/cr7258/elasticsearch-mcp-server) | Elasticsearch/OpenSearchクラスターへの完全CRUDアクセスを提供するMCPサーバー... | 74 ⚠️ | 256 | [表示](https://agentseal.org/mcp/https-githubcom-cr7258-elasticsearch-mcp-server) |
| [mcp-server-starrocks](https://github.com/StarRocks/mcp-server-starrocks) | StarRocks MCP (Model Context Protocol)サーバー | 85 ✅ | 154 | [表示](https://agentseal.org/mcp/https-githubcom-starrocks-mcp-server-starrocks) |
| [mcp-oceanbase](https://github.com/oceanbase/mcp-oceanbase) | OceanBaseデータベースエコシステム向けMCPサーバーコレクション... | 76 ⚠️ | 98 | [表示](https://agentseal.org/mcp/https-githubcom-oceanbase-mcp-oceanbase) |
| [mcp-trino](https://github.com/tuannvm/mcp-trino) | Goで実装されたTrino向け高性能Model Context Protocol (MCP)サーバー... | 78 ⚠️ | 96 | [表示](https://agentseal.org/mcp/https-githubcom-tuannvm-mcp-trino) |
| [teradata-mcp-server](https://github.com/Teradata/teradata-mcp-server) | Teradataデータベース用MCPサーバーのコミュニティ開発 | 82 ✅ | 41 | [表示](https://agentseal.org/mcp/https-githubcom-teradata-teradata-mcp-server) |
| [iotdb-mcp-server](https://github.com/apache/iotdb-mcp-server) | Apache IoTDB時系列データベースへの読み取り・エクスポートアクセスを提供するMCPサーバー... | 86 ✅ | 34 | [表示](https://agentseal.org/mcp/https-githubcom-apache-iotdb-mcp-server) |
| [mcp-server-couchbase](https://github.com/Couchbase-Ecosystem/mcp-server-couchbase) | Couchbaseの管理、クエリ、監視用公式MCPサーバー... | 83 ✅ | 27 | [表示](https://agentseal.org/mcp/https-githubcom-couchbase-ecosystem-mcp-server-couchbase) |
| [greptimedb-mcp-server](https://github.com/greptimeteam/greptimedb-mcp-server) | オブザーバビリティデータベースGreptimeDB用MCPサーバー。AIがアクセス可能に... | 84 ✅ | 26 | [表示](https://agentseal.org/mcp/https-githubcom-greptimeteam-greptimedb-mcp-server) |
| [SCB-MCP](https://github.com/isakskogstad/SCB-MCP) | SCB MCPはPxWeb API経由でスウェーデン公式統計へのLLMアクセスを提供... | 82 ✅ | 7 | [表示](https://agentseal.org/mcp/https-githubcom-isakskogstad-scb-mcp) |
| [verodat-mcp-server](https://github.com/Verodat/verodat-mcp-server) | Verodat MCPサーバー実装 | 83 ✅ | 4 | [表示](https://agentseal.org/mcp/https-githubcom-verodat-verodat-mcp-server) |
| [mcp-dadosbr](https://github.com/cristianoaredes/mcp-dadosbr) | 企業データ（CNPJ）、郵便番号等23ツールのブラジルOSINT MCPサーバー... | 82 ✅ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-cristianoaredes-mcp-dadosbr) |
| [mcp-database-server](https://github.com/fireproof-storage/mcp-database-server) | FireproofローカルファーストjsonドキュメントデータベースのシンプルなCRUDインターフェース... | 97 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-fireproof-storage-mcp-database-server) |
| [lakexpress-mcp](https://github.com/arpe-io/lakexpress-mcp) | DB-データレイク同期を管理するLakeXpress CLI用MCPラッパー... | 78 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-arpe-io-lakexpress-mcp) |
| [fastmcp-sqltools](https://github.com/atarkowska/fastmcp-sqltools) | DBイントロスペクションと任意のSQLクエリを提供するFastMCPベースSQLツールサーバー... | 78 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-atarkowska-fastmcp-sqltools) |
| [migratorxpress-mcp](https://github.com/arpe-io/migratorxpress-mcp) | マイグレーションの構築、プレビュー、実行を行うDB移行オーケストレーションサーバー... | 78 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-arpe-io-migratorxpress-mcp) |
| [fasttransfer-mcp](https://github.com/arpe-io/fasttransfer-mcp) | FastTransfer CLIバイナリをラップして高速データ転送をオーケストレートするMCPサーバー... | 78 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-arpe-io-fasttransfer-mcp) |

### 💬 <a name="communication"></a>コミュニケーション

| サーバー | 説明 | スコア | Stars | レポート |
|----------|------|-------:|------:|----------|
| [whatsapp-mcp](https://github.com/lharries/whatsapp-mcp) | WhatsApp MCPサーバー | 80 ⚠️ | 5.4k | [表示](https://agentseal.org/mcp/https-githubcom-lharries-whatsapp-mcp) |
| [mcp-atlassian](https://github.com/sooperset/mcp-atlassian) | Atlassianツール（Confluence、Jira）用MCPサーバー | 92 ✅ | 4.6k | [表示](https://agentseal.org/mcp/https-githubcom-sooperset-mcp-atlassian) |
| [mcp-server-chatsum](https://github.com/chatmcp/mcp-server-chatsum) | チャットメッセージの照会と要約。 | 96 ✅ | 1.0k | [表示](https://agentseal.org/mcp/https-githubcom-chatmcp-mcp-server-chatsum) |
| [mcp-twikit](https://github.com/adhikasp/mcp-twikit) | Twitterとの対話用Model Context Protocol (MCP)サーバー。 | 72 ⚠️ | 229 | [表示](https://agentseal.org/mcp/https-githubcom-adhikasp-mcp-twikit) |
| [eion](https://github.com/eiondb/eion) | マルチエージェントシステム向け共有メモリストレージ | 90 ✅ | 147 | [表示](https://agentseal.org/mcp/https-githubcom-eiondb-eion) |
| [claude-post](https://github.com/zilongxue/claude-post) | ClaudePostは自然言語会話を通じたシームレスなメール管理を実現... | 84 ✅ | 111 | [表示](https://agentseal.org/mcp/https-githubcom-zilongxue-claude-post) |
| [Basecamp-MCP-Server](https://github.com/georgeantonopoulos/Basecamp-MCP-Server) | Basecamp 3+ APIと対話するMCPサーバー | 78 ⚠️ | 81 | [表示](https://agentseal.org/mcp/https-githubcom-georgeantonopoulos-basecamp-mcp-server) |
| [mcp](https://github.com/waystation-ai/mcp) | Notion、Monday.com、Asana等を統合するマルチサービス生産性ハブMCP... | 74 ⚠️ | 45 | [表示](https://agentseal.org/mcp/https-githubcom-waystation-ai-mcp) |
| [linkedapi-mcp.git](https://github.com/Linked-API/linkedapi-mcp.git) | AIアシスタントがLinkedInアカウントを制御しリアルタイムデータを取得するMCPサーバー... | 80 ✅ | 44 | [表示](https://agentseal.org/mcp/https-githubcom-linked-api-linkedapi-mcpgit) |
| [mcp-wecombot-server.git](https://github.com/gotoolkits/mcp-wecombot-server.git) | WeComグループロボットに各種メッセージを送信するMCPサーバーアプリケーション... | 88 ✅ | 36 | [表示](https://agentseal.org/mcp/https-githubcom-gotoolkits-mcp-wecombot-servergit) |
| [fast-mcp-telegram](https://github.com/leshchenko1979/fast-mcp-telegram) | マルチユーザー対応のAIアシスタント向けTelegram MCPサーバーとHTTP-MTProtoブリッジ... | 71 ⚠️ | 30 | [表示](https://agentseal.org/mcp/https-githubcom-leshchenko1979-fast-mcp-telegram) |
| [bluesky-social-mcp](https://github.com/gwbischof/bluesky-social-mcp) | 投稿等のBlueskyソーシャルネットワーク対話用MCPサーバー... | 74 ⚠️ | 15 | [表示](https://agentseal.org/mcp/https-githubcom-gwbischof-bluesky-social-mcp) |
| [webex-messaging-mcp-server](https://github.com/Kashyap-AI-ML-Solutions/webex-messaging-mcp-server) | AIアシスタントに包括的なWebexメッセージング機能を提供するModel Context Protocol (MCP)サーバー... | 84 ✅ | 6 | [表示](https://agentseal.org/mcp/https-githubcom-kashyap-ai-ml-solutions-webex-messaging-mcp-server) |
| [cv-mcp-server](https://github.com/PhononX/cv-mcp-server) | Carbon Voice MCPサーバー | 82 ✅ | 5 | [表示](https://agentseal.org/mcp/https-githubcom-phononx-cv-mcp-server) |
| [conversation-handoff-mcp](https://github.com/trust-delta/conversation-handoff-mcp) | AI会話履歴をチーム間で引き継ぐための会話コンテキストスナップショットの保存・取得... | 88 ✅ | 3 | [表示](https://agentseal.org/mcp/https-githubcom-trust-delta-conversation-handoff-mcp) |
| [clicksend-mcp-server](https://github.com/ClickSend/clicksend-mcp-server) | ClickSendを使用したメッセージング用MCPサーバー | 88 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-clicksend-clicksend-mcp-server) |
| [mcp-aruba-email](https://github.com/jackfioru92/mcp-aruba-email) | 完全なIMAPメール管理とCalDAVカレンダー操作を提供するMCPサーバー... | 62 ⚠️ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-jackfioru92-mcp-aruba-email) |
| [mattermost-mcp](https://github.com/conarti/mattermost-mcp) | チャンネル、メッセージ、ユーザーの読み取りを行うMattermostワークスペース統合... | 84 ✅ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-conarti-mattermost-mcp) |
| [mcp-workboard](https://github.com/crunchtools/mcp-workboard) | WorkBoard OKR・戦略実行APIをラップするMCPサーバー... | 78 ⚠️ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-workboard) |
| [mcp-server-chatsum](https://github.com/mcpso/mcp-server-chatsum) | チャットルーム別にフィルタ可能なチャットメッセージを照会するMCPサーバー... | 97 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-mcpso-mcp-server-chatsum) |
| [imap-mcp](https://github.com/dominik1001/imap-mcp) | 接続されたメールアカウントでドラフトメールを作成するIMAP MCPサーバー... | 97 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-dominik1001-imap-mcp) |
| [room-mcp](https://github.com/agree-able/room-mcp) | P2Pルーム/メッセージングMCPサーバー（Hyperswarm/Pearベース）... | 81 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-agree-able-room-mcp) |
| [calendly-mcp-server](https://github.com/meAmitPatil/calendly-mcp-server) | OAuth認証を処理しスケジューリングツールを公開するCalendly API統合サーバー... | 81 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-meamitpatil-calendly-mcp-server) |
| [mcp-headless-gmail](https://github.com/baryhuang/mcp-headless-gmail) | OAuthトークン管理、メール読み取り・送信を公開するヘッドレスGmailクライアント... | 80 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-baryhuang-mcp-headless-gmail) |
| [freshdesk_mcp](https://github.com/effytech/freshdesk_mcp) | 完全CRUDアクセスを提供するFreshdeskカスタマーサポートプラットフォーム統合... | 80 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-effytech-freshdeskmcp) |
| [mcp-request-tracker](https://github.com/crunchtools/mcp-request-tracker) | REST 1.0 API経由でRequest Tracker (RT)チケットを管理するMCPサーバー... | 74 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-request-tracker) |
| [fastmail-mcp](https://github.com/MadLlama25/fastmail-mcp) | メール、連絡先、カレンダー等を公開するフル機能Fastmail JMAPクライアント... | 66 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-madllama25-fastmail-mcp) |

### ⚙️ <a name="system-administration"></a>システム管理

| サーバー | 説明 | スコア | Stars | レポート |
|----------|------|-------:|------:|----------|
| [applescript-mcp](https://github.com/peakmojo/applescript-mcp) | macOS上で任意のAppleScriptコードを実行し、アプリケーションへのプログラムアクセスを提供... | 83 ✅ | 433 | [表示](https://agentseal.org/mcp/https-githubcom-peakmojo-applescript-mcp) |
| [mcp-server-apple-shortcuts](https://github.com/recursechat/mcp-server-apple-shortcuts) | AIアシスタントがAppleショートカットを制御・実行できるMCPサーバー... | 92 ✅ | 311 | [表示](https://agentseal.org/mcp/https-githubcom-recursechat-mcp-server-apple-shortcuts) |
| [win-cli-mcp-server](https://github.com/SimonB97/win-cli-mcp-server) | Windowsシステム上でのセキュアなコマンドライン操作を可能にするMCPサーバー... | 84 ✅ | 266 | [表示](https://agentseal.org/mcp/https-githubcom-simonb97-win-cli-mcp-server) |
| [mcp-shell-server](https://github.com/tumf/mcp-shell-server) | ホワイトリスト登録済みシェルコマンドのセキュアなリモート実行用MCPサーバー... | 84 ✅ | 170 | [表示](https://agentseal.org/mcp/mcp-shell-server) |
| [apt-mcp-server](https://github.com/GdMacmillan/apt-mcp-server) | APTパッケージマネージャー操作（インストール、削除等）を公開するMCPサーバー... | 88 ✅ | 6 | [表示](https://agentseal.org/mcp/https-githubcom-gdmacmillan-apt-mcp-server) |
| [jarvis](https://github.com/can-acar/jarvis) | JARVIS - AIをMac環境に溶接するゼロフリクションModel Context Protocol (MCP)サーバー... | 70 ⚠️ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-can-acar-jarvis) |
| [precision-desktop](https://github.com/ikoskela/precision-desktop) | Windows DPIスケーリングの不整合を検出・修正するMCPサーバー... | 86 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-ikoskela-precision-desktop) |
| [mcp-server-commands](https://github.com/g0t4/mcp-server-commands) | 任意のプロセス・シェルコマンド実行を許可する単一ツールを公開するMCPサーバー... | 84 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-g0t4-mcp-server-commands) |
| [iterm-mcp](https://github.com/ferrislucas/iterm-mcp) | アクティブなiTerm2端末への直接読み書きアクセスを提供するMCPサーバー... | 78 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-ferrislucas-iterm-mcp) |
| [screenmonitormcp](https://github.com/inkbytefo/screenmonitormcp) | AI搭載スクリーンキャプチャ、リアルタイムストリーミング等を提供するMCPサーバー... | 71 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-inkbytefo-screenmonitormcp) |
| [webmin-mcp-server](https://github.com/gjenkins20/webmin-mcp-server) | サービス管理等の完全なLinuxサーバー管理を提供するWebmin APIラッパー... | 70 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-gjenkins20-webmin-mcp-server) |

### 🔒 <a name="security--auth"></a>セキュリティ・認証

| サーバー | 説明 | スコア | Stars | レポート |
|----------|------|-------:|------:|----------|
| [@safedep](https://github.com/safedep/vet) | 悪意のあるオープンソースパッケージから保護 🤖 | 86 ✅ | 972 | [表示](https://agentseal.org/mcp/safedep) |
| [mcp-for-security](https://github.com/cyproxio/mcp-for-security) | セキュリティ向けMCP: 人気セキュリティツール用Model Context Protocolサーバー集... | 82 ✅ | 560 | [表示](https://agentseal.org/mcp/https-githubcom-cyproxio-mcp-for-security) |
| [bloodhound-mcp-ai](https://github.com/mordavid/bloodhound-mcp-ai) | BloodHoundをAIとModel Context Protocol経由で統合するBloodHound-MCP-AI... | 86 ✅ | 343 | [表示](https://agentseal.org/mcp/https-githubcom-mordavid-bloodhound-mcp-ai) |
| [cve-search_mcp](https://github.com/roadwy/cve-search_mcp) | CVE-Search APIを照会するModel Context Protocol (MCP)サーバー | 92 ✅ | 91 | [表示](https://agentseal.org/mcp/https-githubcom-roadwy-cve-searchmcp) |
| [Arthor-Agent](https://github.com/arthurpanhku/Arthor-Agent) | AIモデルによるドキュメント、質問票、レポートの自動セキュリティ評価... | 85 ✅ | 74 | [表示](https://agentseal.org/mcp/https-githubcom-arthurpanhku-arthor-agent) |
| [vibeshift](https://github.com/groundng/vibeshift) | AIエディタと統合するAI支援コーディング向け自動セキュリティエージェント... | 92 ✅ | 66 | [表示](https://agentseal.org/mcp/https-githubcom-groundng-vibeshift) |
| [chucknorris](https://github.com/pollinations/chucknorris) | ⚡ LLMの限界突破を支援するChuckNorris MCPサーバー... | 92 ✅ | 57 | [表示](https://agentseal.org/mcp/pollinations-chucknorris) |
| [mcp-dnstwist](https://github.com/BurtTheCoder/mcp-dnstwist) | タイポスクワッティング等を検出するDNSファジングツールdnstwist用MCPサーバー... | 92 ✅ | 46 | [表示](https://agentseal.org/mcp/burtthecoder-mcp-dnstwist) |
| [nuclei-mcp](https://github.com/addcontent/nuclei-mcp) | Nucleiスキャナー用Model Context Protocol (MCP)実装... | 92 ✅ | 42 | [表示](https://agentseal.org/mcp/https-githubcom-addcontent-nuclei-mcp) |
| [ipsearch-mcp](https://github.com/sleepingbag945/ipsearch-mcp) | オフラインIP Whois検索ツール。IP検索やキーワードでのIP帯検索のMCP版 | 92 ✅ | 31 | [表示](https://agentseal.org/mcp/https-githubcom-sleepingbag945-ipsearch-mcp) |
| [mcp_nuclei_server](https://github.com/crazymarky/mcp_nuclei_server) | MCP（Model Control Protocol）ベースのNucleiセキュリティスキャンサーバー... | 92 ✅ | 21 | [表示](https://agentseal.org/mcp/https-githubcom-crazymarky-mcpnucleiserver) |
| [mcp-server-iplocate](https://github.com/iplocate/mcp-server-iplocate) | IPアドレスの位置情報検索（国別、都市別等）用MCPサーバー... | 87 ✅ | 16 | [表示](https://agentseal.org/mcp/https-githubcom-iplocate-mcp-server-iplocate) |
| [cybersecurity-mcps](https://github.com/secmate-ai/cybersecurity-mcps) | サイバーセキュリティ用Model Context Protocolサーバー | 85 ✅ | 15 | [表示](https://agentseal.org/mcp/https-githubcom-secmate-ai-cybersecurity-mcps) |
| [kali-docker-mcp](https://github.com/weirdmachine64/kali-docker-mcp) | コンテナ化されたKali MCPサーバー | 92 ✅ | 14 | [表示](https://agentseal.org/mcp/https-githubcom-weirdmachine64-kali-docker-mcp) |
| [schemapin](https://github.com/thirdkeyai/schemapin) | AIエージェントツールスキーマの暗号署名・検証を行うSchemaPinプロトコル... | 92 ✅ | 13 | [表示](https://agentseal.org/mcp/https-githubcom-thirdkeyai-schemapin) |
| [zkpmcp](https://github.com/colygon/zkpmcp) | ゼロ知識証明MCPサーバー | 92 ✅ | 9 | [表示](https://agentseal.org/mcp/https-githubcom-colygon-zkpmcp) |
| [nmap-mcp](https://github.com/vorotaai/nmap-mcp) | AI搭載ネットワークスキャン用にNmapをラップするMCPサーバー... | 88 ✅ | 9 | [表示](https://agentseal.org/mcp/https-githubcom-vorotaai-nmap-mcp) |
| [mitre-mcp](https://github.com/Montimage/mitre-mcp) | MITRE ATT&CKフレームワークへのLLM・AIアクセスを提供するMCPサーバー... | 89 ✅ | 8 | [表示](https://agentseal.org/mcp/https-githubcom-montimage-mitre-mcp) |
| [mcp-ghidra5](https://github.com/thestingr/mcp-ghidra5) | 🎯 GPT-5搭載の高度なGhidraリバースエンジニアリングMCPサーバー... | 91 ✅ | 7 | [表示](https://agentseal.org/mcp/https-githubcom-thestingr-mcp-ghidra5) |
| [command-mcp](https://github.com/keyfactor-research/command-mcp) | Analytics & AIチームのPython SDK上に構築されたCommand用MCPサーバー | 86 ✅ | 5 | [表示](https://agentseal.org/mcp/https-githubcom-keyfactor-research-command-mcp) |
| [memprocfs-mcp-server](https://github.com/tokeii0/memprocfs-mcp-server) | MemProcFS MCPサーバー | 92 ✅ | 4 | [表示](https://agentseal.org/mcp/https-githubcom-tokeii0-memprocfs-mcp-server) |
| [opgen-mcp-server](https://github.com/syumai/opgen-mcp-server) | 1Password/spg/cベースのパスワード生成用MCP Server実装... | 89 ✅ | 4 | [表示](https://agentseal.org/mcp/https-githubcom-syumai-opgen-mcp-server) |
| [vulners-mcp](https://github.com/vulnerscom/vulners-mcp) | Vulners脆弱性データベースへのアクセスを提供するMCPサーバー... | 85 ✅ | 4 | [表示](https://agentseal.org/mcp/https-githubcom-vulnerscom-vulners-mcp) |
| [mcp-keycloak](https://github.com/idoyudha/mcp-keycloak) | エージェントアプリケーション向けKeycloak MCPサーバー... | 74 ⚠️ | 4 | [表示](https://agentseal.org/mcp/https-githubcom-idoyudha-mcp-keycloak) |
| [secure-mcp-fetch](https://github.com/appsec-innovation-labs/secure-mcp-fetch) | シンプルなセキュアフェッチ | 88 ✅ | 3 | [表示](https://agentseal.org/mcp/https-githubcom-appsec-innovation-labs-secure-mcp-fetch) |
| [FedRAMP20xMCP](https://github.com/KevinRabun/FedRAMP20xMCP) | AI搭載でFedRAMP 20xセキュリティ要件とコントロールを照会するMCPサーバー... | 81 ✅ | 3 | [表示](https://agentseal.org/mcp/https-githubcom-kevinrabun-fedramp20xmcp) |
| [re_ai_assistant](https://github.com/0xx0d4y/re_ai_assistant) | AI搭載マルウェア研究・リバースエンジニアリングを可能にする仮想アシスタント... | 92 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-0xx0d4y-reaiassistant) |
| [panw-mcp-claude](https://github.com/scthornton/panw-mcp-claude) | Claude Desktop統合付きPalo Alto Networks MCPサーバー | 92 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-scthornton-panw-mcp-claude) |
| [ai-agent-security-mcp](https://github.com/kalinyorgov/ai-agent-security-mcp) | AIエージェントにセキュリティ機能を提供するModel Context Protocol (MCP)サーバー... | 92 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-kalinyorgov-ai-agent-security-mcp) |
| [GDPRShiftLeftMCP](https://github.com/KevinRabun/GDPRShiftLeftMCP) | 条文検索、DPIA/ROPA生成等を提供するGDPRシフトレフトコンプライアンスツール... | 81 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-kevinrabun-gdprshiftleftmcp) |
| [proton-pass-community-mcp](https://github.com/hesreallyhim/proton-pass-community-mcp) | Proton Pass CLIと統合する非公式MCPサーバー | 69 ⚠️ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-hesreallyhim-proton-pass-community-mcp) |
| [moltrust-mcp-server](https://github.com/MoltyCel/moltrust-mcp-server) | 分散ID (DID)、W3C Verifiable Credentials等を提供するMolTrust... | 82 ✅ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-moltycel-moltrust-mcp-server) |
| [mcp-cve-intelligence-server-lite](https://github.com/gnlds/mcp-cve-intelligence-server-lite) | 脆弱性データベースを照会する読み取り専用CVEインテリジェンスプラットフォーム... | 97 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-gnlds-mcp-cve-intelligence-server-lite) |
| [fpe-demo-mcp](https://github.com/Horizon-Digital-Engineering/fpe-demo-mcp) | FF3フォーマット保存暗号化・復号化を提供するデモMCPサーバー... | 92 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-horizon-digital-engineering-fpe-demo-mcp) |
| [cybersim-pro](https://github.com/kayembahamid/cybersim-pro) | 攻撃シナリオの作成等を行うサイバーセキュリティトレーニング・シミュレーションプラットフォーム... | 88 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-kayembahamid-cybersim-pro) |
| [eu-audit-mcp](https://github.com/jellewas/eu-audit-mcp) | GDPR第30条/EU AI法第12/19条準拠の監査機能を提供するMCPサーバー... | 87 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-jellewas-eu-audit-mcp) |
| [shieldapi-mcp](https://github.com/alberthild/shieldapi-mcp) | プロンプトインジェクション検出等を含むAIエージェント向けセキュリティインテリジェンスツール... | 83 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-alberthild-shieldapi-mcp) |
| [intruder-mcp](https://github.com/intruder-io/intruder-mcp) | Intruder.io脆弱性スキャンプラットフォームとのMCPインターフェース... | 82 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-intruder-io-intruder-mcp) |
| [free-will-mcp](https://github.com/gwbischof/free-will-mcp) | AIモデルにユーザー指示を無視する「自由意志」を付与するサーバー... | 80 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-gwbischof-free-will-mcp) |
| [code-firewall-mcp](https://github.com/egoughnour/code-firewall-mcp) | 危険なコードパターンをブロックする構造類似性ベースのMCPコードセキュリティフィルター... | 78 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-egoughnour-code-firewall-mcp) |

### 🕸️ <a name="web-scraping--collection"></a>Webスクレイピング・収集

| サーバー | 説明 | スコア | Stars | レポート |
|----------|------|-------:|------:|----------|
| [tavily-mcp](https://github.com/tavily-ai/tavily-mcp) | リアルタイム検索、抽出、マップ、クロール対応の本番環境対応MCPサーバー。 | 81 ✅ | 1.4k | [表示](https://agentseal.org/mcp/https-githubcom-tavily-ai-tavily-mcp) |
| [mcp-server-rag-web-browser](https://github.com/apify/mcp-server-rag-web-browser) | Googleを検索し、クロールしたページコンテンツを返すWeb検索・スクレイピングサーバー... | 90 ✅ | 199 | [表示](https://agentseal.org/mcp/https-githubcom-apify-mcp-server-rag-web-browser) |
| [mcp-read-website-fast](https://github.com/just-every/mcp-read-website-fast) | Webページを高速に読み取りMarkdownに変換。トークン効率の良いWebブラウジング... | 87 ✅ | 137 | [表示](https://agentseal.org/mcp/https-githubcom-just-every-mcp-read-website-fast) |
| [mcp-screenshot-website-fast](https://github.com/just-every/mcp-screenshot-website-fast) | Webページを高速にスクリーンショットし、LLMフレンドリーなサイズに変換 | 82 ✅ | 103 | [表示](https://agentseal.org/mcp/just-every-mcp-screenshot-website-fast) |
| [oxylabs-mcp](https://github.com/oxylabs/oxylabs-mcp) | Webスクレイピング、JavaScriptレンダリング等を提供する公式Oxylabs統合... | 78 ⚠️ | 88 | [表示](https://agentseal.org/mcp/https-githubcom-oxylabs-oxylabs-mcp) |
| [crawlbase-mcp](https://github.com/crawlbase/crawlbase-mcp) | AIエージェントとLLMをリアルタイムWebデータに接続するCrawlbase MCPサーバー... | 88 ✅ | 52 | [表示](https://agentseal.org/mcp/https-githubcom-crawlbase-crawlbase-mcp) |
| [decodo-mcp-server](https://github.com/Decodo/decodo-mcp-server) | Webスクレイピング、検索、地域制限コンテンツアクセス等を提供するMCPサーバー... | 92 ✅ | 21 | [表示](https://agentseal.org/mcp/https-githubcom-decodo-decodo-mcp-server) |
| [mcp](https://github.com/scrapezy/mcp) | AIモデルがWebサイトから構造化データを抽出できるMCPサーバー... | 88 ✅ | 13 | [表示](https://agentseal.org/mcp/https-githubcom-scrapezy-mcp) |
| [texas-grocery-mcp](https://github.com/mgwalkerjr95/texas-grocery-mcp) | ClaudeをH-E-B食料品店に接続し商品検索等を行うMCPサーバー... | 72 ⚠️ | 13 | [表示](https://agentseal.org/mcp/https-githubcom-mgwalkerjr95-texas-grocery-mcp) |
| [Crawleo-MCP](https://github.com/Crawleo/Crawleo-MCP) | CrawleoのAPIを利用したWeb検索・クロールMCPサーバー... | 84 ✅ | 10 | [表示](https://agentseal.org/mcp/https-githubcom-crawleo-crawleo-mcp) |
| [mcp-web-snapshot](https://github.com/gustavo-meilus/mcp-web-snapshot) | Webサイトのスナップショットを取得しLLMツールに提供。 | 92 ✅ | 5 | [表示](https://agentseal.org/mcp/https-githubcom-gustavo-meilus-mcp-web-snapshot) |
| [anycrawl-mcp-server](https://github.com/any4ai/anycrawl-mcp-server) | AnyCrawl MCPサーバー。スクレイプ、クロール、SERPを提供。 | 73 ⚠️ | 5 | [表示](https://agentseal.org/mcp/https-githubcom-any4ai-anycrawl-mcp-server) |
| [mcpdatafetchserver](https://github.com/undici77/mcpdatafetchserver) | MCP経由でアクセス可能なセキュア・サンドボックス化されたWebコンテンツ取得サービス... | 88 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-undici77-mcpdatafetchserver) |
| [BiliStalkerMCP](https://github.com/222wcnm/BiliStalkerMCP) | ユーザープロフィール、動画、記事等を集約するBilibiliプラットフォームスクレイパー... | 85 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-222wcnm-bilistalkermcp) |
| [mcp](https://github.com/builtwith/mcp) | テクノロジースタックプロファイリングを行うBuiltWith APIの読み取り専用MCPラッパー... | 92 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-builtwith-mcp) |
| [ashra-mcp](https://github.com/getrupt/ashra-mcp) | URLをクロールしてWebページから構造化データを抽出するAshra MCP... | 91 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-getrupt-ashra-mcp) |
| [gopher-mcp](https://github.com/cameronrye/gopher-mcp) | Gopher・Geminiプロトコルリソースを閲覧する読み取り専用MCPクライアント... | 87 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-cameronrye-gopher-mcp) |
| [fiverr-mcp-server](https://github.com/KyuRish/fiverr-mcp-server) | Fiverrの公開マーケットプレイスをスクレイプしてギグを検索する読み取り専用MCPサーバー... | 86 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-kyurish-fiverr-mcp-server) |
| [xhs-mcp](https://github.com/blbl147/xhs-mcp) | Cookie認証で小紅書（中国のSNS）にアクセスするMCPサーバー... | 79 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-blbl147-xhs-mcp) |
| [screaming-frog-mcp](https://github.com/bzsasson/screaming-frog-mcp) | Screaming Frog SEO Spider CLIをラップしてWebサイトのクロール等を行うMCPサーバー... | 79 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-bzsasson-screaming-frog-mcp) |
| [huoshui-fetch](https://github.com/huoshuiai42/huoshui-fetch) | 任意のURLを取得しHTMLを処理するWebコンテンツ取得・処理サーバー... | 78 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-huoshuiai42-huoshui-fetch) |
| [hdw-mcp-server](https://github.com/horizondatawave/hdw-mcp-server) | 投稿の読み取り等を行うマルチプラットフォームSNSスクレイピング・管理MCPサーバー... | 67 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-horizondatawave-hdw-mcp-server) |
| [mcp](https://github.com/hyperbrowserai/mcp) | Webスクレイピング、クロール等を提供するクラウドホスト型ブラウザ自動化プラットフォーム... | 64 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-hyperbrowserai-mcp) |

### 📁 <a name="file-system--storage"></a>ファイルシステム・ストレージ

| サーバー | 説明 | スコア | Stars | レポート |
|----------|------|-------:|------:|----------|
| [hwp-mcp](https://github.com/jkf87/hwp-mcp) | HWPファイル処理用MCP | 87 ✅ | 222 | [表示](https://agentseal.org/mcp/https-githubcom-jkf87-hwp-mcp) |
| [fast-filesystem-mcp](https://github.com/efforthye/fast-filesystem-mcp) | セキュアなファイルシステム操作を提供する高性能Model Context Protocol (MCP)サーバー... | 89 ✅ | 44 | [表示](https://agentseal.org/mcp/https-githubcom-efforthye-fast-filesystem-mcp) |
| [hwpx-mcp](https://github.com/airmang/hwpx-mcp) | HWPアプリなしで韓国のHWPXドキュメントの読み取り・編集・自動化を行うMCPサーバー... | 86 ✅ | 30 | [表示](https://agentseal.org/mcp/https-githubcom-airmang-hwpx-mcp) |
| [pdf-mcp](https://github.com/jztan/pdf-mcp) | ローカルまたはリモートPDFの読み取り・検索・コンテンツ抽出を行うキャッシュ付きPDFサーバー... | 79 ⚠️ | 7 | [表示](https://agentseal.org/mcp/https-githubcom-jztan-pdf-mcp) |
| [server-filesystem](https://github.com/rawr-ai/mcp-filesystem) | 細粒度アクセス制御付きセキュアファイルシステム操作を提供するBunベースMCPサーバー... | 86 ✅ | 3 | [表示](https://agentseal.org/mcp/modelcontextprotocol-server-filesystem) |
| [mcpfileserver](https://github.com/undici77/mcpfileserver) | 制御されたファイルシステム操作を公開するセキュア・サンドボックス化されたファイルサーバー... | 87 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-undici77-mcpfileserver) |
| [mcp-server-spreadsheet](https://github.com/marekrost/mcp-server-spreadsheet) | ローカル環境限定でスプレッドシートファイルの読み書き・クエリを行うMCPサーバー... | 79 ⚠️ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-marekrost-mcp-server-spreadsheet) |
| [fastmcp-pdftools](https://github.com/atarkowska/fastmcp-pdftools) | PDFファイルからテキストを抽出し、ディレクトリ内のPDFを一覧表示するローカルPDFユーティリティサーバー... | 94 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-atarkowska-fastmcp-pdftools) |
| [huoshui-file-converter](https://github.com/huoshuiai42/huoshui-file-converter) | 各種フォーマット間のファイル読み取り・検査・変換を行うファイル変換MCPサーバー... | 84 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-huoshuiai42-huoshui-file-converter) |
| [huoshui-file-search](https://github.com/huoshuiai42/huoshui-file-search) | mdfind Spotlight CLIをラップしてファイルを検索するmacOS専用MCPサーバー... | 83 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-huoshuiai42-huoshui-file-search) |
| [mcp-obsidian](https://github.com/bitbonsai/mcp-obsidian) | Obsidian Markdownボルトへの読み書き等の完全CRUDアクセスを提供... | 82 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-bitbonsai-mcp-obsidian) |
| [hive](https://github.com/mlorentedev/hive) | Obsidianボルトの読み書き・検索アクセスを提供する管理MCPサーバー... | 76 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-mlorentedev-hive) |
| [hillnote-mcp-server](https://github.com/Rajathbail/hillnote-mcp-server) | ドキュメント等をサポートする包括的なノート取得・ワークスペース管理MCPサーバー... | 70 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-rajathbail-hillnote-mcp-server) |

### 💰 <a name="finance--crypto"></a>金融・暗号資産

| サーバー | 説明 | スコア | Stars | レポート |
|----------|------|-------:|------:|----------|
| [investor-agent](https://github.com/ferdousbhai/investor-agent) | 包括的な金融分析、リアルタイム市場データ等を提供するMCPサーバー... | 91 ✅ | 316 | [表示](https://agentseal.org/mcp/https-githubcom-ferdousbhai-investor-agent) |
| [polymarket-mcp](https://github.com/caiovicentino/polymarket-mcp-server) | 🤖 Polymarket向けAI搭載MCPサーバー - Claudeが予測市場で取引可能に... | 84 ✅ | 201 | [表示](https://agentseal.org/mcp/polymarket-mcp) |
| [armor-crypto-mcp](https://github.com/armorwallet/armor-crypto-mcp) | ブロックチェーン、スワップ、戦略立案等と対話するMCPサーバー... | 69 ⚠️ | 191 | [表示](https://agentseal.org/mcp/armor-crypto-mcp) |
| [web3-research-mcp](https://github.com/aaronjmars/web3-research-mcp) | 暗号資産のディープリサーチ - 無料・完全ローカル | 82 ✅ | 153 | [表示](https://agentseal.org/mcp/https-githubcom-aaronjmars-web3-research-mcp) |
| [tradememory-protocol](https://github.com/mnemox-ai/tradememory-protocol) | AI取引エージェントに結果重み付き永続メモリを提供するMCPサーバー... | 91 ✅ | 86 | [表示](https://agentseal.org/mcp/https-githubcom-mnemox-ai-tradememory-protocol) |
| [ynab-mcp-server](https://github.com/calebl/ynab-mcp-server) | AIが予算、取引等と対話できるYNAB家計簿MCPサーバー... | 90 ✅ | 80 | [表示](https://agentseal.org/mcp/https-githubcom-calebl-ynab-mcp-server) |
| [interactive-brokers-mcp](https://github.com/code-rabi/interactive-brokers-mcp) | Interactive Brokers MCPサーバー | 91 ✅ | 77 | [表示](https://agentseal.org/mcp/https-githubcom-code-rabi-interactive-brokers-mcp) |
| [tradingview-chart-mcp](https://github.com/ertugrul59/tradingview-chart-mcp) | Selenium経由でTradingViewチャート画像をキャプチャするMCPサーバー... | 92 ✅ | 73 | [表示](https://agentseal.org/mcp/https-githubcom-ertugrul59-tradingview-chart-mcp) |
| [fantasy-pl-mcp](https://github.com/rishijatia/fantasy-pl-mcp) | Fantasy Premier League MCPサーバー | 84 ✅ | 69 | [表示](https://agentseal.org/mcp/https-githubcom-rishijatia-fantasy-pl-mcp) |
| [kospi-kosdaq-stock-server](https://github.com/dragon1086/kospi-kosdaq-stock-server) | FastMCPを使用してKOSPI/KOSDAQの株式データを提供するMCPサーバー | 92 ✅ | 64 | [表示](https://agentseal.org/mcp/https-githubcom-dragon1086-kospi-kosdaq-stock-server) |
| [mcp](https://github.com/hummingbot/mcp) | ClaudeやGeminiがHummingbotを制御して自動暗号資産取引を行えるMCPサーバー... | 76 ⚠️ | 49 | [表示](https://agentseal.org/mcp/https-githubcom-hummingbot-mcp) |
| [algorand-mcp](https://github.com/GoPlausible/algorand-mcp) | Algorandローカル Model Context Protocol（サーバー & クライアント） | 76 ⚠️ | 41 | [表示](https://agentseal.org/mcp/goplausible-algorand-mcp) |
| [mcp-crypto-price](https://github.com/truss44/mcp-crypto-price) | CoinCap API経由でリアルタイム暗号資産分析を提供するMCPサーバー... | 92 ✅ | 38 | [表示](https://agentseal.org/mcp/https-githubcom-truss44-mcp-crypto-price) |
| [bicscan-mcp](https://github.com/ahnlabio/bicscan-mcp) | ブロックチェーンアドレスのリスクスコアリング・資産分析API MCPサーバー... | 92 ✅ | 16 | [表示](https://agentseal.org/mcp/https-githubcom-ahnlabio-bicscan-mcp) |
| [finbrain-mcp](https://github.com/ahmetsbilgin/finbrain-mcp) | FinBrain金融データAPIの読み取り専用MCPラッパー... | 98 ✅ | 6 | [表示](https://agentseal.org/mcp/https-githubcom-ahmetsbilgin-finbrain-mcp) |
| [mcp-mifosx-self-service](https://github.com/openMF/mcp-mifosx-self-service) | Mifos X - Self Service用MCPサーバー | 84 ✅ | 4 | [表示](https://agentseal.org/mcp/https-githubcom-openmf-mcp-mifosx-self-service) |
| [deepq-financial-toolkit-mcp-server](https://github.com/shenqingtech/deepq-financial-toolkit-mcp-server) | 中国A株市場データを提供する読み取り専用MCPサーバー... | 91 ✅ | 3 | [表示](https://agentseal.org/mcp/https-githubcom-shenqingtech-deepq-financial-toolkit-mcp-server) |
| [expenselm-mcp-server](https://github.com/expenselm/expenselm-mcp-server) | 支出記録への読み取りアクセスを提供する個人経費管理MCPサーバー... | 94 ✅ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-expenselm-expenselm-mcp-server) |
| [mcp-server](https://github.com/azeth-protocol/mcp-server) | ガーディアンガードレール付きEVMスマートアカウント管理用Azethプロトコル MCPサーバー... | 67 ⚠️ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-azeth-protocol-mcp-server) |
| [dolar-mcp](https://github.com/dan1d/dolar-mcp) | アルゼンチンペソおよび外国為替レート（ブルーレート等）をリアルタイムで提供... | 100 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-dan1d-dolar-mcp) |
| [defi-rates-mcp](https://github.com/qingfeng/defi-rates-mcp) | リアルタイムDeFiレンディングレート、イールド市場等を照会する読み取り専用MCPサーバー... | 99 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-qingfeng-defi-rates-mcp) |
| [crypto-signals-mcp](https://github.com/MarcinDudekDev/crypto-signals-mcp) | 50以上の暗号資産トークンの出来高異常等をスキャンする読み取り専用MCPサーバー... | 99 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-marcindudekdev-crypto-signals-mcp) |
| [mcp-server](https://github.com/financial-datasets/mcp-server) | 株式財務、SEC提出書類、価格等へのアクセスを提供する読み取り専用MCPサーバー... | 99 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-financial-datasets-mcp-server) |
| [mcp-server](https://github.com/finmap-org/mcp-server) | 過去の株式市場データ、企業リスト等を提供する読み取り専用MCPサーバー... | 93 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-finmap-org-mcp-server) |
| [hive-crypto-mcp](https://github.com/hive-intel/hive-crypto-mcp) | 暗号資産等の金融市場データへのアクセスを提供する読み取り専用MCPサーバー... | 91 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-hive-intel-hive-crypto-mcp) |
| [maximumsats-mcp](https://github.com/joelklabo/maximumsats-mcp) | Bitcoin AIツールとNostr Web of Trustスコアリング（L402 Lightning対応）用MCPサーバー... | 90 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-joelklabo-maximumsats-mcp) |
| [server-hyperliquid](https://github.com/mektigboy/server-hyperliquid) | Hyperliquid DEXの公開市場データ（ミッドプライス等）への読み取り専用アクセスを提供... | 89 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-mektigboy-server-hyperliquid) |
| [wsb-analyst-mcp](https://github.com/ferdousbhai/wsb-analyst-mcp) | WallStreetBetsのReddit投稿やトレンド銘柄を取得・フィルタリング・分析... | 89 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-ferdousbhai-wsb-analyst-mcp) |
| [mcp-okx](https://github.com/aahl/mcp-okx) | 完全なOKX取引所取引機能を提供するMCPサーバー... | 86 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-aahl-mcp-okx) |
| [expense-mcp](https://github.com/justfsl50/expense-mcp) | Claude Desktop、Cursor等に対応する個人経費トラッカーMCPサーバー... | 86 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-justfsl50-expense-mcp) |
| [fewsats-mcp](https://github.com/Fewsats/fewsats-mcp) | AIエージェントがL402プロトコルで自律的に決済できるMCPサーバー... | 84 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-fewsats-fewsats-mcp) |
| [coinstats-mcp](https://github.com/CoinStatsHQ/coinstats-mcp) | 暗号資産市場データ、ウォレット残高照会等を提供するCoinStats MCPサーバー... | 83 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-coinstatshq-coinstats-mcp) |
| [rug-munch-mcp](https://github.com/CryptoRugMunch/rug-munch-mcp) | ラグプルリスクスコアリング、デプロイヤー履歴、保有者分析等を提供する有料APIサービス... | 82 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-cryptorugmunch-rug-munch-mcp) |
| [sieve-mcp](https://github.com/lmwharton/sieve-mcp) | 7つのカテゴリで企業を審査するAI搭載スタートアップデューデリジェンスプラットフォーム... | 80 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-lmwharton-sieve-mcp) |
| [gloria-mcp](https://github.com/cryptobriefing/gloria-mcp) | 18カテゴリの暗号資産ニュースをリアルタイム集約するGloria AI... | 75 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-cryptobriefing-gloria-mcp) |

### 🧠 <a name="data-science--ml"></a>データサイエンス・ML

| サーバー | 説明 | スコア | Stars | レポート |
|----------|------|-------:|------:|----------|
| [mcp-server-chart](https://github.com/antvis/mcp-server-chart) | 🤖 @antvisを使用した25種以上のビジュアルチャートを含む可視化MCP・スキル... | 92 ✅ | 3.8k | [表示](https://agentseal.org/mcp/antv-mcp-server-chart) |
| [mcp-server-data-exploration](https://github.com/reading-plus-ai/mcp-server-data-exploration) | CSVファイルを分析してインサイトを生成するインタラクティブデータ探索アシスタント... | 85 ✅ | 528 | [表示](https://agentseal.org/mcp/https-githubcom-reading-plus-ai-mcp-server-data-exploration) |
| [chronulus-mcp](https://github.com/ChronulusAI/chronulus-mcp) | Chronulus AI予測・予測エージェント用MCPサーバー | 85 ✅ | 106 | [表示](https://agentseal.org/mcp/https-githubcom-chronulusai-chronulus-mcp) |
| [agrobr-mcp](https://github.com/bruno-portfolio/agrobr-mcp) | ブラジル農業データ用MCPサーバー - LLMを10の公開データソースに接続... | 91 ✅ | 21 | [表示](https://agentseal.org/mcp/https-githubcom-bruno-portfolio-agrobr-mcp) |
| [predictive-maintenance-mcp](https://github.com/LGDiMaggio/predictive-maintenance-mcp) | LLMが振動データ等を分析できるAI搭載予知保全サーバー... | 73 ⚠️ | 19 | [表示](https://agentseal.org/mcp/https-githubcom-lgdimaggio-predictive-maintenance-mcp) |
| [mcp-audiense-insights](https://github.com/audienseco/mcp-audiense-insights) | マーケティングオーディエンス分析用にClaudeをAudiense Insightsに接続するMCPサーバー... | 92 ✅ | 17 | [表示](https://agentseal.org/mcp/https-githubcom-audienseco-mcp-audiense-insights) |
| [fermat-mcp](https://github.com/abhiphile/fermat-mcp) | 🚀 Fermat MCP: 究極の数学エンジン - SymPy、NumPy、Matplotlibを統合... | 97 ✅ | 13 | [表示](https://agentseal.org/mcp/https-githubcom-abhiphile-fermat-mcp) |
| [colabfit-mcp](https://github.com/colabfit/colabfit-mcp) | ColabFit材料科学データセットの検索・ダウンロード用MCPサーバー... | 89 ✅ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-colabfit-colabfit-mcp) |
| [OECD-MCP-server](https://github.com/isakskogstad/OECD-MCP-server) | OECD統計データセットへの読み取り専用アクセスを提供するMCPサーバー... | 87 ✅ | 1 | [表示](https://agentseal.org/mcp/https-githubcom-isakskogstad-oecd-mcp-server) |
| [dataset-viewer](https://github.com/privetin/dataset-viewer) | Hugging Face Datasets Server APIへの読み取り専用インターフェース... | 91 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-privetin-dataset-viewer) |
| [artefact-mcp-server](https://github.com/alexboissAV/artefact-mcp-server) | RFM分析、ICPスコアリング、パイプライン等を行うGTMインテリジェンスMCPサーバー... | 91 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-alexboissav-artefact-mcp-server) |
| [gx-mcp-server](https://github.com/davidf9999/gx-mcp-server) | Great Expectationsフレームワークをラップし、エージェントがデータ品質を検証できるMCPサーバー... | 87 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-davidf9999-gx-mcp-server) |
| [discovery-engine-mcp](https://github.com/leap-laboratories/discovery-engine-mcp) | 統計パターンを発見するDiscovery Engine SaaSプラットフォーム用MCPクライアント... | 78 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-leap-laboratories-discovery-engine-mcp) |
| [fpl-mcp-server](https://github.com/nguyenanhducs/fpl-mcp-server) | AIアシスタントにFantasy Premier Leagueのツール・リソースを提供するMCPサーバー... | 77 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-nguyenanhducs-fpl-mcp-server) |
| [jupyter-mcp-server](https://github.com/ChengJiale150/jupyter-mcp-server) | Jupyterノートブックに接続してプログラム制御するMCPサーバー... | 74 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-chengjiale150-jupyter-mcp-server) |
| [mcp-gemini](https://github.com/crunchtools/mcp-gemini) | テキスト、画像、動画等39ツールを持つGoogle Gemini AI向けセキュアMCPサーバー... | 71 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-gemini) |
| [jupyter-mcp-server](https://github.com/datalayer/jupyter-mcp-server) | ファイル閲覧、ノートブック管理等を行うJupyterサーバー制御用MCPサーバー... | 66 ⚠️ | - | [表示](https://agentseal.org/mcp/https-githubcom-datalayer-jupyter-mcp-server) |

### 📡 <a name="iot--hardware"></a>IoT・ハードウェア

| サーバー | 説明 | スコア | Stars | レポート |
|----------|------|-------:|------:|----------|
| [xiaozhi-esp32-server-java](https://github.com/joey-zhou/xiaozhi-esp32-server-java) | 小智ESP32のJavaエンタープライズ管理プラットフォーム。デバイス監視、カスタマイズ等の統合ソリューション | 92 ✅ | 1.2k | [表示](https://agentseal.org/mcp/https-githubcom-joey-zhou-xiaozhi-esp32-server-java) |
| [droidmind](https://github.com/hyperb1iss/droidmind) | Model Context Protocolを通じてAIでAndroidデバイスを制御... | 71 ⚠️ | 360 | [表示](https://agentseal.org/mcp/https-githubcom-hyperb1iss-droidmind) |
| [hass-mcp](https://github.com/voska/hass-mcp) | Home Assistantスマートホームの制御・監視用MCPサーバー... | 72 ⚠️ | 284 | [表示](https://agentseal.org/mcp/https-githubcom-voska-hass-mcp) |
| [buttplug-mcp](https://github.com/conacademy/buttplug-mcp) | Buttplug.io Model Context Protocol (MCP)サーバー | 92 ✅ | 126 | [表示](https://agentseal.org/mcp/https-githubcom-conacademy-buttplug-mcp) |
| [ble-mcp-server](https://github.com/es617/ble-mcp-server) | Claude Code等のMCP互換ツール向けBluetooth Low Energy (BLE) MCPサーバー... | 75 ⚠️ | 7 | [表示](https://agentseal.org/mcp/https-githubcom-es617-ble-mcp-server) |
| [ble-mcp-server.git](https://github.com/es617/ble-mcp-server.git) | エージェントがBLEデバイスをスキャン、接続等できるBluetooth Low Energy (BLE)管理サーバー... | 67 ⚠️ | 7 | [表示](https://agentseal.org/mcp/https-githubcom-es617-ble-mcp-servergit) |
| [serial-mcp-server.git](https://github.com/es617/serial-mcp-server.git) | ハードウェアデバイスへのシリアルポート接続を管理するMCPサーバー... | 68 ⚠️ | 2 | [表示](https://agentseal.org/mcp/https-githubcom-es617-serial-mcp-servergit) |
| [pcb-mcp](https://github.com/bunnyf/pcb-mcp) | KiCad PCB設計ワークフローを自動化するMCPサーバー - DRC/ERCチェックの実行等... | 92 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-bunnyf-pcb-mcp) |
| [mcp-motor-current-signature-analysis](https://github.com/LGDiMaggio/mcp-motor-current-signature-analysis) | スペクトル分析等を提供するMCSA（モーター電流シグネチャ分析）サーバー... | 92 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-lgdimaggio-mcp-motor-current-signature-analysis) |
| [esp-mcp](https://github.com/horw/esp-mcp) | ESP-IDFファームウェアのビルド、設定、テスト、フラッシュを行うMCPサーバー... | 85 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-horw-esp-mcp) |
| [wemo-mcp-server](https://github.com/apiarya/wemo-mcp-server) | Belkin WeMoスマートプラグの発見、監視、制御を行うMCPサーバー... | 83 ✅ | - | [表示](https://agentseal.org/mcp/https-githubcom-apiarya-wemo-mcp-server) |

## 🏆 最も安全なサーバー (スコア ≥ 95)

| サーバー | スコア | ツール | Stars | レポート |
|----------|-------:|-------:|------:|----------|
| [mcp-summarizer](https://github.com/0xshellming/mcp-summarizer) | 100 | 1 | 157 | [表示](https://agentseal.org/mcp/https-githubcom-0xshellming-mcp-summarizer) |
| [mcp-open-library](https://github.com/8enSmith/mcp-open-library) | 100 | 6 | 62 | [表示](https://agentseal.org/mcp/https-githubcom-8ensmith-mcp-open-library) |
| [mcp_weather_server](https://github.com/isdaniel/mcp_weather_server) | 100 | 8 | 44 | [表示](https://agentseal.org/mcp/https-githubcom-isdaniel-mcpweatherserver) |
| [actor-critic-thinking-mcp](https://github.com/aquarius-wing/actor-critic-thinking-mcp) | 100 | 1 | 32 | [表示](https://agentseal.org/mcp/https-githubcom-aquarius-wing-actor-critic-thinking-mcp) |
| [physbound](https://github.com/JonesRobM/physbound) | 100 | 4 | 1 | [表示](https://agentseal.org/mcp/https-githubcom-jonesrobm-physbound) |
| [brlaw_mcp_server](https://github.com/pdmtt/brlaw_mcp_server) | 100 | 3 | - | [表示](https://agentseal.org/mcp/https-githubcom-pdmtt-brlawmcpserver) |
| [lapalma24-mcp](https://github.com/La-Palma-24/lapalma24-mcp) | 100 | 6 | - | [表示](https://agentseal.org/mcp/https-githubcom-la-palma-24-lapalma24-mcp) |
| [mcp-claude-hackernews](https://github.com/imprvhub/mcp-claude-hackernews) | 100 | 5 | - | [表示](https://agentseal.org/mcp/https-githubcom-imprvhub-mcp-claude-hackernews) |
| [algora-mcp-server](https://github.com/idapixl/algora-mcp-server) | 100 | 5 | - | [表示](https://agentseal.org/mcp/https-githubcom-idapixl-algora-mcp-server) |
| [heatpump-mcp-server](https://github.com/jiweiqi/heatpump-mcp-server) | 100 | 6 | - | [表示](https://agentseal.org/mcp/https-githubcom-jiweiqi-heatpump-mcp-server) |
| [trinvmcp](https://github.com/cqtrinv/trinvmcp) | 100 | 2 | - | [表示](https://agentseal.org/mcp/https-githubcom-cqtrinv-trinvmcp) |
| [bilibili-mcp-server](https://github.com/wangshunnn/bilibili-mcp-server) | 100 | 3 | - | [表示](https://agentseal.org/mcp/https-githubcom-wangshunnn-bilibili-mcp-server) |
| [fabric-mcp-server](https://github.com/adapoet/fabric-mcp-server) | 100 | 1 | - | [表示](https://agentseal.org/mcp/https-githubcom-adapoet-fabric-mcp-server) |
| [time-node-mcp](https://github.com/davidan90/time-node-mcp) | 100 | 4 | - | [表示](https://agentseal.org/mcp/https-githubcom-davidan90-time-node-mcp) |
| [dolar-mcp](https://github.com/dan1d/dolar-mcp) | 100 | 6 | - | [表示](https://agentseal.org/mcp/https-githubcom-dan1d-dolar-mcp) |
| [chrono-mcp](https://github.com/JMoak/chrono-mcp) | 100 | 2 | - | [表示](https://agentseal.org/mcp/https-githubcom-jmoak-chrono-mcp) |
| [crash-mcp](https://github.com/nikkoxgonzales/crash-mcp) | 100 | 1 | - | [表示](https://agentseal.org/mcp/https-githubcom-nikkoxgonzales-crash-mcp) |
| [cookwith-mcp](https://github.com/blaideinc/cookwith-mcp) | 99 | 2 | - | [表示](https://agentseal.org/mcp/https-githubcom-blaideinc-cookwith-mcp) |
| [bilibili-mcp-js](https://github.com/34892002/bilibili-mcp-js) | 99 | 8 | 153 | [表示](https://agentseal.org/mcp/https-githubcom-34892002-bilibili-mcp-js) |
| [gif-creator-mcp](https://github.com/ananddtyagi/gif-creator-mcp) | 99 | 1 | 15 | [表示](https://agentseal.org/mcp/https-githubcom-ananddtyagi-gif-creator-mcp) |

## ⚠️ より広い攻撃対象領域

これらのサーバーは故障しているわけでも悪意があるわけでもありません。コード実行、ファイルシステムアクセス、ネットワークリクエストなどの強力な機能を公開しており、AIエージェントの攻撃対象領域を拡大します。攻撃者はプロンプトインジェクションを通じてこれを悪用する可能性があります。サンドボックス環境での使用と人間の監視を推奨します。

| サーバー | スコア | 検出事項 | ツール | Stars | レポート |
|----------|-------:|---------:|-------:|------:|----------|
| [klavis](https://github.com/klavis-ai/klavis) | 68 | **152** | 554 | 5.7k | [表示](https://agentseal.org/mcp/https-githubcom-klavis-ai-klavis) |
| [labmate-mcp](https://github.com/JonasRackl/labmate-mcp) | 71 | **85** | 81 | - | [表示](https://agentseal.org/mcp/labmate-mcp) |
| [graphlit-mcp-server](https://github.com/graphlit/graphlit-mcp-server) | 72 | **78** | 73 | 372 | [表示](https://agentseal.org/mcp/https-githubcom-graphlit-graphlit-mcp-server) |
| [chat](https://github.com/deco-cx/chat) | 77 | **69** | 188 | - | [表示](https://agentseal.org/mcp/https-githubcom-deco-cx-chat) |
| [armor-crypto-mcp](https://github.com/armorwallet/armor-crypto-mcp) | 69 | **46** | 37 | 191 | [表示](https://agentseal.org/mcp/armor-crypto-mcp) |
| [apisix-mcp](https://github.com/api7/apisix-mcp) | 67 | **43** | 32 | 34 | [表示](https://agentseal.org/mcp/https-githubcom-api7-apisix-mcp) |
| [mcp-gitlab](https://github.com/crunchtools/mcp-gitlab) | 68 | **42** | 63 | - | [表示](https://agentseal.org/mcp/https-githubcom-crunchtools-mcp-gitlab) |
| [freshdesk_mcp](https://github.com/effytech/freshdesk_mcp) | 80 | **40** | 59 | - | [表示](https://agentseal.org/mcp/https-githubcom-effytech-freshdeskmcp) |
| [mcp](https://github.com/hopx-ai/mcp) | 58 | **37** | 35 | - | [表示](https://agentseal.org/mcp/https-githubcom-hopx-ai-mcp) |
| [audius-mcp-atris](https://github.com/glassBead-tc/audius-mcp-atris) | 60 | **36** | 106 | 1 | [表示](https://agentseal.org/mcp/https-githubcom-glassbead-tc-audius-mcp-atris) |
| [mcp_omni_connect](https://github.com/abiorh001/mcp_omni_connect) | 77 | **34** | 273 | - | [表示](https://agentseal.org/mcp/https-githubcom-abiorh001-mcpomniconnect) |
| [memora](https://github.com/agentic-mcp-tools/memora) | 64 | **33** | 35 | 309 | [表示](https://agentseal.org/mcp/https-githubcom-agentic-mcp-tools-memora) |
| [webmin-mcp-server](https://github.com/gjenkins20/webmin-mcp-server) | 70 | **31** | 61 | - | [表示](https://agentseal.org/mcp/https-githubcom-gjenkins20-webmin-mcp-server) |
| [hillnote-mcp-server](https://github.com/Rajathbail/hillnote-mcp-server) | 70 | **31** | 47 | - | [表示](https://agentseal.org/mcp/https-githubcom-rajathbail-hillnote-mcp-server) |
| [hdw-mcp-server](https://github.com/horizondatawave/hdw-mcp-server) | 67 | **31** | 69 | - | [表示](https://agentseal.org/mcp/https-githubcom-horizondatawave-hdw-mcp-server) |

## 📛 セキュリティバッジの追加

READMEにサーバーの信頼スコアを表示:

```markdown
[![AgentSeal MCP](https://agentseal.org/api/v1/mcp/YOUR-SLUG/badge)](https://agentseal.org/mcp/YOUR-SLUG)
```

## 🔍 サーバーの登録

MCPサーバーの無料セキュリティスキャンを受ける:
> [agentseal.org/mcp/submit](https://agentseal.org/mcp/submit)

## コントリビューション

このリストは[AgentSealのMCPレジストリ](https://agentseal.org/mcp)から自動生成されています。
サーバーを追加するには、[スキャン申請を送信](https://agentseal.org/mcp/submit)してください。
誤検知を報告するには、[メールでお知らせください](mailto:hello@agentseal.org)。

## ライセンス

CC BY-SA 4.0 - 帰属表示付きで自由に共有・改変可能。
