---
type: external-resource
category: research-tool
title: "PRISMA-KB — LLM-Powered Academic Knowledge Base Builder"
authors: [dschloe (강사님 추정)]
github: "https://github.com/dschloe/PRISMA-KB"
source: raw/external/README 2.md
ingested: 2026-05-29
nickname: "강사님 연구 도구"
related: [[AI-엔지니어-가이드]], [[서비스-기획-워크플로우]]
---

# 📚 PRISMA-KB — 강사님 연구 도구

> 강사님(`dschloe` 추정)이 본인 박사 논문·SSCI 저널 논문 쓰려고 만든 **LLM 활용 체계적 문헌고찰(SR) 자동화 오픈소스 도구**.

> ⭐ **너 yeardream-wiki와 같은 철학** — 강사가 참고하라고 준 이유 = 너 학습 위키 방식이 본인 연구 방법론과 일치하기 때문.

---

## 한 줄 정의

**PRISMA-KB** = PDF 논문들을 LLM으로 자동 요약·분류·검색·인용해서 **체계적 문헌고찰(Systematic Review) 논문 작성 자동화**하는 Python 도구.

---

## 강사님 연구 컨텍스트 ⭐⭐

### Paper 1 (SSCI 저널·진행 중)

> **"Human Competencies Required for Effective Human–AI Collaboration: A Systematic Review"**
> (인간-AI 협업에 필요한 인간 역량 — 체계적 문헌고찰)

**5개 연구 질문 (RQ)**:

| RQ | 질문 |
|---|---|
| **RQ1** | 문헌에서 인간-AI 협업(HAC)은 어떻게 정의되나? |
| **RQ2** | 효과적인 HAC에 필요한 **인간 역량**은? |
| **RQ3** | HAC 효과성에 영향을 미치는 요인은? |
| **RQ4** | 어떤 산업·업무 맥락에서 HAC 연구가 진행됐나? |
| **RQ5** | 현재 연구 격차와 미래 방향은? |

### Paper 2 (PhD 논문·예정)

> **"AI Transition and Talent Development in Korea"**
> (AI 전환과 한국의 인재 개발)

### 핵심 메시지

> "사회가 인간 전문성 시대에서 AI 증강 시대로 이행 시,
> **어떤 역량이 필요하고 한국 기관은 얼마나 잘 대응하나?**"

→ **너 진로와 직결**: 비전공자 → AI 부트캠프 = 한국의 AI 전환 인재 개발 케이스 그 자체.

---

## 영감 — Andrej Karpathy ⭐⭐

**Karpathy** = OpenAI 공동창업자 + 전 테슬라 AI 디렉터 + 현 AI 분야 글로벌 거장.

→ 강사가 Karpathy의 **LLM 지식 베이스 워크플로우** X 포스트를 Python 도구로 재구현.

→ **너 작업 방식 = Karpathy 패턴**. 강사가 알려준 메타.

---

## ⭐ 너 yeardream-wiki와의 비교

| 차원 | PRISMA-KB (강사) | yeardream-wiki (너) |
|---|---|---|
| **목적** | SR 논문 자동화 | 비전공자 AI 학습 |
| **소스** | 학술 PDF | 강의 자료·Gemini 답 |
| **LLM** | Gemini·Claude·OpenAI·Ollama | Claude·Gemini |
| **출력** | RQ 답변·SR 초안 | 학습 정수 추출 |
| **형식** | 마크다운 | 마크다운 ✅ |
| **자동화** | cron + GitHub Actions | (수동, 추후 가능) |
| **철학** | "LLM이 위키를 도움 / Vault ≠ 코드" | 같음 ⭐ |

→ **5가지 설계 원칙이 너 워크플로우와 100% 일치**:
1. "LLM이 위키를 도움" — 너 = Claude로 정수 추출
2. CLI-first — 너 = Claude Code
3. **Vault ≠ 코드** — 너 = wiki/ vs raw/ 분리 ✅
4. **LLM-agnostic** — 너 = Claude + Gemini 조합 ([[AI-도구-조합]])
5. Iterative — 너 = 매일 누적

---

## Vault 구조 (참고)

```
vault/
├── 01_raw/           # PDF·초록
├── 02_screening/     # 선정 논문 CSV
├── 03_notes/         # 논문별 노트
├── 04_concepts/      # 개념 위키
├── 05_indexes/       # paper_index.json
├── 06_outputs/       # 리뷰 초안
└── README.md
```

