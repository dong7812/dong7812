# Dongkyu Lee

**문제를 먼저 이해하고, 직접 만들어 검증합니다.**

기존 도구를 쓰기 전에 그게 왜 필요한지, 어디서 비효율이 생기는지를 먼저 따집니다. 그 과정에서 없으면 직접 만들고, 만든 것은 실제로 써보며 계속 고칩니다.

---

### 주요 프로젝트

| 프로젝트 | 설명 | 배포 |
|---|---|---|
| **[dompruner-mcp](https://github.com/dong7812/dompruner-mcp)** | LLM 웹 파이프라인을 위한 DOM AST 미들웨어. WebFetch 대비 93.5% 토큰 절감, 소형 모델 없음 | ![npm](https://img.shields.io/npm/dm/dompruner-mcp?style=flat-square&label=npm&color=cb3837) |
| **[dompruner-py](https://github.com/dong7812/dompruner-py)** | LangChain 생태계용 Python 포트. `DomPrunerLoader` · `DomPrunerSitemapLoader` · `DomPrunerFetchTool` | ![PyPI](https://img.shields.io/pypi/dm/dompruner?style=flat-square&label=PyPI&color=3775a9) |
| **[huginin-cli](https://github.com/dong7812/huginin-cli)** | AI 세션을 캡처하고 결정 이력을 커밋에 연결하는 CLI | Go |
| **[collab-proof](https://github.com/dong7812/collab-proof)** | 세션 종료 후 AI vs 개발자 기여도를 기록 — 외부 의존성 없음 | Shell |

---

### 설계 판단의 예시

**dompruner를 "범용 크롤러"로 안 만든 이유**
JS 렌더링, auth, proxy를 붙이면 기능은 늘지만 정체성을 잃습니다. 핵심 가치는 "HTML이 주어졌을 때 LLM이 읽을 수 있는 형태로 정제한다"이고, fetch는 편의 레이어입니다. 경계를 그은 덕에 LangChain 미들웨어로서의 역할이 명확해졌습니다.

**MCP와 Python 포트가 다르게 동작하는 이유**
MCP는 LLM이 직접 호출하는 도구라 fetch까지 책임지고 CSR 페이지에서 Playwright를 자동 시도합니다. Python은 개발자가 파이프라인에 끼워 넣는 미들웨어라 fetch는 사용자 몫입니다. 같은 엔진, 다른 역할.

---

### 오픈소스 기여

| 프로젝트 | 기여 내용 | 상태 |
|---|---|---|
| **[ESLint](https://github.com/eslint/eslint)** | `fix: prevent ASI hazard in no-unused-labels autofix` 외 PR 4건 | ✅ Merged |
| **[claude-skills](https://github.com/alirezarezvani/claude-skills)** ⭐24k | collab-proof 스킬 기여 | ✅ Merged |
| **[langchain-ai/docs](https://github.com/langchain-ai/docs)** | dompruner-py를 [Document Loaders 공식 목록](https://docs.langchain.com/oss/python/integrations/document_loaders)에 등재 ([#5424](https://github.com/langchain-ai/docs/pull/5424)) | ✅ Merged |

---

### 스택

`TypeScript` · `Go` · `Python` · `Shell`

MCP · BM25+ · DOM AST · LLM APIs

---

### 관심 분야

- LLM 애플리케이션의 **토큰 효율화** 미들웨어
- **MCP 생태계** — 도구가 조합 가능한 AI 인프라
- 개발자 경험(DevEx) — AI 도구를 더 쉽게 쓸 수 있는 구조 설계
