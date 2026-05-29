# Agent Learning Hub

A curated AI Agent learning roadmap for people who want to build useful, reliable agents instead of collecting random links.

이 저장소는 핵심 전시 화면으로 README 하나만 관리합니다. 목표는 커뮤니티의 훌륭한 공유 글, 공식 블로그, 논문, 오픈소스 프로젝트, 실제 엔지니어링 경험을 실행 가능한 AI Agent 학습 todo list로 정리하는 것입니다.

## Maintainer

Curated by [천쓰저우](https://github.com/jjyaoao) (Datawhale 멤버) <a href="https://www.xiaohongshu.com/user/profile/67b9cc34000000000e013517" target="_blank"><img alt="Static Badge" src="https://img.shields.io/badge/Rednote-샤오홍슈-e93c49"></a>

## How To Use

- 초보자라면: "Learning Todo List"를 위에서 아래로 진행하고, 한 항목을 끝낼 때마다 체크하세요.
- 이미 LLM 앱을 만들 줄 안다면: Stage 2 또는 Stage 3부터 시작해 Agent loop, 도구 호출, 평가, 엔지니어링을 중점적으로 보강하세요.
- 프로젝트를 만들고 싶다면: 바로 "Project Ladder"를 보고 각 단계마다 실행 가능한 결과물을 하나씩 만드세요.
- 자료만 찾고 싶다면: "Curated Resources"를 보고 공식 문서와 고전 논문을 우선 읽으세요.

## What To Learn Now

Agent 분야는 빠르게 변합니다. 지금 더 투자할 만한 것은 오래된 "역할극식 multi-agent 프레임워크"가 아니라 실제 생산성에 더 가까운 다음 방향입니다:

| Priority | Learn | Why |
| --- | --- | --- |
| 1 | Claude Code / Codex-style coding agents | 실제 코드베이스, shell, 파일 편집, 테스트, 권한, 컨텍스트 압축을 다루는 최고의 agent 엔지니어링 샘플입니다. |
| 2 | Agent harness engineering | agent의 역량 중 큰 부분은 harness에서 나옵니다: 도구 프로토콜, 권한, 상태, 피드백, 리플레이, CI, 평가. |
| 3 | OpenClaw / Hermes-style personal agents | 장기 실행, 로컬 우선, 앱 간 연동, 메모리, skills, 메시지 진입점은 "개인 운영체제"에 더 가깝습니다. |
| 4 | Skills / MCP / A2A / ACP | skills는 능력 재사용을 맡고, MCP는 도구를 연결하며, A2A는 agent를 연결하고, ACP는 호스트 앱을 연결합니다. |
| 5 | Evaluation and safety | eval, trace, 권한 경계가 없는 agent는 demo라고 볼 수밖에 없습니다. |

이미 템플릿처럼 일반화된 오래된 crew/role-play 프레임워크에 에너지를 크게 쏟는 것은 권하지 않습니다. 알아둘 수는 있지만 주된 학습 축이 되어서는 안 됩니다.

## Learning Todo List

### Stage 0: Understand What An Agent Is

- [ ] chatbot, workflow, agent, multi-agent를 구분한다.
- [ ] agent의 기본 루프를 이해한다: observe -> think -> act -> observe.
- [ ] 언제 agent를 쓰지 말아야 하는지 이해한다: 작업이 예측 가능하고 흐름이 안정적이며 일반 스크립트로 해결할 수 있다면 agent는 오히려 불확실성을 늘린다.
- [ ] 끝까지 읽기: [Anthropic: Building effective agents](https://www.anthropic.com/engineering/building-effective-agents).
- [ ] 끝까지 읽기: [OpenAI: A practical guide to building agents](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/).

산출물: 한 페이지짜리 짧은 노트를 작성해 "내 상황에는 왜 일반 workflow가 아니라 agent가 필요한가?"에 답한다.

### Stage 1: Build A Minimal Agent Loop

- [ ] 하나의 LLM API로 일반 대화를 구현할 수 있다.
- [ ] 모델이 구조화된 JSON을 출력하게 할 수 있다.
- [ ] search, calculator, read_file 같은 도구 함수를 정의할 수 있다.
- [ ] 모델의 tool call / function call을 파싱할 수 있다.
- [ ] 도구를 실행하고 그 결과를 모델에 다시 전달할 수 있다.
- [ ] agent loop에 최대 단계 수, 타임아웃, 오류 처리를 추가할 수 있다.

추천 읽기:

- [OpenAI Function Calling](https://platform.openai.com/docs/guides/function-calling)
- [Gemini API Function Calling](https://ai.google.dev/gemini-api/docs/function-calling)
- [Claude Tool Use](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/overview)

산출물: 도구를 선택하고 실행한 뒤 최종 답변을 반환할 수 있는 50-150줄짜리 최소 agent.

### Stage 2: Learn Tool Use, RAG, And Memory

- [ ] 검색 증강 생성을 할 수 있다: chunk, embed, retrieve, answer with citations.
- [ ] 검색, 데이터베이스, 파일, 브라우저, 코드 실행을 도구로 연결할 수 있다.
- [ ] 단기 컨텍스트, 세션 메모리, 장기 메모리를 구분할 수 있다.
- [ ] 도구 실패, 빈 결과, 반복 호출, 환각 인용을 처리할 수 있다.
- [ ] agent가 답변에 출처나 근거를 제시하게 할 수 있다.

추천 읽기:

- [LlamaIndex Agents](https://docs.llamaindex.ai/en/stable/use_cases/agents/)
- [LangChain Docs](https://docs.langchain.com/)
- [Gemini API Code Execution](https://ai.google.dev/gemini-api/docs/code-execution)
- [Model Context Protocol](https://modelcontextprotocol.io/)

오픈소스 프로젝트 참고:

| Project | Why It Fits Stage 2 |
| --- | --- |
| [GPT Researcher](https://github.com/assafelovic/gpt-researcher) | "자료 조사 도우미"에 가장 가까운 완성형 제품: 검색, 수집, 선별, 인용, 긴 보고서 생성. |
| [Open Deep Research](https://github.com/langchain-ai/open_deep_research) | LangGraph로 작성된 deep research 예제로, 다중 검색, 상태 관리, 인용 출력을 배우기 좋습니다. |
| [STORM](https://github.com/stanford-oval/storm) | Stanford OVAL의 연구 글쓰기 시스템으로, outline, question asking, 다중 관점 자료 종합을 배우기 좋습니다. |
| [Khoj](https://github.com/khoj-ai/khoj) | 개인 second brain으로, 로컬 문서, 웹페이지, 의미 검색, 장기 메모리를 배우기 좋습니다. |
| [Onyx](https://github.com/onyx-dot-app/onyx) | 엔터프라이즈급 RAG/search assistant로, connectors, hybrid search, 권한, 프로덕션화를 배우기 좋습니다. |
| [AnythingLLM](https://github.com/Mintplex-Labs/anything-llm) | 로컬 RAG + agents 제품으로, 초보자가 완성형 앱 구조를 빠르게 이해하기 좋습니다. |
| [RAGFlow](https://github.com/infiniflow/ragflow) | 문서 이해형 RAG 엔진으로, ingestion, chunking, retrieval, grounded answer를 배우기 좋습니다. |
| [mem0](https://github.com/mem0ai/mem0) | 메모리 계층 컴포넌트로, agent에 장기 memory를 추가하는 방법을 배우기 좋습니다. |
| [Letta](https://github.com/letta-ai/letta) | stateful agents를 위한 memory/context 플랫폼으로, 컨텍스트 관리를 배우기 좋습니다. |

산출물: 주제를 입력하면 자동으로 검색, 선별, 요약하고 인용 링크를 출력하는 자료 조사 도우미.

### Stage 3: Study One Modern Agent Harness

먼저 현대적인 agent 시스템 하나를 골라 깊이 학습하세요. 핵심은 "프레임워크 API를 어떻게 호출하는가"가 아니라 도구, 컨텍스트, 권한, 상태, 로그, 하위 작업, 피드백을 어떻게 조직하는가입니다.

| System | Best For | Learn This If You Want To |
| --- | --- | --- |
| [Claude Code Docs](https://code.claude.com/docs/en/overview) | Coding agent product | 실제 coding agent의 CLI, 도구, 권한, hooks, subagents, MCP를 배웁니다. |
| [learn-claude-code](https://github.com/shareAI-lab/learn-claude-code) | From-scratch agent harness | 0에서 1까지 Claude Code-like harness를 재현합니다. |
| [claw0](https://github.com/shareAI-lab/claw0) | From-scratch OpenClaw gateway | agent loop부터 session, channel, gateway, memory, heartbeat, delivery, resilience, concurrency까지 구축합니다. |
| [hello-agents](https://github.com/datawhalechina/hello-agents) | Chinese agent tutorial | 처음부터 지능형 agent를 구축하며 Agent 원리와 실습을 체계적으로 보강하기 좋습니다. |
| [OpenClaw](https://github.com/openclaw/openclaw) | Local-first personal agent | 로컬 장기 실행 agent, skills, 메시지 진입점, 시스템 도구, 보안 경계를 배웁니다. |
| [Hermes Agent](https://github.com/NousResearch/hermes-agent) | Self-hosted growing agent | 장기 메모리, skills, toolsets, 멀티 플랫폼 메시지 게이트웨이, 마이그레이션 역량을 배웁니다. |
| [CyberClaw](https://github.com/ttguy0707/CyberClaw) | Transparent agent architecture | 전체 행동 감사, 2단계 안전 호출, 이중 수위 메모리, heartbeat 작업을 배웁니다. |
| [LangGraph](https://langchain-ai.github.io/langgraph/) | Stateful graph orchestration | 상태 그래프, 재개 가능한 실행, 제어 가능한 오케스트레이션을 배웁니다. |

- [ ] agent harness 하나의 디렉터리 구조를 읽고 이해한다.
- [ ] 그 안의 agent loop, tool registry, permission gate, session store, context compaction을 찾아낸다.
- [ ] 최소 예제를 실행하고 자신만의 도구 하나를 추가한다.
- [ ] 완전한 trace 하나를 관찰하고 각 단계가 왜 발생했는지 설명한다.
- [ ] 같은 작업을 "bare agent loop"와 "harness"로 각각 구현하고 차이를 비교한다.

산출물: 디버깅 가능한 agent harness demo. README, 실행 단계, 예제 입출력, 실패 기록을 포함한다.

### Stage 4: Multi-Agent Is Coordination, Not Magic

- [ ] planner / executor / reviewer / critic / router 같은 흔한 역할을 이해한다.
- [ ] agent끼리 마음대로 대화하게 두는 대신 supervisor 또는 graph로 multi-agent를 관리하는 법을 배운다.
- [ ] 각 agent의 책임 경계, 입출력 schema, 중지 조건을 정의할 수 있다.
- [ ] 루프, 논쟁, 작업 표류, 컨텍스트 팽창을 처리할 수 있다.
- [ ] 언제 단일 agent가 더 나은지 판단할 수 있다.

추천 읽기:

- [Claude Code Subagents](https://code.claude.com/docs/en/sub-agents)
- [Claude Code Hooks](https://code.claude.com/docs/en/hooks)
- [Google Agent Development Kit](https://google.github.io/adk-docs/)
- [Agent2Agent Protocol](https://google-a2a.github.io/A2A/specification/)
- [Agent Client Protocol](https://agentclientprotocol.com/)

산출물: research -> write -> review -> revise 같은 소형 multi-agent 시스템.

### Stage 5: Learn Skills, Protocols, And Capability Packaging

현대 agent의 역량은 모델과 도구뿐 아니라 재사용 가능한 skills에서도 나옵니다. 좋은 skill은 작은 운영 매뉴얼과 같아서 agent에게 언제 쓰고, 어떻게 쓰며, 어떤 스크립트/리소스가 필요하고, 결과를 어떻게 검증할지 알려줍니다.

- [ ] Skill과 Tool의 차이를 이해한다: tool은 호출 가능한 인터페이스이고, skill은 재사용 가능한 절차 지식이다.
- [ ] Skill과 Prompt의 차이를 이해한다: prompt는 보통 일회성 지시이고, skill은 발견 가능하고 버전 관리되며 배포 가능한 능력 패키지다.
- [ ] Skill과 MCP의 차이를 이해한다: MCP는 외부 도구/데이터 소스를 연결하고, skill은 agent에게 특정 유형의 작업을 완료하는 방법을 알려준다.
- [ ] Claude Code Skills의 파일 구조와 트리거 메커니즘을 읽는다.
- [ ] OpenClaw Skills의 로딩, 스코프, 보안 경계를 읽는다.
- [ ] name, description, 사용 시점, 단계, 검수 기준을 포함한 최소 `SKILL.md`를 작성한다.
- [ ] skill에 스크립트나 템플릿 파일을 추가하고 agent가 언제 그것을 로드해야 하는지 설명한다.
- [ ] skill에 smoke test를 작성해 실제로 작업 성공률을 높이는지 검증한다.

추천 읽기:

- [Claude Code Skills](https://code.claude.com/docs/en/skills)
- [Claude Agent Skills](https://docs.claude.com/en/docs/agents-and-tools/agent-skills)
- [Claude Code Agent SDK Skills](https://code.claude.com/docs/en/agent-sdk/skills)
- [OpenClaw Skills](https://github.com/openclaw/openclaw/blob/main/docs/tools/skills.md)
- [Model Context Protocol](https://modelcontextprotocol.io/)
- [Agent2Agent Protocol](https://google-a2a.github.io/A2A/specification/)
- [Agent Client Protocol](https://agentclientprotocol.com/)

산출물: code-review, research-report, migration-helper, pdf-extraction, release-note-writer 같은 재사용 가능한 skill.

### Stage 6: Browser And Computer-Use Agents

- [ ] browser agent와 일반 API tool의 차이를 이해한다.
- [ ] Playwright 또는 browser-use로 웹페이지 관찰과 클릭을 수행할 수 있다.
- [ ] 브라우저 작업에 안전 제한을 추가할 수 있다: 민감한 계정에 로그인하지 않고, 권한을 넘지 않으며, 플랫폼 규칙을 우회하지 않는다.
- [ ] 페이지 변화, 팝업, 로드 실패, 요소 위치 찾기 실패를 처리할 수 있다.
- [ ] 스크린샷, DOM, 동작 로그를 기록해 사후 검토를 쉽게 할 수 있다.

추천 읽기:

- [Claude Computer Use](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/computer-use-tool)
- [browser-use](https://github.com/browser-use/browser-use)
- [WebArena](https://arxiv.org/abs/2307.13854)
- [VisualWebArena](https://arxiv.org/abs/2401.13649)

산출물: 공개 웹페이지만 조작하는 browser agent. 예: 웹페이지 열기, 정보 추출, 요약 생성.

### Stage 7: Evaluation, Observability, And Safety

- [ ] demo만 보지 말고 agent용 고정 테스트 세트를 준비한다.
- [ ] 성공률, 실패 원인, 도구 호출 횟수, 비용, 지연 시간을 기록한다.
- [ ] trace를 읽고 실패가 prompt, 도구, 검색, 모델, 상태 관리 중 어디에서 발생했는지 알 수 있다.
- [ ] 메일 발송, 파일 삭제, 결제, 콘텐츠 게시 같은 위험 도구에는 사람 확인을 추가한다.
- [ ] prompt injection, data exfiltration, tool abuse 같은 위험을 이해한다.
- [ ] 회귀 테스트로 prompt나 도구 변경 후 역량이 퇴화하지 않도록 막을 수 있다.

추천 읽기:

- [OpenAI Evals](https://platform.openai.com/docs/guides/evals)
- [OpenAI Agent platform](https://openai.com/agent-platform/)
- [LangSmith](https://docs.smith.langchain.com/)
- [AgentBench](https://arxiv.org/abs/2308.03688)
- [SWE-bench](https://arxiv.org/abs/2310.06770)

산출물: 최소 20개 작업, 기대 결과, 실제 결과, 실패 분류를 포함한 agent eval 표.

### Stage 8: Ship A Real Agent

- [ ] 명확한 사용자, 명확한 작업, 명확한 성공 기준이 있다.
- [ ] 로그, trace, 오류 재시도, 타임아웃, 비용 상한이 있다.
- [ ] 권한 경계와 사람 확인 메커니즘이 있다.
- [ ] 배포 방식이 있다: CLI, Web app, Slack bot, GitHub Action 또는 백그라운드 작업.
- [ ] README가 있다: 실행 방법, key 설정 방법, 도구 확장 방법, 제한 사항.

산출물: 다른 사람이 clone해서 실행할 수 있는 agent 프로젝트.

## Project Ladder

| Level | Project | What You Learn |
| --- | --- | --- |
| 1 | Calculator Agent | 최소 tool call loop |
| 2 | Web Research Agent | 검색, 선별, 인용, 요약 |
| 3 | PDF QA Agent | RAG, chunk, retrieval, citation |
| 4 | Coding Review Agent | diff 읽기, 위험도 정렬, 테스트 제안 |
| 5 | Browser Agent | 페이지 관찰, 클릭, 추출, 실패 복구 |
| 6 | Claude Code-like Nano Agent | shell, 파일 편집, 권한, session, compact |
| 7 | OpenClaw-like Gateway | channel, routing, session, memory, heartbeat, delivery |
| 8 | Reusable Skill Pack | SKILL.md, 스크립트, 템플릿, 트리거 조건, smoke test |
| 9 | Multi-Agent Writer | planner, writer, reviewer 협업 |
| 10 | Personal Agent | OpenClaw/Hermes-style 메모리, skills, 메시지 진입점 |
| 11 | Production Harness | evals, trace, 권한, CI, runner, 리플레이 |

## Curated Resources

### Official Guides And Blogs

| Resource | Why It Matters |
| --- | --- |
| [Anthropic: Building effective agents](https://www.anthropic.com/engineering/building-effective-agents) | Agent 설계 입문 필독 자료로, workflow와 agent의 경계를 명확히 설명합니다. |
| [Claude Code Overview](https://code.claude.com/docs/en/overview) | 현재 가장 연구할 만한 coding agent 제품 문서의 입구입니다. |
| [Claude Code Subagents](https://code.claude.com/docs/en/sub-agents) | 작업 분해, 컨텍스트 격리, 전용 subagent를 배웁니다. |
| [Claude Code Hooks](https://code.claude.com/docs/en/hooks) | agent 동작을 가로채고 검증하고 확장하는 방법을 배웁니다. |
| [Claude Code GitHub Actions](https://docs.claude.com/en/docs/claude-code/github-actions) | coding agent가 PR / issue workflow에 들어가는 방법을 배웁니다. |
| [Claude Code Advanced Patterns](https://resources.anthropic.com/hubfs/Claude%20Code%20Advanced%20Patterns_%20Subagents%2C%20MCP%2C%20and%20Scaling%20to%20Real%20Codebases.pdf) | Anthropic 공식 자료로, subagents, MCP, 실제 코드베이스 확장을 다룹니다. |
| [OpenAI: A practical guide to building agents](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/) | 제품 및 엔지니어링 팀을 위한 agent 도입 가이드입니다. |
| [OpenAI: New tools for building agents](https://openai.com/index/new-tools-for-building-agents/) | Responses API, Agents SDK, 도구, tracing에 대한 공식 소개입니다. |
| [OpenAI Agents SDK](https://platform.openai.com/docs/guides/agents-sdk/) | OpenAI 네이티브 agent 개발 입구입니다. |
| [Claude Tool Use](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/overview) | Claude 도구 호출 메커니즘입니다. |
| [Claude Computer Use](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/computer-use-tool) | 컴퓨터 조작형 agent에 대한 공식 참고 자료입니다. |
| [Gemini Function Calling](https://ai.google.dev/gemini-api/docs/function-calling) | Gemini 도구 호출 공식 문서입니다. |
| [Gemini Code Execution](https://ai.google.dev/gemini-api/docs/code-execution) | Gemini 코드 실행 도구입니다. |
| [Google Agent Development Kit](https://google.github.io/adk-docs/) | Google의 agent 개발 프레임워크입니다. |
| [Model Context Protocol](https://modelcontextprotocol.io/) | Agent가 도구와 데이터 소스를 연결하는 중요한 프로토콜입니다. |

### Project Map

프로젝트를 star 수만 보고 무작정 읽지 말고, 학습 목적별로 나눠 보세요:

| Layer | Study These | Learn |
| --- | --- | --- |
| Build From Scratch | [learn-claude-code](https://github.com/shareAI-lab/learn-claude-code), [claw0](https://github.com/shareAI-lab/claw0), [hello-agents](https://github.com/datawhalechina/hello-agents) | agent loop, tool registry, session, context compaction, gateway, trace, subagents. |
| Personal / Always-On Agents | [OpenClaw](https://github.com/openclaw/openclaw), [Hermes Agent](https://github.com/NousResearch/hermes-agent), [CyberClaw](https://github.com/ttguy0707/CyberClaw) | 장기 실행, skills, 메모리, 메시지 진입점, 권한, 보안 감사. |
| Coding Agents | [Claude Code](https://code.claude.com/docs/en/overview), [OpenAI Codex](https://github.com/openai/codex), [OpenCode](https://github.com/opencode-ai/opencode), [OpenHands](https://github.com/All-Hands-AI/OpenHands), [SWE-agent](https://github.com/SWE-agent/SWE-agent), [pi](https://github.com/earendil-works/pi) | 실제 코드베이스 편집, shell, 테스트, sandbox, PR workflow. |
| Deep Research / RAG Agents | [DeerFlow](https://github.com/bytedance/deer-flow), [LlamaIndex](https://docs.llamaindex.ai/) | 검색, 수집, retrieval, rerank, 인용, 보고서 생성. |
| Tutorial Encyclopedias | [GenAI_Agents](https://github.com/NirDiamant/GenAI_Agents), [hello-agents](https://github.com/datawhalechina/hello-agents), [smolagents](https://github.com/huggingface/smolagents), [agents-towards-production](https://github.com/NirDiamant/agents-towards-production) | ReAct, Plan-and-Execute, Multi-Agent, production patterns를 가로로 비교합니다. |
| Browser / Multimodal Agents | [browser-use](https://github.com/browser-use/browser-use), [UI-TARS-desktop](https://github.com/bytedance/UI-TARS-desktop) | 브라우저/데스크톱 조작, 시각 이해, 동작 공간, 실패 복구. |

### Skills, Protocols, And Tooling

| Concept | Learn From | What It Solves |
| --- | --- | --- |
| Skills | [Claude Code Skills](https://code.claude.com/docs/en/skills), [OpenClaw Skills](https://github.com/openclaw/openclaw/blob/main/docs/tools/skills.md) | 특정 작업 유형의 절차 지식, 스크립트, 템플릿, 검수 기준을 재사용 가능한 능력으로 패키징합니다. |
| MCP | [Model Context Protocol](https://modelcontextprotocol.io/) | agent가 외부 도구, 데이터 소스, 서비스를 표준 방식으로 연결하게 합니다. |
| A2A | [Agent2Agent Protocol](https://google-a2a.github.io/A2A/specification/) | 서로 다른 agent가 발견, 통신, 협업할 수 있게 합니다. |
| ACP | [Agent Client Protocol](https://agentclientprotocol.com/) | 에디터, 터미널, IDE, 호스트 앱, agent 사이에 통합 인터페이스를 만듭니다. |
| Skill Quality | [SWE-Skills-Bench](https://arxiv.org/abs/2603.15401), [Agent Skills analysis](https://arxiv.org/abs/2602.08004) | skills가 새로운 prompt 잡음을 만드는 대신 실제로 성공률을 높이는지 평가합니다. |

### Modern Agent Systems

| System | Why It Is Useful |
| --- | --- |
| [Claude Code](https://code.claude.com/docs/en/overview) | coding agent의 제품화 형태를 배웁니다: shell, 파일, 권한, hooks, subagents, MCP. |
| [learn-claude-code](https://github.com/shareAI-lab/learn-claude-code) | 처음부터 Claude Code-like nano agent를 만들며 harness engineering을 이해하기 좋습니다. |
| [claw0](https://github.com/shareAI-lab/claw0) | 처음부터 OpenClaw-like agent gateway를 만들며 channel, routing, session, memory, delivery, concurrency를 다룹니다. |
| [hello-agents](https://github.com/datawhalechina/hello-agents) | 중국어 agent 시스템 튜토리얼로, Agent 원리와 실습을 처음부터 보강하기 좋습니다. |
| [OpenClaw](https://github.com/openclaw/openclaw) | 로컬 우선 개인 agent로, 장기 실행 agent와 시스템 수준 도구 호출을 연구하기 좋습니다. |
| [Hermes Agent](https://github.com/NousResearch/hermes-agent) | 셀프 호스팅, 장기 메모리, skills, 메시지 게이트웨이, toolsets. |
| [CyberClaw](https://github.com/ttguy0707/CyberClaw) | 투명하고 제어 가능한 agent 아키텍처로, 감사, 2단계 실행, 보안 경계를 연구하기 좋습니다. |
| [DeerFlow](https://github.com/bytedance/deer-flow) | ByteDance 오픈소스 long-horizon SuperAgent harness로, Deep Research, 보고서, slides, 웹페이지, 이미지, 비디오 생성을 연구하기 좋습니다. |
| [smolagents](https://github.com/huggingface/smolagents) | Hugging Face의 경량 agent 프레임워크로, CodeAgent 접근법을 연구할 만합니다. |
| [LangGraph](https://langchain-ai.github.io/langgraph/) | 상태 그래프와 제어 가능한 agent 오케스트레이션으로, 여전히 엔지니어링 기초로 배울 가치가 있습니다. |
| [Qwen-Agent](https://github.com/QwenLM/Qwen-Agent) | 중국 모델 생태계의 도구 호출, RAG, MCP agent 프레임워크입니다. |
| [Pydantic AI](https://pydantic.dev/docs/ai/core-concepts/agent/) | 타입 안전성과 구조화 출력을 제공하며, 프로덕션 Python agent에 적합합니다. |
| [pi](https://github.com/earendil-works/pi) | AI agent toolkit(TypeScript), coding agent CLI, agent core, 통합 멀티 제공자 LLM API, TUI 라이브러리를 포함하며 자체 확장을 지원합니다. |

### Legacy Or Optional Frameworks

이 프로젝트들은 여전히 참고 가치가 있지만 현재 학습의 주축으로 삼는 것은 권하지 않습니다.

| Framework | Note |
| --- | --- |
| [CrewAI](https://docs.crewai.com/) | role/task/crew 추상화를 이해할 수 있지만, 많은 상황은 이미 더 강력한 coding agent / harness 형태로 대체되었습니다. |
| [AutoGen](https://microsoft.github.io/autogen/) | multi-agent 대화 프레임워크의 고전 프로젝트로, 역사와 논문을 이해하기 좋지만 크게 집중할 필요는 없습니다. |
| [LangChain Agents](https://docs.langchain.com/) | 생태계는 여전히 중요하지만 LangGraph와 구체적인 엔지니어링 패턴에 더 집중하는 것을 권합니다. |

### Papers

| Paper | Topic |
| --- | --- |
| [ReAct](https://arxiv.org/abs/2210.03629) | Reasoning + acting의 기본 패러다임. |
| [Toolformer](https://arxiv.org/abs/2302.04761) | 모델이 언제 도구를 호출할지 학습합니다. |
| [Reflexion](https://arxiv.org/abs/2303.11366) | 언어 피드백과 자기 개선. |
| [Generative Agents](https://arxiv.org/abs/2304.03442) | 메모리, 성찰, 계획 기반 시뮬레이션 agent. |
| [Voyager](https://arxiv.org/abs/2305.16291) | 오픈 월드에서의 장기 학습 agent. |
| [AutoGen](https://arxiv.org/abs/2308.08155) | multi-agent 대화 프레임워크. |
| [AgentBench](https://arxiv.org/abs/2308.03688) | Agent 역량 평가. |
| [WebArena](https://arxiv.org/abs/2307.13854) | 실제 웹 환경에서의 agent benchmark. |
| [SWE-bench](https://arxiv.org/abs/2310.06770) | 실제 GitHub issue 수정 평가. |
| [SWE-agent](https://arxiv.org/abs/2405.15793) | 소프트웨어 엔지니어링 agent의 agent-computer interface. |
| [Dive into Claude Code](https://arxiv.org/abs/2604.14228) | 시스템 설계 관점에서 Claude Code 같은 coding agent의 harness, 권한, 압축, 확장 메커니즘을 분석합니다. |
| [AI Harness Engineering](https://arxiv.org/abs/2605.13357) | harness를 agent 역량의 원천으로 연구합니다. |
| [Configuring Agentic AI Coding Tools](https://arxiv.org/abs/2602.14690) | Claude Code, Codex, Gemini, Cursor 같은 coding tools의 설정 메커니즘 분석. |
| [Your Agent, Their Asset](https://arxiv.org/abs/2604.04759) | OpenClaw 같은 로컬 agent의 실제 보안 위험 분석. |

### GitHub Repositories

| Repo | Why It Is Useful |
| --- | --- |
| [datawhalechina/hello-agents](https://github.com/datawhalechina/hello-agents) | 중국어 agent 시스템 튜토리얼로, 처음부터 agent를 구축합니다. |
| [shareAI-lab/learn-claude-code](https://github.com/shareAI-lab/learn-claude-code) | Bash is all you need, 0에서 1까지 Claude Code-like agent harness를 배웁니다. |
| [shareAI-lab/claw0](https://github.com/shareAI-lab/claw0) | 0에서 1까지 OpenClaw-like gateway를 배우며, 10개의 점진적 장이 agent loop부터 concurrency까지 다룹니다. |
| [openclaw/openclaw](https://github.com/openclaw/openclaw) | 로컬 개인 agent, skills, 장기 실행 작업, 시스템 도구, 권한 경계를 연구합니다. |
| [NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent) | 셀프 호스팅 agent, 장기 메모리, skills, toolsets, 멀티 플랫폼 메시지 게이트웨이를 연구합니다. |
| [ttguy0707/CyberClaw](https://github.com/ttguy0707/CyberClaw) | 투명한 agent, 보안 감사, 2단계 실행, 이중 수위 메모리, heartbeat 작업을 연구합니다. |
| [bytedance/deer-flow](https://github.com/bytedance/deer-flow) | Deep Research / long-horizon agent로, 검색, 보고서 생성, 샌드박스, memory, skills, subagents, message gateway를 배우기 좋습니다. |
| [NirDiamant/GenAI_Agents](https://github.com/NirDiamant/GenAI_Agents) | 종합 튜토리얼 저장소로, ReAct, Plan-and-Execute, Multi-Agent 등의 구현 방식을 가로로 비교하기 좋습니다. |
| [NirDiamant/agents-towards-production](https://github.com/NirDiamant/agents-towards-production) | production-grade agent 튜토리얼 저장소로, 엔지니어링 컴포넌트를 보강하기 좋습니다. |
| [huggingface/smolagents](https://github.com/huggingface/smolagents) | 경량 CodeAgent 스타일 프레임워크로, "모델이 코드를 써서 동작을 실행하게 하는" 패러다임을 연구하기 좋습니다. |
| [openai/codex](https://github.com/openai/codex) | OpenAI 오픈소스 coding agent CLI로, sandbox, approval, CLI 제품 형태를 연구하기 좋습니다. |
| [opencode-ai/opencode](https://github.com/opencode-ai/opencode) | 터미널 우선 오픈소스 coding agent로, Claude Code / Codex와 비교하기 좋습니다. |
| [langchain-ai/langgraph](https://github.com/langchain-ai/langgraph) | 상태 그래프와 제어 가능한 agent 오케스트레이션. |
| [openai/openai-agents-python](https://github.com/openai/openai-agents-python) | OpenAI Agents SDK Python. |
| [QwenLM/Qwen-Agent](https://github.com/QwenLM/Qwen-Agent) | Qwen 생태계 agent 프레임워크. |
| [browser-use/browser-use](https://github.com/browser-use/browser-use) | 브라우저 agent 실전. |
| [bytedance/UI-TARS-desktop](https://github.com/bytedance/UI-TARS-desktop) | 멀티모달 데스크톱 agent stack으로, 시각 UI 조작을 연구하기 좋습니다. |
| [SWE-agent/SWE-agent](https://github.com/SWE-agent/SWE-agent) | 소프트웨어 엔지니어링 agent. |
| [All-Hands-AI/OpenHands](https://github.com/All-Hands-AI/OpenHands) | 오픈소스 coding agent. |
| [microsoft/ai-agents-for-beginners](https://github.com/microsoft/ai-agents-for-beginners) | 체계적인 입문 과정. |
| [jjyaoao/HelloAgents](https://github.com/jjyaoao/HelloAgents) | OpenAI 네이티브 API 기반의 프로덕션급 multi-agent 프레임워크로, ToolResponse, 컨텍스트 엔지니어링, 세션 지속화, subagent, TraceLogger 등을 다룹니다. |
| [earendil-works/pi](https://github.com/earendil-works/pi) | TypeScript로 작성된 AI agent toolkit으로, pi-coding-agent CLI, pi-agent-core 런타임, pi-ai(통합 멀티 제공자 LLM API), pi-tui(터미널 UI 라이브러리)를 포함하며 Slack bot과 vLLM pods를 지원합니다. |

### Thoughtful Blogs

| Blog | Why It Is Useful |
| --- | --- |
| [Lilian Weng: LLM Powered Autonomous Agents](https://lilianweng.github.io/posts/2023-06-23-agent/) | 고전적인 장문 글로, agent 아키텍처, 메모리, 계획, 도구 사용을 체계적으로 정리합니다. |
| [Simon Willison: AI/LLM writing](https://simonwillison.net/tags/llms/) | 매우 실용적인 LLM 엔지니어링 관찰로, 엔지니어링 감각을 보강하기 좋습니다. |
| [LangChain Blog](https://blog.langchain.com/) | LangGraph, LangSmith, agent 엔지니어링 실무. |
| [Google Developers Blog: ADK](https://developers.googleblog.com/agent-development-kit-easy-to-build-multi-agent-applications/) | Google ADK 공식 발표 글. |

### Claude Code Study Path

Claude Code는 현재 가장 분해해 볼 만한 coding agent 제품 중 하나입니다. "공식 문서 -> 재현 프로젝트 -> 아키텍처 분석 -> 엔지니어링 비교" 순서로 학습하는 것을 권합니다:

- 공식 문서를 읽고 hooks, subagents, MCP, GitHub Actions, permissions를 이해합니다.
- 공개 분석 논문을 읽고 agent harness의 설계 공간을 추상화합니다.
- [learn-claude-code](https://github.com/shareAI-lab/learn-claude-code)를 따라 처음부터 핵심 메커니즘을 재현합니다.
- [hello-agents](https://github.com/datawhalechina/hello-agents), [OpenClaw](https://github.com/openclaw/openclaw), [Hermes Agent](https://github.com/NousResearch/hermes-agent) 같은 오픈소스 프로젝트와 비교하며 엔지니어링 구현을 배웁니다.

| Resource | Focus |
| --- | --- |
| [Claude Code Common Workflows](https://code.claude.com/docs/en/tutorials) | 공식 workflow 튜토리얼로, 일상 사용과 프로젝트 협업을 배우기 좋습니다. |
| [Claude Code Overview](https://code.claude.com/docs/en/overview) | 공식 입구로, 제품 역량과 명령줄 작동 방식을 이해합니다. |
| [learn-claude-code](https://github.com/shareAI-lab/learn-claude-code) | 처음부터 Claude Code-like agent를 재현하며 harness 최소 구현을 배우기 좋습니다. |
| [Claude Code 소스 코드 분석](https://claudecoding.dev/) | 중국어 아키텍처 해설로, 모듈별 구현 사고를 이해하기 좋습니다. |
| [Claude Code 소스 코드 분석 지도](https://code.claudecn.com/) | 지도 방식으로 agent loop, 도구, 명령, multi-agent 협업을 분해합니다. |
| [Dive into Claude Code](https://arxiv.org/abs/2604.14228) | 연구 관점에서 Claude Code의 설계 공간과 agent harness 패턴을 요약합니다. |
| [Agentic Education](https://arxiv.org/abs/2604.17460) | Claude Code로 Claude Code를 배우는 인터랙티브 코스 아이디어. |

## Learning Principles

- Build first, then read deeper.
- Prefer small reliable agents over impressive demos.
- Use tools with strict schemas.
- Add evals before you add more agents.
- Trace every important run.
- Treat multi-agent as a coordination problem.
- Keep humans in the loop for risky actions.
- Respect platform rules, copyrights, and data access boundaries.

## Contributing

Good contributions are welcome. Please prefer:

- official docs and official engineering blogs;
- high-quality papers and benchmarks;
- open-source repositories with runnable code;
- serious technical blogs with original insight;
- small projects that help learners practice one specific skill.

Please avoid:

- copied platform posts;
- course ads without substantial content;
- private or paywalled material;
- scraping-oriented content that bypasses platform rules.