→ **너 wiki/ 구조와 비슷**:
- 01_raw ↔ raw/
- 03_notes/papers ↔ wiki/lectures
- 04_concepts ↔ wiki/concepts
- 06_outputs ↔ wiki/syntheses

---

## 주요 기능

| 스크립트 | 역할 |
|---|---|
| **compile.py** | PDF → 구조화 노트 (Gemini로) |
| **compile_auto.py** | 대량 배치 + API 429 대기·재개 + 진행 상태 저장 + macOS caffeinate |
| **query.py** | RQ 답변 합성 |
| **export.py** | SR 초안 마크다운 생성 |
| **lint.py** | 분류체계·RQ 커버리지·일관성 검사 |

→ **너 위키도 lint 가능** (CLAUDE.md 워크플로우에 명시됨).

---

## 자동화 패턴 — cron + 5분 자동화 (미션 2와 연결 ⭐)

> 강사가 `crontab daily 08:10 UTC = 17:10 KST`로 매일 자동 컴파일

→ **너 미션 2 (5분마다 책 정보 GitHub 업로드)와 같은 패턴**. 
→ Day 2 07강 cron + [[1주차-2일차-07-프로세스와-네트워크]] = 강사 실제 사용 방법론.

---

## 너 활용 가능성

### Stage 4 파이널 프로젝트
- **자동 리포트 생성 시스템** — PRISMA-KB 패턴 응용
- 데이터 → LLM 자동 분석 → 보고서

### 졸업 후 진로 (Phase 6)
- 연구 보조 (대학원 진학 시) — 직접 사용 가능
- 오픈소스 기여 후보 (강사 도구 = 기여 진입점)

### 즉시 활용 — yeardream-wiki에 적용
- **lint.py 패턴** = CLAUDE.md "Lint" 워크플로우 자동화
- **export.py 패턴** = 단계별 종합 ([[syntheses/]]) 자동 생성
- **compile_auto cron** = 강의 자료 자동 ingest 스크립트

---

## 학술 용어 풀이 (비전공자용)

- **SR (Systematic Review)** = 체계적 문헌고찰. 모든 관련 논문을 정해진 방법으로 수집·분석·종합
- **PRISMA 2020** = SR 작성 국제 표준 가이드라인
- **SSCI** = 사회과학 저널 인용 지수. 국제 우수 학술지 표시
- **RQ (Research Question)** = 연구 질문. SR의 핵심 골격
- **Scopus·Web of Science·OpenAlex** = 학술 논문 검색 DB (DOI 메타데이터)

---

## 강사님이 너한테 이걸 준 이유 (추정)

1. **너 학습 방식 = 강사 연구 방식과 동일** — LLM + 마크다운 + Vault 분리. 메타 인지 신호
2. **연구 주제 = 너 케이스와 직결** — 한국 비전공자 AI 인재 개발의 살아있는 예시
3. **Stage 4 파이널 프로젝트 영감** — 자동 리포트·SR 자동화 패턴 응용
4. **진로 확장 가능성** — 대학원·연구 보조·오픈소스 기여 출발점

---

## 액션 아이템

- [ ] GitHub `dschloe/PRISMA-KB` 한 번 둘러보기 (10분)
- [ ] **Karpathy LLM 지식베이스 X 포스트** 읽기 (https://x.com/karpathy/status/2039805659525644595)
- [ ] yeardream-wiki에 **lint·export 패턴 도입** 검토
- [ ] **Paper 1 RQ5** (연구 격차) = 너 비전공자 케이스가 격차 메우는 사례인가 고민
- [ ] 강사한테 직접 물어보기: "왜 저한테 이 자료 주셨나요?" → 답이 진로 힌트

---

## 관련 페이지

- [[AI-엔지니어-가이드]] — Phase 6 (대학원·연구 보조 옵션 추가)
- [[서비스-기획-워크플로우]] — PRISMA-KB도 같은 4단계 패턴
- [[AI-도구-조합]] — LLM-agnostic 철학과 일치
- [[학습-워크플로우]] — 너 위키 패턴과 동일
- [[공룡책-OS-Concepts-10판]] — 외부 자료 누적 패턴

## 출처

- `raw/external/README 2.md` (181 줄, 영문)
- GitHub: https://github.com/dschloe/PRISMA-KB
- 강사 직접 제공 (2026-05-29 라이브)
