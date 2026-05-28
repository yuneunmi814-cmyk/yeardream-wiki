---
type: tool
aliases: [AI 도구 조합, Claude Pro, Copilot, Cursor, Gemini, ChatGPT, 비용 절감]
stage: 1
first_seen: 2026-05-29
last_updated: 2026-05-29
related: [[Python]], [[AI-엔지니어-가이드]], [[현업-용어]]
---

# AI 도구 조합 (은미 맞춤)

## 한 줄 정의

**Claude Pro 메인 + 무료 도구 혼합**으로 월 $30 시작점. 작업별 최적 도구 분배.

---

## 추천 조합 (2026-05-29 기준)

### 시작점 — 월 $30

```
[메인] Claude Pro                    $20/월
[코드 통합] GitHub Copilot           $10/월  (SwiftUI·Xcode·VSCode)
[보조] Gemini 무료 + ChatGPT 무료   $0
───────────────────────────────────
                                    $30/월
```

### 확장 단계 — 월 $50~$120

```
[메인] Claude Pro / Max              $20~$100
[코드 통합] Cursor Pro               $20  (Claude 통합 에디터)
[보조] Gemini Advanced (선택)        $20  (긴 컨텍스트 200만 토큰)
```

---

## 작업별 도구 분배 ⭐

| 작업 | 추천 도구 | 이유 |
|---|---|---|
| **위키 정수 추출·복잡 풀이** | **Claude Pro** ⭐ | 깊이 사고·톤 맞춤 |
| **자동화 워크플로우** | **Claude Code** ⭐ | 일상 사용 중 |
| **SwiftUI·Xcode 코드** | **Copilot** 또는 **Cursor** | 에디터 통합 |
| **콘텐츠 작성** (yoon.ai.lab) | **Claude** | 톤·캐릭터 일관성 |
| **간단 질문·검색** | Gemini 무료 / ChatGPT 무료 | 토큰 아끼기 |
| **실시간 검색·리서치** | **Perplexity** (무료) | 출처 명시·웹 검색 |
| **이미지 생성** (인스타) | ChatGPT (DALL-E) / Gemini | 한글 친화 |
| **긴 문서 요약** | **Gemini** | 200만 토큰 컨텍스트 |
| **번역** | Gemini 또는 DeepL | 한↔영 정확도 |

---

## Claude 사용량 구독 가이드

| 플랜 | 월 비용 | 적합 |
|---|---|---|
| Claude.ai 무료 | $0 | 가끔 |
| **Claude Pro** ⭐ | $20 | **은미 시작점** (일상 + Claude Code) |
| Claude Max 5x | $100 | 코드 작업 매일 |
| Claude Max 20x | $200 | 풀로 돌리는 사람 |

**의사결정 흐름**:
1. Claude Pro $20 시작
2. 한도 자주 차면 → Max 5x ($100) 업그레이드
3. 그래도 부족하면 → Max 20x ($200)

---

## 한도 관리 (Anthropic Console)

**경로**:
```
console.anthropic.com 로그인
   → Settings → Plans & Billing → Usage limits
   → "Set monthly spending limit" 입력
   → Notifications → Email alerts 활성화
```

**추천**: 처음 $20/월부터 → 사용량 보고 조정.

**대시보드 확인 도구**:
- **Cloudflare Analytics** (은미 사용 중) — `dash.cloudflare.com` → Pages → Analytics
- **Anthropic Console** — `console.anthropic.com` → Usage
- **OpenAI Platform** — `platform.openai.com` → Usage

---

## 도구 카테고리 정리

### 코딩 통합 에디터
- **GitHub Copilot** ($10) — VSCode·Xcode 자동완성
- **Cursor** ($20 Pro) — Claude 통합 전용 에디터
- **Windsurf** — 비슷, Codeium 신제품
- **Claude Code** — 터미널 기반, 일상 사용 ⭐

### LLM 채팅·작업
- **Claude** ⭐ — 글쓰기·복잡 사고·코드 강함
- **ChatGPT** — 멀티모달·플러그인 풍부
- **Gemini** — 긴 컨텍스트·구글 통합
- **Perplexity** — 검색·출처 명시

