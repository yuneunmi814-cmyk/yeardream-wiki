---
type: concept
aliases: [컴퓨터의 이해, 컴퓨터 기초, 기계어, 운영체제, OS, Low/High Level Language]
stage: 1
first_seen: 2026-05-26
last_updated: 2026-05-27
sources: 2
related: [[app-web-services]], [[http-protocol]], [[database-basics]], [[library-vs-framework]]
---

# Computer Basics

## 한 줄 정의

컴퓨터가 **0과 1로 동작하는 기계**라는 사실에서 출발해, 사람이 쓰는 프로그래밍 언어가 어떻게 그 기계 위에서 돌아가는지, 그리고 OS가 그 복잡함을 어떻게 추상화하는지에 대한 기초 멘탈 모델.

## 핵심 아이디어

### 0과 1, 기계어

- 컴퓨터가 직접 알아듣는 언어는 **0 or 1**
- 일상 전자기기 동작도 결국 1/0의 조합: TV·컴퓨터·에어컨 on/off
- 기계어 예시: `0000 1001 1100 0110 1010 1111 0101 1000` (8비트 단위)
- **개발자의 역할**: "복잡한 기계어를 사람이 사용하기 쉽게 만들어 기계를 활용하게 한다" (강의 본문)

### 프로그래밍 언어로 소통하는 개발자

대표 언어 예시 (강의 본문 그대로):
> Javascript, Swift, Kotlin, C++, Go, C, Rust, Assembley, Java, C#, Python …

모두 **컴퓨터 기계 위에서 실행되기 위한 언어들**.

### 번역 흐름

```
Code 작성 → 인터프리터 / 컴파일러 → 기계어 번역 → 컴퓨터 인식
```

- **인터프리터**: 코드를 한 줄씩 즉시 해석·실행 (Python·JavaScript 등)
- **컴파일러**: 코드 전체를 미리 번역 → 실행파일 생성 (C·C++·Rust 등)

### Low level vs High level language

- **Low level**: 기계와 직접적으로 더 가까운 언어 (Assembly 등)
  - 프로그래머가 기계를 **직접 컨트롤** 가능, **속도가 빠름**
  - 단, 작성이 어렵고 실수하기 쉬움
- **High level**: 단점을 보완하기 위해 나온 언어 (Python·JavaScript 등)
  - "고차원의 언어"라는 의미가 **아님** — 강의 본문 명시 메모
  - 사람이 읽고 쓰기 쉬운 추상화 수준

### 클라이언트와 서버 (Front-end / Back-end 첫 등장)

```
[배달앱(클라이언트)]  ⇄  [서버]
  Web: 프론트엔드        Web: 백엔드

  → 배달음식 주문
  ← 주문완료 / 배달이동
```

→ 자세히는 [[app-web-services]] 참조.

### 운영체제 (OS)

> "컴퓨팅 기계를 쉽게 다루기 위한 시스템 소프트웨어" (강의 본문)

| 분류 | 예시 |
|------|------|
| 데스크탑 | macOS / Windows / Linux |
| 모바일 | Android / iOS |

**스마트폰 OS의 일생**:
```
공장 제작 → OS 설치 → App 제작 → 사용자 활용
```

→ 출시 시점에 OS가 함께 배포됨 (사용자가 SwiftUI 앱 만든 경험으로 익숙한 흐름).

### OS = 하드웨어 접근 권한 관리자

카메라 활용 AR 어플리케이션 예시:
1. 앱이 카메라에 접근하려면 권한 필요
2. **OS가 카메라 접근 코드 제공** (OS 별로 코드 다름 → iOS·Android 따로 작성)
3. 개발자는 이를 활용해 앱 제작

권한 요청 UI 예시:
> "AR Measure PRO가 사진을 찍거나 동영상을 녹화하도록 허용하시겠습니까? — 앱 사용 중에만 / 이번만 / 허용 안함"

→ OS의 본질: 이런 컨트롤을 **사용자가 쉽게** 할 수 있게 돕는 시스템 소프트웨어.

## 왜 중요한가

- **모든 상위 계층의 토대** — 앱·웹·클라우드·AI 모두 이 위에서 돌아감
- **사용자 배경상 이미 작동 지식**: SwiftUI(iOS·Swift), Core ML, Cloudflare Pages(Linux 서버 추상화), Claude Code(macOS 일상). 이 페이지는 멘탈 모델 "정리" 용
- **콘텐츠 후보**: "0과 1로 시작하는 IT 한 장 설명" — 비전공자 친화 입문 시리즈

## 자주 헷갈리는 것

- **High level ≠ 고차원**: 단순히 사람 친화적 추상화 수준이 높다는 뜻
- **Low level = 빠르다, 어렵다 / High level = 편하다, 상대적으로 느릴 수도**: 트레이드오프 관계
- **인터프리터 vs 컴파일러**: 둘 다 "번역"이지만, 시점이 다름 (실행 시 vs 미리)
- **Front-end / Back-end는 "위치"가 아니라 "역할"**: 같은 서버 안에 둘 다 있을 수도

## 코드/실습 예시

(강의 진행·실습 후 보충)

## 관련 페이지

- [[app-web-services]] — 컴퓨터 위에서 돌아가는 서비스 계층
- [[http-protocol]] — Front/Back-end 간 통신 규약
- [[database-basics]] — 데이터 저장 계층
- [[library-vs-framework]] — 코드 추상화 단계 한 차원 위
- [[industry-terms]] — Git·클라우드·SaaS 등 상위 도구

## 출처

- [[lectures/week-01-day-1]]
- `raw/stage-1-foundations/[수업자료] 컴퓨터의 이해.pdf` (22p, Elice IT 리터러시 시리즈 1강)
- `raw/stage-1-foundations/00-it-literacy-computer-basics.md` (Vision OCR 추출본, 2026-05-27)
