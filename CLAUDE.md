# LGE MS사업본부 Vibe Coding 교육 가이드

## 프로젝트 개요

- **교육 일시**: 2026년 4월 22일
- **대상**: LG전자 MS(Media Solution)사업본부 인원
- **주제**: Databricks 환경에서의 Vibe Coding 실습
- **시나리오**: LG Smart TV 데이터 기반 End-to-End 데이터/AI 파이프라인 구축
- **배포 형태**: GitHub 개인 프로필 Push → GitBook 연동으로 교육 가이드 제공

## 교육 구성 (4개 섹션)

### Section 1: Databricks Vibe Coding 리소스 소개
Databricks 환경에서 사용 가능한 3가지 AI 코딩 리소스를 소개한다.

| 리소스 | 설명 | 특징 |
|--------|------|------|
| **Genie Code** | Databricks 내장 AI 코딩 어시스턴트 | 노트북/대시보드/파이프라인 에디터에서 `Cmd+I`로 호출, Agent Mode 지원 |
| **AI Dev Kit** | Claude Code/Cursor 연동 MCP 서버 + Skills | 44개 MCP 도구, 25개 Skills, 크로스 프로덕트 오케스트레이션 |
| **AI Builder App** | Databricks Apps 플랫폼 기반 웹 앱 배포 | FastAPI/React/Streamlit 등 지원, OAuth 인증, Lakebase 연동 |

### Section 2: AI Builder App 배포 핸즈온
Lakebase 미사용 시 제약사항 설명 및 git clone부터 상세 배포 과정 핸즈온.

- Lakebase 미사용 시 제약사항 (OLTP 기능 제한, 세션 관리 등)
- git clone → app.yaml 구성 → requirements.txt → 배포 → 테스트
- Databricks CLI를 통한 앱 생성/배포/관리 전 과정

### Section 3: Genie Code에 AI Dev Kit 구성하기
- **참조**: https://github.com/SimyungYang/genie-code-ai-dev-kit
- AI Dev Kit MCP 서버를 Databricks App으로 배포
- Genie Code Settings에서 MCP 서버 연결
- 15개 도구 제한 내 권장 프로필 선택
- Skills를 `/Workspace/.assistant/skills/`에 배포
- 크로스 프로덕트 오케스트레이션 테스트 (Genie Space 생성 + 대시보드 + Job 스케줄링)

### Section 4: LG Smart TV 시나리오 End-to-End 핸즈온
- **참조**: https://simyungyang.gitbook.io/databricks-enablement-resources/hands-on-workshop/smart-tv-vibe
- 가상 데이터 생성 (170만건+) → 데이터 파이프라인 → 분석 → ML → GenAI 에이전트

#### 워크로드 시나리오: LG Smart TV 데이터 플랫폼

**데이터셋 (가상 데이터)**:

| 테이블 | 건수 | 설명 |
|--------|------|------|
| `bronze.devices` | 10,000 | TV 디바이스 마스터 (모델명, 지역, 패널 타입, OS 버전 등) |
| `bronze.viewing_logs` | 500,000 | 채널/앱 시청 기록 (시청 시간, 장르, 해상도 등) |
| `bronze.click_events` | 1,000,000 | 리모컨/UI 조작 이벤트 (메뉴 탐색, 앱 전환, 설정 변경 등) |
| `bronze.ad_impressions` | 200,000 | 광고 노출/클릭/전환 데이터 |

**End-to-End 파이프라인 구성**:

| 순서 | 모듈 | 핵심 기능 | 소요시간 |
|------|------|---------|---------|
| 1 | 환경 설정 (UC Catalog/Schema/Volume) | Unity Catalog | ~1분 |
| 2 | 가상 데이터 생성 (170만건) | PySpark, Delta Lake | ~10분 |
| 3 | Bronze→Silver→Gold 수동 변환 | CTAS, SQL, Medallion Architecture | ~30분 |
| 4 | SDP 파이프라인 자동화 | Lakeflow Declarative Pipelines, Expectations | ~30분 |
| 5 | AI/BI 대시보드 & Genie Space | Dashboard, Genie Space | ~1시간 |
| 6 | 실시간 이벤트 생성기 배포 | Databricks Apps, FastAPI | ~30분 |
| 7 | Structured Streaming | Auto Loader, Structured Streaming | ~1시간 |
| 8 | ML 추천 모델 & MLOps | Feature Store, LightGBM, MLflow, Model Serving | ~1.5시간 |
| 9 | 이미지 이상 탐지 | CNN, SHAP, 비정형 데이터 처리 | ~1시간 |
| 10 | GenAI 에이전트 & OLTP | Agent Bricks, Lakebase | ~2시간 |

