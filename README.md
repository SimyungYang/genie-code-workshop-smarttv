# LGE MS사업본부 Vibe Coding 워크샵

> **교육 일시**: 2026년 4월 22일 | **대상**: LG전자 MS(Media Solution)사업본부

Databricks 환경에서 **Genie Code**와 **AI Dev Kit**을 활용한 Vibe Coding 실습 워크샵입니다.

LG Smart TV webOS 텔레메트리 데이터를 기반으로, 자연어 프롬프트만으로 데이터 파이프라인부터 AI 에이전트까지 End-to-End로 구축합니다.

---

## 워크샵 구성

### Section 1: Databricks Vibe Coding 리소스 소개

| 주제 | 내용 |
|------|------|
| [Genie Code 완전 가이드](section-1-vibe-coding-intro/genie-code/) | 프롬프트 잘 쓰는 법, 꿀팁 20가지, 템플릿 |
| AI Dev Kit | Claude Code/Cursor 연동 MCP 서버 + Skills |
| AI Builder App | Databricks Apps 플랫폼 기반 웹 앱 배포 |

### Section 2: AI Builder App 배포 핸즈온

Lakebase 미사용 시 제약사항, git clone부터 배포까지 상세 가이드

### Section 3: Genie Code에 AI Dev Kit 구성하기

MCP 서버 배포 → Genie Code 연결 → 15개 도구 선택 → Skills 배포

### Section 4: LG Smart TV E2E 핸즈온

| 모듈 | 내용 |
|------|------|
| [02. 가상 데이터 생성](section-4-smart-tv-handson/02-data-generation.md) | webOS TV 로그 기반 17테이블 250만건 |
| [03. SDP 파이프라인](section-4-smart-tv-handson/03-sdp-pipeline.md) | 데이터 품질, Medallion Architecture, Expectations |
| [04. 대시보드 & Genie Space](section-4-smart-tv-handson/04-dashboard-genie.md) | 대시보드 3개, Genie Space 3개, 정확도 고도화 |
| [05. 에이전트 개발](section-4-smart-tv-handson/05-agent-development.md) | KA + Genie Agent + Supervisor Agent |

---

## 사전 요구사항

| 항목 | 요구사항 |
|------|---------|
| Databricks Workspace | Premium 이상, Unity Catalog 활성화 |
| 컴퓨트 | 서버리스 컴퓨트 접근 권한 |
| Genie Code | Agent Mode 활성화 |

---

## 참고 리소스

- [Genie Code + AI Dev Kit 구성 가이드](https://github.com/SimyungYang/genie-code-ai-dev-kit)
- [AI Dev Kit GitHub](https://github.com/databricks-solutions/ai-dev-kit)
- [Databricks Genie Code 공식 문서](https://docs.databricks.com/aws/en/genie-code/)
