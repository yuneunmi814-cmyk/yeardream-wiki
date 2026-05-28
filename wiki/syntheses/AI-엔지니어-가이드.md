---
type: synthesis
stage: 1
created: 2026-05-29
last_updated: 2026-05-29
status: 가설 (트랙 분기 6월 중 확정 시 갱신)
trigger: "은미 본인 의지 표명 (2026-05-29)"
---

# AI 엔지니어 가이드 (은미 맞춤)

> ⚠️ 트랙 분기 6월 중. 최종 결정 전 변동 가능. 현 시점 가설 가이드. 강의 진행하며 갱신.

---

## 결론 — 6 Phase

```
지금 ─────────────────── 11월 ─────── 12월 이후
Phase 1 → 2 → 3 → 4 → 5 → 6
  ↓     ↓    ↓    ↓    ↓    ↓
Stage1 후반 후반 Stage3 Stage4 졸업 후
```

---

## Phase 1 — 지금 (~6월 초): Stage 1 강의 따라잡기

**상태**: Day 3까지 들음, 압도된 상태에서 회복 중. 매일 정수 추출 패턴 정착.

**할 일**:
- ✅ Python 기초 (Day 4 시작)
- ✅ 강의 페이지 🚀 예습 섹션 → 점진적으로 본문까지
- ✅ 매일 1개 정수 추출 후 위키 누적
- [ ] Day 4 라이브 수업 후 [[Python]]·[[변수]]·[[자료형]]·[[리스트]]·[[조건문]] 본문 정독
- [ ] 손코딩: 강의 실습 ☑️ 직접 타이핑

---

## Phase 2 — Stage 1 후반 (6월): Python 손코딩 친숙화

**목표**: Python을 "읽을 줄 안다" → "짧은 코드는 직접 짠다"

**할 일**:
- Python 30분/일 손코딩 (강의 외 추가)
- **Jupyter Notebook 셋업** (맥북에)
  ```bash
  pip install jupyter
  jupyter notebook
  ```
- 작은 프로젝트 1개:
  - **Cloudflare Pages 분석 자동 수집** (네 웹앱 데이터로)
  - 또는 **인스타 게시물 메타 데이터 정리 스크립트**
- 학습 자료: Hugging Face 시작하기, Python 공식 튜토리얼

---

## Phase 3 — Stage 2 (6~7월): ML / DL 기초

**목표**: AI 모델이 어떻게 학습되는지 직접 만져봄

**할 일**:
- **머신러닝 기초**: scikit-learn으로 분류·회귀 모델
- **딥러닝 기초**: PyTorch로 간단한 신경망
- **LLM API 직접 호출**:
  ```python
  from anthropic import Anthropic
  client = Anthropic()
  response = client.messages.create(...)
  ```
- 너는 이미 Claude Code 일상 사용 → API 호출 진입 빠름

**병행**:
- **공룡책 1차** (Ch.1·3·9·13 가볍게) — Day 2 라이브 노트 약속
- Kaggle 미니 챌린지 첫 도전 (병행 프로그램)

---

## Phase 4 — Stage 3 (7~10월): AI 트랙 분기

**6월 중 트랙 확정 시점**:
- **AI 서비스개발자 트랙** ⭐ — AI 엔지니어 / AI Agent 엔지니어 (네 가설)
- AI 분석가 트랙 — 데이터 사이언티스트·NLP·CV 깊이

**AI 서비스개발자 트랙 가정 시 할 일**:
- **Python + FastAPI 백엔드 마스터**
- **LangChain·LlamaIndex 학습** (LLM 워크플로우 도구)
- **Docker 기초** (모델 컨테이너화)
- **벡터 DB 다루기** (ChromaDB·Pinecone — RAG 시 필수)
- **MLOps 기초** (모델 배포·모니터링)

---

## Phase 5 — Stage 4 (10~11월): 파이널 프로젝트

**목표**: 실제 AI 솔루션 1개 + 포트폴리오

**프로젝트 후보** (네 자산 활용):
- **프로젝트윤365 클라이언트 AI 솔루션 1개** ⭐ — 사업 자산화 직결
- 예시: 클라이언트 문서 자동 분류 / 고객 응답 자동화 / 인사이트 리포트 자동 생성