### 이미지·멀티미디어
- **DALL-E 3** (ChatGPT)
- **Midjourney** ($10) — 가장 예쁨
- **Gemini 이미지 생성**

---

## 토큰 절약 워크플로우 ⭐ (2026-05-29 추가)

**핵심**: 무료 도구로 1차 처리 → Claude로 정수만 가져옴.

```
[간단 질문]      → Gemini / ChatGPT 무료
[긴 문서 요약]   → Gemini (200만 토큰 컨텍스트)
       ↓
[결과를 Claude에] → 정수 추출·위키 누적·깊이 분석
       ↓
[Claude Code]    → 자동화·코드·복잡 작업
```

→ Claude 토큰 70% 절약 패턴.

## Copilot 의사결정 (2026-05-29 추가)

| 상황 | Copilot 가치 |
|---|---|
| SwiftUI 자주 만든다 | ✅ 매우 유용 |
| Xcode 자주 켠다 | ✅ 유용 |
| 거의 Claude Code만 쓴다 | ⚠️ 중복 가능 |
| Cursor 쓴다 | ❌ Claude 통합돼있어 중복 |

**Claude Code vs Copilot 차이**:
- **Claude Code** = 터미널. 새 코드 생성·자동화·복잡 작업
- **Copilot** = 에디터 안 자동완성. 한 줄 칠 때 다음 줄 추천

→ 보완 관계. 너 SwiftUI 빈도에 따라 결정.

## 콘텐츠 자산화

- **"AI 부트캠프생이 매달 쓰는 도구 5개"** — yoon.ai.lab 정기
- **"$30으로 AI 풀스택 작업 가능한 도구 조합"** — prompt.by.yoon
- **"Claude Pro vs Max — 언제 업그레이드?"** — 의사결정 가이드
- **"무료 도구로 Claude 토큰 70% 절약"** ⭐ — 토큰 절약 워크플로우

---

## 🙋 구글 AI 두 계보 (2026-05-29 추가)

```
[Google Brain]                    [DeepMind]
언어·검색 전문                     게임·과학·강화학습 전문
   ↓                                  ↓
2017 Transformer                  2014 구글이 DeepMind 인수
2018 BERT                         2016 AlphaGo Lee (이세돌) ⭐
2021 MUM                          2017 AlphaGo Zero (스스로 학습)
2023 PaLM, Bard                   2018 AlphaZero (바둑·체스·쇼기)
                                  2019 AlphaStar (스타크래프트 II) ⭐
                                  2020 AlphaFold (단백질, 2024 노벨상)
              ↘    ↙
            2023 Google DeepMind 통합
                  ↓
            2024 Gemini ⭐ (둘의 합작)
```

### 알파고 시리즈

| 연도 | 이름 | 정복 |
|---|---|---|
| 2016 | **AlphaGo Lee** | 이세돌 격파 |
| 2017 | AlphaGo Zero | 사람 기보 없이 스스로 학습 → AlphaGo Lee 100:0 |
| 2018 | AlphaZero | 바둑·체스·쇼기 (범용) |
| 2019 | **AlphaStar** | **스타크래프트 II** 그랜드마스터 (상위 0.15%) |
| 2020 | AlphaFold | 단백질 구조 예측 → **2024 노벨화학상** |

### 스타크래프트가 바둑보다 어려웠던 이유

| | 바둑 | 스타크래프트 |
|---|---|---|
| 정보 | 완전 (다 보임) | **불완전** (안개) |
| 시간 | 턴제 | **실시간** |
| 유닛 | 1종 | 다양 |
| 행동 | 200여 수 | **분당 수백 명령** |

→ AlphaStar 의의 = **불완전·실시간 게임 정복**.

### 비유 정리

- **Google Brain** = 도서관 사서 (언어·검색)
- **DeepMind** = 바둑 챔피언 (게임·과학)
- **Gemini (2024)** = 둘이 결혼해서 낳은 멀티모달 AI

---

## 관련 페이지

- [[AI-엔지니어-가이드]] — 직무 가이드
- [[Python]] — Claude로 짜는 주력 언어
- [[현업-용어]] — 클라우드·SaaS

## 출처

- 사용자 사용 패턴 분석 (Claude Code 일상 + Cloudflare Pages + SwiftUI)
- 2026-05-29 기준 시장 가격