**12가지 Databricks 핵심 기능 커버리지**:
Unity Catalog, Delta Lake, SDP (Lakeflow), Auto Loader, Structured Streaming, AI/BI Dashboard, AI/BI Genie, MLflow, Model Serving, Vector Search, Agent Bricks, Apps + Lakebase

**3가지 학습 트랙**:

| 트랙 | 방식 | 추천 대상 |
|------|------|---------|
| **Track A** | 노트북 직접 실행 | 코드를 한 줄씩 이해하고 싶은 분 |
| **Track B** | Claude Code + AI Dev Kit | AI 코딩 도구 생산성 체험 |
| **Track C** | Genie Code (Databricks 내장) | 별도 설치 없이 AI 코딩 체험 |

## 시나리오 상세: LG Smart TV 비즈니스 컨텍스트

### MS사업본부 관점의 핵심 유스케이스

1. **시청 행동 분석**: 채널/앱별 시청 패턴, 시간대별 사용량, 장르 선호도
2. **광고 효과 측정**: 광고 노출→클릭→전환 퍼널 분석, CPM/CTR 최적화
3. **콘텐츠 추천**: 시청 이력 기반 ML 추천 모델, A/B 테스트
4. **디바이스 이상 탐지**: 패널 불량, 네트워크 오류, 앱 크래시 등 조기 감지
5. **실시간 모니터링**: 라이브 방송 시청률, 실시간 광고 성과 트래킹
6. **고객 서비스 에이전트**: GenAI 기반 Smart TV 사용 가이드, 트러블슈팅 챗봇

### Gold 테이블 예시 (분석/서빙용)

- `gold.daily_viewing_summary`: 일별/모델별/지역별 시청 통계
- `gold.content_recommendation_features`: ML 추천 모델 피처 테이블
- `gold.ad_campaign_performance`: 광고 캠페인별 성과 집계
- `gold.device_health_metrics`: 디바이스 건강 지표 (이상 탐지용)
- `gold.user_engagement_360`: 사용자 참여도 360도 뷰

## 파일 구조 (예정)

```
├── CLAUDE.md                          # 이 파일
├── README.md                          # GitBook 메인 페이지
├── SUMMARY.md                         # GitBook 목차
├── section-1-vibe-coding-intro/       # Section 1: 리소스 소개
│   ├── genie-code.md
│   ├── ai-dev-kit.md
│   └── ai-builder-app.md
├── section-2-ai-builder-app/          # Section 2: App 배포 핸즈온
│   ├── prerequisites.md
│   ├── deploy-step-by-step.md
│   └── lakebase-constraints.md
├── section-3-genie-code-aidevkit/     # Section 3: Genie Code + AI Dev Kit
│   ├── architecture.md
│   ├── setup-guide.md
│   └── tool-profiles.md
├── section-4-smart-tv-handson/        # Section 4: E2E 핸즈온
│   ├── 01-setup.md
│   ├── 02-data-generation.md
│   ├── 03-medallion-pipeline.md
│   ├── 04-sdp-pipeline.md
│   ├── 05-dashboard-genie.md
│   ├── 06-event-generator.md
│   ├── 07-streaming.md
│   ├── 08-ml-recommendation.md
│   ├── 09-anomaly-detection.md
│   └── 10-agent-bricks.md
└── notebooks/                         # 실습 노트북
```

## 참고 리소스

| 주제 | URL |
|------|-----|
| Genie Code + AI Dev Kit 구성 가이드 | https://github.com/SimyungYang/genie-code-ai-dev-kit |
| Smart TV Vibe 워크샵 (기존) | https://simyungyang.gitbook.io/databricks-enablement-resources/hands-on-workshop/smart-tv-vibe |
| AI Dev Kit GitHub | https://github.com/databricks-solutions/ai-dev-kit |
| Databricks Agent Bricks 문서 | https://docs.databricks.com/generative-ai/agent-bricks |
| Lakebase 문서 | https://docs.databricks.com/database |
| SDP (Lakeflow) 문서 | https://docs.databricks.com/delta-live-tables |

## 작업 규칙

- 교육 가이드 문서는 **한국어**로 작성
- 코드 주석과 변수명은 **영어** 사용
- GitBook 호환 Markdown 형식 유지 (SUMMARY.md 기반 네비게이션)
- 각 섹션은 독립적으로 진행 가능하도록 구성
- 노트북은 Track A/B/C 모두 호환 가능하도록 작성
