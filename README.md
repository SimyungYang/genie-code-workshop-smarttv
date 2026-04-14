# LGE MS사업본부 Vibe Coding 워크샵

> **교육 일시**: 2026년 4월 22일 | **대상**: LG전자 MS(Media Solution)사업본부

Databricks 환경에서 **Genie Code**와 **AI Dev Kit**을 활용한 Vibe Coding 실습 워크샵입니다.

LG Smart TV webOS 텔레메트리 데이터를 기반으로, 자연어 프롬프트만으로 데이터 파이프라인부터 AI 에이전트까지 End-to-End로 구축합니다.

> **학습 트랙**: 이 워크샵은 **Genie Code (Track C)** 전용입니다. 모든 실습을 Genie Code Agent Mode로 진행합니다.

---

## 타임테이블

| 시간 | 섹션 | 내용 | 소요 |
|------|------|------|------|
| 09:30~10:00 | **Section 1** | Vibe Coding 리소스 소개 (Genie Code, AI Dev Kit, AI Builder App) | 30분 |
| 10:00~10:30 | **Section 2** | AI Dev Kit MCP 서버 앱 배포 핸즈온 | 30분 |
| 10:30~11:00 | **Section 3** | Genie Code에 AI Dev Kit 연결 + Skills 배포 | 30분 |
| 11:00~11:10 | ☕ | 휴식 | 10분 |
| 11:10~11:15 | **Section 4-01** | 환경 설정 (카탈로그/스키마) | 5분 |
| 11:15~11:30 | **Section 4-02** | 가상 데이터 생성 (250만건) | 15분 |
| 11:30~12:30 | **Section 4-03** | SDP 파이프라인 — 데이터 품질 + 증분 처리 | 1시간 |
| 12:30~13:30 | 🍚 | 점심 | 1시간 |
| 13:30~15:00 | **Section 4-04** | AI/BI 대시보드 & Genie Space + 정확도 고도화 | 1.5시간 |
| 15:00~15:10 | ☕ | 휴식 | 10분 |
| 15:10~17:10 | **Section 4-05** | GenAI 에이전트 개발 (KA + Genie + Supervisor) | 2시간 |
| 17:10~17:30 | | Q&A 및 마무리 | 20분 |

---

## 워크샵 구성

### Section 1: Databricks Vibe Coding 리소스 소개

| 주제 | 내용 |
|------|------|
| [Genie Code 완전 가이드](section-1-vibe-coding-intro/genie-code/) | 프롬프트 잘 쓰는 법, 꿀팁 20가지, 템플릿 |

### Section 2: AI Dev Kit MCP 서버 배포

[AI Builder App 배포 핸즈온](section-2-ai-builder-app/) — git clone부터 앱 배포, 서비스 프린시펄 권한까지

### Section 3: Genie Code에 AI Dev Kit 구성하기

[AI Dev Kit 구성 가이드](section-3-genie-code-aidevkit/) — MCP 서버 연결 → 20개 도구 제한 내 선택 → Skills 배포

### Section 4: LG Smart TV E2E 핸즈온

| 모듈 | 내용 |
|------|------|
| [01. 환경 설정](section-4-smart-tv-handson/01-setup.md) | 카탈로그/스키마 생성, Custom Instructions 설정 |
| [02. 가상 데이터 생성](section-4-smart-tv-handson/02-data-generation.md) | webOS TV 로그 기반 17테이블 250만건 |
| [03. SDP 파이프라인](section-4-smart-tv-handson/03-sdp-pipeline.md) | 데이터 품질, Medallion Architecture, 증분 처리, Expectations |
| [04. 대시보드 & Genie Space](section-4-smart-tv-handson/04-dashboard-genie.md) | 대시보드 3개, Genie Space 3개, 정확도 고도화 |
| [05. 에이전트 개발](section-4-smart-tv-handson/05-agent-development.md) | KA + Genie Agent + Supervisor Agent + Lakebase(선택) |

---

## 사전 요구사항

| 항목 | 요구사항 |
|------|---------|
| Databricks Workspace | Premium 이상, Unity Catalog 활성화 |
| 컴퓨트 | 서버리스 컴퓨트 접근 권한 |
| Genie Code | Agent Mode 활성화 |
| 리전 | 서울리전 기본, US리전 사용 가능 (Lakebase 등) |

---

## 다루는 Databricks 핵심 기능

| # | 기능 | 공식 문서 |
|---|------|----------|
| 1 | **Unity Catalog** | [docs.databricks.com/unity-catalog](https://docs.databricks.com/en/data-governance/unity-catalog/index.html) |
| 2 | **Delta Lake** | [docs.databricks.com/delta](https://docs.databricks.com/en/delta/index.html) |
| 3 | **SDP (Lakeflow Declarative Pipelines)** | [docs.databricks.com/delta-live-tables](https://docs.databricks.com/en/delta-live-tables/index.html) |
| 4 | **AI/BI Dashboard** | [docs.databricks.com/dashboards](https://docs.databricks.com/en/dashboards/index.html) |
| 5 | **AI/BI Genie** | [docs.databricks.com/genie](https://docs.databricks.com/en/genie/index.html) |
| 6 | **Vector Search** | [docs.databricks.com/vector-search](https://docs.databricks.com/en/generative-ai/vector-search.html) |
| 7 | **Agent Bricks** | [docs.databricks.com/agent-bricks](https://docs.databricks.com/en/generative-ai/agent-bricks/index.html) |
| 8 | **Model Serving** | [docs.databricks.com/model-serving](https://docs.databricks.com/en/machine-learning/model-serving/index.html) |
| 9 | **Databricks Apps** | [docs.databricks.com/apps](https://docs.databricks.com/en/dev-tools/databricks-apps/index.html) |
| 10 | **Lakebase** (선택) | [docs.databricks.com/database](https://docs.databricks.com/en/database/index.html) |
| 11 | **Genie Code** | [docs.databricks.com/genie-code](https://docs.databricks.com/en/genie-code/index.html) |
| 12 | **AI Dev Kit** | [github.com/databricks-solutions/ai-dev-kit](https://github.com/databricks-solutions/ai-dev-kit) |

---

## 참고 리소스

| 주제 | URL |
|------|-----|
| Genie Code + AI Dev Kit 구성 가이드 | [github.com/SimyungYang/genie-code-ai-dev-kit](https://github.com/SimyungYang/genie-code-ai-dev-kit) |
| 이 워크샵 GitHub | [github.com/SimyungYang/genie-code-workshop-smarttv](https://github.com/SimyungYang/genie-code-workshop-smarttv) |
| AI Dev Kit GitHub | [github.com/databricks-solutions/ai-dev-kit](https://github.com/databricks-solutions/ai-dev-kit) |
| Genie Code 공식 문서 | [docs.databricks.com/genie-code](https://docs.databricks.com/en/genie-code/index.html) |
| Genie Code 프롬프트 팁 | [docs.databricks.com/genie-code/tips](https://docs.databricks.com/en/genie-code/tips.html) |
| Genie Code Custom Instructions | [docs.databricks.com/genie-code/instructions](https://docs.databricks.com/en/genie-code/instructions.html) |
| Genie Code Skills | [docs.databricks.com/genie-code/skills](https://docs.databricks.com/en/genie-code/skills.html) |
| Genie Code MCP 연결 | [docs.databricks.com/genie-code/mcp](https://docs.databricks.com/en/genie-code/mcp.html) |
