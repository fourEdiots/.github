# All is Well - 임베딩 결합 적응형 자연어 패널 추출 시스템
## LangGraph + RAG + BGE Reranker 기반 차세대 지능형 검색 플랫폼

## 📋 목차

- [프로젝트 소개](#-프로젝트-소개)
- [프리뷰](#-프리뷰)
- [팀원 및 역할](#-팀원-및-역할)
- [주요 화면](#-주요-화면)
- [시스템 아키텍처](#-시스템-아키텍처)
- [주요 기능](#-주요-기능)
  - [지능형 3-Tier 검색](#1--지능형-3-tier-검색)
  - [AI 페르소나 생성](#2--ai-페르소나-생성)
  - [통계 시각화](#3--인터랙티브-통계-시각화)
- [기술 스택](#-기술-스택)
- [프로젝트 구조](#-프로젝트-구조)
- [빠른 시작](#-빠른-시작)
- [성능 및 비용](#-성능-및-비용)
- [기대 효과](#-기대-효과)
- [라이선스](#-라이선스)

## 📌 프로젝트 소개
All is Well은 방대한 패널 데이터베이스에서 사용자의 자연어 질의를 지능적으로 처리하여 최적의 패널을 추출하는 차세대 검색 시스템입니다.
"캠핑을 좋아하는 30대 서울 거주 여성"과 같은 자연어 질의만으로 36,113명의 패널과 636,248건의 설문 응답 데이터를 검색하고, AI가 생성한 페르소나 및 통계 시각화를 통해 즉각적인 인사이트를 제공합니다.

### 🎯 핵심 가치기존 시스템의 한계:

- 키워드 기반 검색으로 추상적 질의 처리 불가
- 효율성과 정확성의 트레이드오프 문제
- 검색 결과의 제한적 활용 (단순 목록만 제공)
- 비연속적 검색 경험 (매번 새로 검색)
- 새 데이터 추가 시 긴 전처리 시간

### All is Well의 혁신:

- 적응형 하이브리드 검색: 질의 난이도 자동 분류 (SQL/임베딩 동적 선택)
- 지능형 그룹 분석: LLM 기반 페르소나 생성 및 AI 이미지 시각화
- 대화형 연속 검색: LangGraph 세션 관리로 드릴다운 지원
- 실시간 통계 시각화: Chart.js 인터랙티브 차트
- BGE 기반 리랭킹: 전처리 없이 질문-응답 의미 유사성 계산

## 🔍프리뷰
<img width="1587" height="2245" alt="프리뷰" src="https://github.com/user-attachments/assets/d872b47f-78db-407c-9c80-878bc7d67007" />

## 👥 팀원 및 역할

| 프로필 | 이름 | 역할 | 담당 업무 | GitHub |
|:------:|------|------|-----------|:------:|
| <img src="https://github.com/SeoukwooLee.png" width="80" height="80"> | **이석우** | Leader/AI-Data Engineer | 패널 검색 파이프라인 구축<br/>LLM 프롬프트 엔지니어링 | [![GitHub](https://img.shields.io/badge/-@SeoukwooLee-181717?style=flat-square&logo=github)](https://github.com/SeoukwooLee) |
| <img src="https://github.com/Dawon-Y.png" width="80" height="80"> | **양다원** | Full-stack Developer | UI 디자인 & 프론트엔드 개발<br/>백엔드(로그인/검색) API 개발 및 연동 | [![GitHub](https://img.shields.io/badge/-@Dawon--Y-181717?style=flat-square&logo=github)](https://github.com/Dawon-Y) |
| <img src="https://github.com/WinterFlw.png" width="80" height="80"> | **정수현** | AI-Data Engineer | AI 아키텍쳐 설계<br/>데이터 임베딩 | [![GitHub](https://img.shields.io/badge/-@WinterFlw-181717?style=flat-square&logo=github)](https://github.com/WinterFlw) |
| <img src="https://github.com/12hsh12.png" width="80" height="80"> | **홍성환** | Full-stack Developer | UI 디자인 & 프론트엔드 개발<br/>백엔드(라이브러리/히스토리/패널 상세) API 개발 및 연동 | [![GitHub](https://img.shields.io/badge/-@12hsh12-181717?style=flat-square&logo=github)](https://github.com/12hsh12) |


## 🎥 주요 화면
1. 메인 검색 화면
- 로그인 후 자연어로 패널 검색
  <img width="661" height="297" alt="image" src="https://github.com/user-attachments/assets/05368a55-1cb2-4037-94bd-9519cb952984" />


2. 검색 결과 화면

- 그룹 페르소나: LLM 생성 텍스트 + AI 이미지 + 해시태그
- 통계 차트: 연령대/성별/지역/직업 분포 시각화
- 개별 패널: 유사도 점수 + 매칭된 질문 응답
  <img width="658" height="292" alt="image" src="https://github.com/user-attachments/assets/78b26064-285c-416f-877a-f75746bf1d4a" />


3. 패널 상세 페이지
- 개별 패널의 고유 페르소나, 기본 프로필, 태그 정보
  <img width="662" height="302" alt="image" src="https://github.com/user-attachments/assets/efa4ed63-4ec5-4cf5-a118-bcd562171d18" />


4. 검색 히스토리 & 라이브러리
- 검색 기록 조회 및 재실행
- 자주 사용하는 검색 저장 관리
  <img width="645" height="292" alt="image" src="https://github.com/user-attachments/assets/86c8ac4d-def4-4020-a23f-e0a81ac49857" />


## 🏗 시스템 아키텍처

``` bash
┌─────────────┐      ┌──────────────┐      ┌─────────────────┐      ┌──────────┐
│             │      │              │      │                 │      │          │
│  Frontend   │────▶│  API Server  │────▶│ Data Pipeline   │────▶│  SQLite  │
│  (React)    │◀────│  (FastAPI)   │◀────│  (FastAPI)      │◀────│   DB     │
│             │      │              │      │                 │      │          │
│  Port 5173  │      │  Port 5001   │      │  Port 8000      │      │ ChromaDB │
└─────────────┘      └──────────────┘      └─────────────────┘      └──────────┘
                            │                      │                       │
                            │                      │                       │
                            ├──────────────────────┴───────────────────────┘
                            │         Cache & Session Management
                            │
                     ┌──────┴───────┐
                     │ BGE Reranker │
                     │   (Local)    │
                     └──────────────┘
```

### 계층별 역할
#### Frontend (React + Vite)

- 사용자 인터페이스
- 검색, 히스토리, 라이브러리 관리
- Chart.js 통계 시각화
- TanStack Query 서버 상태 관리

#### API Server (FastAPI)

- 사용자 인증 (JWT)
- 검색 결과 캐시 관리
- 히스토리 & 라이브러리 CRUD
- CSV 다운로드 제공
- 프록시 패턴으로 보안 강화

#### Data Pipeline (FastAPI + LangGraph)

- LangGraph 3-Tier 검색 워크플로우
- LLM 기반 쿼리 분석 & 결과 요약
- ChromaDB 벡터 검색
- BGE Reranker 재순위화
- 페르소나 & 이미지 생성

#### Database (SQLite + ChromaDB)

- SQLite: 구조화 데이터 (36,113명 패널, 636,248건 응답)
- ChromaDB: 벡터 검색 (질문 44개 + 답변 ~202K개)

## ✨ 주요 기능
### 1. 🔍 지능형 3-Tier 검색
``` bash
사용자 쿼리: "서울 20대 여성 중 ChatGPT 사용하는 사람"
                              ↓
┌─────────────────────────────────────────────────────────────┐
│  Step 1: LLM 쿼리 분석 (gpt-4o-mini)                        │
│  {                                                           │
│    demographics: {region: "서울", age: [20-29], gender: "여성"}│
│    structured_keywords: []                                  │
│    semantic_queries: ["ChatGPT 사용"]                       │
│  }                                                          │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│  Step 2: Tier 1 - Demographics SQL (인구통계 필터)          │
│  WHERE region='서울' AND gender='여성' AND age BETWEEN 20-29│
│  → 1,234명 후보 추출                                        │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│  Step 3: Tier 2 - Structured SQL (구조화 키워드)            │
│  SKIP (해당 없음)                                           │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│  Step 4: Tier 3 - Semantic Vector Search + BGE Reranker     │
│  [1] Question-First: 44개 질문 검색 → AI 관련 5개 질문 선정  │
│  [2] Answer Search: 1,234명 후보 중 5개 질문 답변만 검색     │
│  [3] BGE Reranker: Cross-encoder로 재순위화                 │
│  → Top 100명 선정 (match_score: 0.85~0.95)                  │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│  Step 5: LLM 결과 요약 & 페르소나 생성                       │
│  "서울 거주 20대 여성 100명 (ChatGPT 사용자)"                │
└─────────────────────────────────────────────────────────────┘
```

### 성능:

- Tier 1-2만 사용: ~100ms ⚡
- Full Pipeline (GPU): ~17초
- Full Pipeline (CPU): ~2.5분

### 2. 🎭 AI 페르소나 생성
그룹 페르소나 (LLM 생성)
``` json
{
  "text": "30대 초반의 액티브한 아웃도어 애호가로, 주말마다 등산이나 캠핑을 즐기며...",
  "hashtags": ["#아웃도어", "#30대", "#액티브", "#캠핑"],
  "image_url": "data:image/png;base64,iVBORw0KG..."
}
```

- 텍스트: GPT-4o-mini가 그룹 특성 요약
- 해시태그: 핵심 키워드 추출
- 이미지: Nano Banana 모델로 시각화

- 개별 페르소나 (36,113개 사전 생성)

- 각 패널의 성향, 관심사, 라이프스타일 요약
- 검색 시 유사도 점수와 함께 제공

### 3. 📊 인터랙티브 통계 시각화
- Chart.js 기반 차트

- 연령대별 분포 (막대 그래프)
- 성별 분포 (원형 차트)
- 지역별 분포 (막대 그래프)
- 직업별 분포 (가로 막대)
- 소득별 분포 (선 그래프)

클릭 한 번으로 차트 전환
``` bash
// 사용자가 "연령대" 클릭 → BarChart 렌더링
<BarChart 
  data={{
    labels: ["20대", "30대", "40대"],
    values: [50, 300, 100]
  }}
  title="연령대별 분포"
/>
```

### 4. 🔄 대화형 드릴다운 검색

연속 질문 시나리오:
``` bash
1차 검색: "캠핑 좋아하는 사람" → 450명
   ↓ session_id 유지
2차 검색: "이 중에서 서울 거주자" → 120명
   ↓ session_id 유지  
3차 검색: "이 중에서 30대만" → 80명
```

LangGraph 상태 관리:

- 이전 결과 집합 내에서만 추가 필터링
- 전체 재검색 불필요 → 효율성 극대화

### 5. 📥 데이터 활용 기능
CSV 다운로드
``` bash
패널ID,나이,성별,지역,구역,직업,요약,유사도
PANEL_001,32,남성,서울,강남구,IT 개발자,주말마다 캠핑을...,0.95
```

- UTF-8 BOM으로 한글 깨짐 방지
- 타임스탬프 파일명: `panel_results_20241128_143022.csv`

**검색 히스토리**
- 최근 검색 자동 저장
- 클릭으로 이전 결과 즉시 복원

**라이브러리**
- 자주 사용하는 검색 저장
- 사용자 지정 제목 관리

## 🛠 기술 스택

### Frontend
```
React 18.x              UI 라이브러리
TypeScript              타입 안전성
Vite                    빌드 도구 (빠른 HMR)
TanStack Query          서버 상태 관리 & 캐싱
Zustand                 클라이언트 전역 상태
React Router v6         라우팅
Axios                   HTTP 클라이언트
Tailwind CSS            유틸리티 기반 스타일링
Chart.js                데이터 시각화
Lucide React            아이콘
```

### Backend (API Server)
```
FastAPI 0.115+          비동기 REST API 프레임워크
Python 3.10+            프로그래밍 언어
Uvicorn                 ASGI 서버
SQLite 3                로컬 데이터베이스
Pydantic 2.x            데이터 검증 & 직렬화
httpx                   비동기 HTTP 클라이언트
python-jose             JWT 토큰
```

### Data Pipeline
```
FastAPI 0.115+          비동기 API 서버
Python 3.13             BGE Reranker 의존성
LangGraph               StateGraph 워크플로우
LangChain               LLM Chains
OpenAI gpt-4o-mini      쿼리 분석 & 결과 요약
ChromaDB                벡터 데이터베이스
OpenAI text-embedding   임베딩 (1536-dim)
BGE Reranker v2-m3      재순위화 (로컬, 무료)
sentence-transformers   BGE 모델 로더
```

### Database
```
SQLite                  구조화 데이터 (111MB)
  - 36,113명 패널 정보
  - 636,248건 설문 응답
  - 검색 캐시 & 히스토리

ChromaDB                벡터 검색 (~1.5GB)
  - 44개 질문 임베딩
  - ~202K개 답변 임베딩
```

## 📁 프로젝트 구조
```
AllIsWell/
├── Frontend/                           # React 프론트엔드
│   ├── src/
│   │   ├── api/                        # API 통신 레이어
│   │   │   ├── auth.js
│   │   │   ├── search.js
│   │   │   ├── history.js
│   │   │   └── library.js
│   │   ├── components/                 # 재사용 컴포넌트
│   │   │   ├── common/
│   │   │   ├── SearchResult/
│   │   │   ├── panelDetail/
│   │   │   └── ...
│   │   ├── pages/                      # 페이지
│   │   │   ├── Login/
│   │   │   ├── Main/
│   │   │   ├── SearchResult/
│   │   │   └── History/
│   │   ├── hooks/                      # 커스텀 훅
│   │   └── utils/                      # 유틸리티
│   ├── package.json
│   └── vite.config.js
│
├── Backend/                            # FastAPI API 서버
│   ├── src/
│   │   └── app/
│   │       ├── db/                     # 데이터베이스
│   │       ├── routers/                # API 라우터
│   │       │   ├── auth.py
│   │       │   ├── search.py
│   │       │   ├── history_api.py
│   │       │   └── library_api.py
│   │       └── schemas/                # Pydantic 스키마
│   ├── databases/
│   │   └── main.db
│   ├── main.py
│   └── requirements.txt
│
└── DataPipeline/                       # FastAPI + LangGraph
    ├── src/
    │   ├── pipeline_v4/                # 메인 파이프라인
    │   │   ├── pipeline.py
    │   │   ├── graph.py                # LangGraph StateGraph
    │   │   ├── nodes.py                # 6개 노드
    │   │   ├── chains.py               # LLM Chains
    │   │   ├── retrievers.py           # 3-Tier 검색
    │   │   └── config.py
    │   ├── api/
    │   │   └── question_first_search.py
    │   ├── database/
    │   ├── embeddings/
    │   │   ├── embedding_service.py
    │   │   ├── vector_db.py
    │   │   └── reranker.py             # BGE Reranker
    │   └── extractors/
    ├── databases/
    │   ├── PersonaSurveyData.db        # SQLite (111MB)
    │   ├── chroma_db_questions/        # 질문 벡터
    │   └── chroma_db_answers/          # 답변 벡터
    ├── scripts/                        # DB 생성 스크립트
    └── requirements.txt
```


## 🚀 빠른 시작
사전 요구사항

Node.js 18.x 이상
Python 3.10 이상 (파이프라인은 3.13 권장)
OpenAI API Key

1️⃣ Frontend 설정 및 실행
```
cd Frontend

# 의존성 설치
npm install

# 환경 변수 설정
echo "VITE_API_URL=http://localhost:5001" > .env

# 개발 서버 실행
npm run dev
# → http://localhost:5173
```

2️⃣ Backend (API Server) 설정 및 실행
```
cd Backend

# 가상환경 생성 및 활성화
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# 의존성 설치
pip install -r requirements.txt

# 데이터베이스 초기화
python create_db_tables.py

# 서버 실행
python main.py
# → http://localhost:5001
# Swagger UI: http://localhost:5001/docs
```

3️⃣ Data Pipeline 설정 및 실행
```
cd DataPipeline

# Python 3.13 가상환경 (BGE Reranker 필요)
python3.13 -m venv .venv313
source .venv313/bin/activate

# 의존성 설치
pip install -r requirements.txt

# OpenAI API 키 설정
export OPENAI_API_KEY='your-api-key'

# 데이터 전처리 (일회성)
cd scripts/
python preprocess_only.py
python create_question_embeddings.py
python create_answer_embeddings.py
cd ..

# 파이프라인 서버 실행
python run_pipeline.py
# → http://localhost:8000
```

4️⃣ 전체 시스템 실행 순서
```
# Terminal 1: Data Pipeline
cd DataPipeline
source .venv313/bin/activate
python run_pipeline.py

# Terminal 2: API Server
cd Backend
source venv/bin/activate
python main.py

# Terminal 3: Frontend
cd Frontend
npm run dev
```

접속: http://localhost:5173

## 📊 성능 및 비용
데이터 규모

- 패널: 36,113명
- 질문: 62개 (44개 비구조화만 임베딩)
- 응답: 636,248건 (~202K개만 임베딩)
- 페르소나: 36,113개 (GPT-4o-mini 생성)
- 데이터베이스: 111MB (SQLite) + ~1.5GB (ChromaDB)

검색 성능
### 검색 성능

| 검색 유형 | 사용 Tier | 처리 시간 | 설명 |
|----------|----------|----------|------|
| 인구통계 검색 | Tier 1 | ~50ms ⚡ | SQL WHERE (성별, 나이, 지역) |
| 구조화 키워드 | Tier 1+2 | ~100ms ⚡ | SQL + LIKE (직업, 학력, 소득) |
| 의미론적 검색 (GPU) | Full Pipeline | ~17초 | 벡터 검색 + BGE Reranker |
| 의미론적 검색 (CPU) | Full Pipeline | ~2.5분 | 벡터 검색 + BGE Reranker |

**참고:** 대부분의 쿼리는 Tier 1-2만 사용하여 1초 이내 응답

비용 (OpenAI API)
초기 설정 (일회성)

질문 임베딩 (44개): ~$0.0001
답변 임베딩 (~202K개): ~$0.003
총: ~$0.003 (1원 미만!)

검색 비용 (쿼리당)

LLM 쿼리 분석: ~$0.0005
쿼리 임베딩: ~$0.00002
LLM 결과 요약: ~$0.0005
BGE Reranker: $0 (로컬 모델)
총: ~$0.001/검색

월간 사용 예상

1,000회 검색/월: ~$1
10,000회 검색/월: ~$10

## 💼 기대 효과
### 경제적 측면
#### 1. 생산성 향상 & 비용 절감

- 복잡한 SQL 작성 불필요 → 데이터 분석 인력 시간 절감
- 신속한 인사이트 도출 → 시장 대응 속도 향상
- 반복 작업 자동화 → IT 자원 소모 최소화

#### 2. 비즈니스 성과 & 매출 증대

- 타겟 마케팅 정확도 향상 → 마케팅 ROI 극대화
- 개인화된 금융/의료 서비스 → 고객 만족도 & 객단가 상승
- 고품질 의사결정 지원 → 사업 성공률 향상

### 사회적 측면
#### 1. 연구 & 기술 혁신 가속화

- 연구 생산성 제고 (논문, 특허, 임상 대상자 모집)
- 범용 플랫폼 확장 (마케팅, 금융, 의료, 공공)

#### 2. 공공 서비스 품질 개선

- 정확한 정책 수립 지원
- 시스템 신뢰도 & 사용자 만족도 향상

#### 3. 데이터 리터러시 장벽 완화

- SQL 지식 없이 자연어로 데이터 탐색
- 조직 전반의 데이터 기반 문화 확산


## 📄 라이선스
이 프로젝트는 MIT 라이선스를 따릅니다.