**기술 스택 (가설)**:
- 백엔드: **Python + FastAPI**
- DB: **Supabase** (PostgreSQL 기반) — 1인 운영 친화
- AI: **Claude API + LangChain**
- 배포: **Docker + Cloudflare** 또는 AWS
- 프론트: **SwiftUI** (이미 익숙) 또는 React+TypeScript

---

## Phase 6 — 졸업 후 (11월~): 진로

**포트폴리오 구성**:
- ✅ Stage 4 파이널 프로젝트 (실 클라이언트 솔루션)
- ✅ GitHub 코드 + 위키 (yeardream-wiki)
- ✅ yoon.ai.lab 콘텐츠 시리즈 (학습 과정 자체)
- ✅ prompt.by.yoon (Claude 활용 노하우)

**옵션**:
1. **인턴십 / 취업** — AI Agent 엔지니어 직무
2. **프로젝트윤365 본격 확장** — 6기 수강 자산 활용
3. **해외 진출 기반** — 실리콘밸리 (장기)

**커뮤니티 (병행)**:
- Pseudo·KDDxAI (한국 AI 커뮤니티)
- LangChain·LlamaIndex 공식 디스코드
- Hugging Face 한국 그룹

---

## 핵심 학습 도구 정리

### 언어
- **Python** ⭐⭐ — Stage 1~4 매일
- **TypeScript** — 프론트엔드 통합 시
- (Go·Rust 등은 Phase 4·5 후 필요시)

### 프레임워크
- **PyTorch** — AI 모델 (Phase 3~)
- **FastAPI** — 백엔드 API (Phase 4~)
- **LangChain** ⭐ — LLM 워크플로우 (Phase 4~)
- **LlamaIndex** — RAG·검색 (Phase 4~)

### 인프라
- **Docker** — 컨테이너 (Phase 4~)
- **Supabase** — BaaS (Phase 5~) ⭐
- **AWS / GCP** — 클라우드 (Phase 5~)
- **Cloudflare** — CDN·Pages (이미 닿음)

### API
- **Claude API** — Anthropic (이미 닿음)
- **OpenAI API** — GPT
- **Gemini API** — Google

---

## 위키 활용

- **모든 강의 페이지의 🙋 정수 섹션**에 매일 1개씩 누적 — 6개월 후 본인 학습 그래프
- **[[Python]]·[[데이터베이스-기초]]·[[앱-웹-서비스]]** 가 핵심 누적 페이지
- **공룡책** ([[공룡책-OS-Concepts-10판]]) 1·2차 학기 중 완독

---

## 콘텐츠 자산화 (yoon.ai.lab)

병행 가능한 시리즈:
- **"비전공자가 AI 엔지니어 되는 6개월 일지"** — 학습 과정 자체가 콘텐츠
- **"매일 정수 1개"** — 위키 정수 추출 그대로 인스타 캐러셀
- **"AI Agent 코드 5분"** — Claude API 짧은 활용 팁

---

## 변동 가능성

- **트랙 확정 시 (6월 중)**: AI 분석가 트랙이면 가이드 큰 폭 변경
- **인턴십 참여 여부**: 6기 인턴십 옵션이라 변동 가능
- **6개월 후 시장 변화**: AI 직무·도구 변동 가능 (지금은 LangChain 표준이지만 6개월 후 다를 수도)

→ 가이드는 **현 시점 합리적 추론**. 강의 진행하며 매월 갱신.

---

## 관련 페이지

- [[Python]] — 주력 언어
- [[앱-웹-서비스]] — AI 서비스 만들 무대
- [[데이터베이스-기초]] — Supabase·PostgreSQL
- [[공룡책-OS-Concepts-10판]] — 학기 학습 동선
- [[학습-워크플로우]] — 매일 패턴
- [[프로그램-개요]] — 6기 인센티브·트랙 분기
- [[커리큘럼]] — 단계별 진도

---

## 출처

- 사용자 본인 의지 표명 (2026-05-29)
- 강의 Day 1~4 진행 중 정수 추출 누적
- [[프로그램-개요]] — 6기 트랙 분기 구조
