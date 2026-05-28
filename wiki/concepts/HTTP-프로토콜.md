---
type: concept
aliases: [HTTP, HyperText Transfer Protocol, HTTP 메서드, GET, POST, PUT, PATCH, DELETE]
stage: 1
first_seen: 2026-05-26
last_updated: 2026-05-27
sources: 1
related: [[앱-웹-서비스]], [[REST-API]], [[파싱]], [[동기-vs-비동기]]
---

# HTTP Protocol

## 한 줄 정의

기기·OS·브라우저 상관없이 **문자(Hyper Text)로 통신**하는 약속(Protocol). 웹·앱 통신의 기본 규약.

## 핵심 아이디어

### 통신의 정의 (강의 본문)

> "컴퓨터 간의 Communication (대화)"

예시:
- 컴퓨터 ↔ 컴퓨터
- 스마트폰 ↔ 서버
- 스마트폰 ↔ 스마트폰 (메신저)

### 통신의 원칙

> **기기간의 요청과 응답으로 이루어진 대화. 1요청, 1응답의 원칙**

배달앱 예시:
- 요청: "후라이드 치킨 주문"
- 응답: "주문 OK! 20분 기다려줘~"

### HTTP 분해

| 약자 | 의미 |
|------|------|
| **H** Hyper | 기기(스마트폰)에 상관없이 문자로 통신 |
| **T** Text | OS와 관계없이 문자로 통신 |
| **T** Transfer | 웹 브라우저에 상관없이 통신 |
| **P** Protocol | 통신 방식의 약속된 룰 |

> **Protocol 메모**: 통신 방식에 있어서 특정한 룰을 가지고 이대로 통신을 하자는 약속된 형태 (강의 본문)

### Hyper Text의 종류 — JSON / XML

**JSON 예시 (명함)**:
```json
{
  "id": 1,
  "name": "홍길동",
  "company": "(주)엘리스",
  "phone": "010-1234-5678"
}
```

**XML 예시 (음반)**:
```xml
<CD>
  <TITLE>Still got the blues</TITLE>
  <ARTIST>Gary Moore</ARTIST>
  <COUNTRY>UK</COUNTRY>
  <COMPANY>Virgin records</COMPANY>
  <PRICE>10.20</PRICE>
  <YEAR>1990</YEAR>
</CD>
```

→ 받은 문서에서 원하는 부분만 뽑는 건 [[파싱]] 영역.

## HTTP 메서드 — CRUD와의 매핑

강의에서 프론트·백엔드 양쪽에서 동일한 4개 메서드 표가 등장:

| 메서드 | 기능 (강의 본문) | CRUD |
|--------|------------------|------|
| **GET** | 기존 저장된 정보·페이지를 읽어옴 | Read |
| **POST** | 정보 저장·전달을 위해 서버에 전달 | Create |
| **PUT / PATCH** | 기존 저장된 정보 내용을 수정 | Update |
| **DELETE** | 저장된 정보를 삭제 | Delete |

### 디지털 명함 예시별 메서드

```
POST  : [명함촬영] → 저장할 명함정보 전달 (이름·회사·전화) → [Server]
GET   : [로그인 후] → 저장된 명함정보 요청 → ← 명함정보 전달
PUT   : [기존 명함] → 명함정보 수정 → ← 수정된 명함정보
DELETE: [기존 명함] → 명함정보 삭제 → ← 삭제 결과
```

GET 일상 예시:
- 로그인 후 Welcome 페이지의 사용자 이름 표시
- 쇼핑몰 제품 상세 페이지 (가격·이미지)

DELETE 일상 예시:
- 명함 삭제 / 계정 탈퇴 ("탈퇴 후 복구할 수 없습니다")

### 프론트엔드 ↔ 백엔드 메서드 호응

> "프론트가 GET으로 요청을 하면 백엔드도 반드시 GET으로 호응해야 한다" (강의 본문)

```
프론트엔드 요청 ──→ 백엔드 응답
GET            GET
POST           POST
PUT/PATCH      PUT/PATCH
DELETE         DELETE
```

## ⚠️ 강의 본문 보완 — PUT vs PATCH

강의 메모:
> "PUT은 정보를 수정하는 http 통신의 함수이지만 **보안적인 이슈가 꾸준히 제기되고 있어** 사용할 때 많은 주의를 필요로 한다. 이를 보완해서 나온 것이 PATCH이다."

**보강**:
- 일반적으로 **PUT = 자원의 전체 교체** (전체 필드를 새 값으로 덮어쓰기), **PATCH = 부분 수정** (특정 필드만 변경) 으로 구분이 본질.
- PUT은 RFC 표준에서 **멱등(idempotent)**이라는 특성 — 같은 요청을 여러 번 보내도 결과 동일.
- "보안 이슈로 PATCH가 등장"이라는 설명은 정확하지 않음. PATCH는 RFC 5789(2010)에서 부분 수정 의도 표현용으로 추가됨.
- 보안 우려가 있다면 그건 PUT 자체보다 **권한 제어 미흡**의 문제 — 어떤 메서드든 동일.

→ 실무·시험·면접에서 "PUT/PATCH 차이"를 묻는다면 **전체 vs 부분 수정**으로 답하는 게 안전.

## 왜 중요한가

- **모든 웹·앱 통신의 토대** — REST API([[REST-API]]), AI Agent 외부 호출, 자동화 워크플로우의 기본
- 사용자(Meta 광고 API·Cloudflare Pages 경험)는 이미 HTTP 사용은 익숙 → **메서드별 의도·규약**을 명시적 멘탈 모델로 정리하는 단계
- 1인 컨설팅에서 API 통합 자주 부딪힘 — 메서드 잘못 쓰면 의외의 동작 (캐싱·재시도 등)

## 자주 헷갈리는 것

- **POST vs PUT**: POST는 "생성"(URI는 서버가 결정), PUT은 "특정 URI에 자원 전체 교체"
- **PUT vs PATCH**: 위 보강 섹션 참조
- **GET 멱등성**: GET은 여러 번 호출해도 같은 결과 — 그래서 캐싱 가능
- **헤더 vs 바디**: HTTP 요청·응답은 헤더(메타 정보) + 바디(실제 데이터) 구조 (강의에선 미언급, 후속 학습 시 보충)

## 코드/실습 예시

(강의 진행·실습 후 보충 — fetch·axios·requests 등)

## 관련 페이지

- [[앱-웹-서비스]] — HTTP는 그 안의 통신 계층
- [[REST-API]] — HTTP 메서드 위에 세워진 API 설계 패턴
- [[파싱]] — JSON/XML 응답 파싱
- [[동기-vs-비동기]] — HTTP 요청의 두 가지 호출 방식

## 출처

- [[lectures/1주차-1일차]]
- `raw/stage-1-foundations/[수업자료] 앱_웹 서비스를 위한 모든 것.pdf` (38p)
- `raw/stage-1-foundations/01-app-web-service.md` (Vision OCR 추출본)
- `raw/stage-1-foundations/02-database-REST-API.md` (Vision OCR 추출본 — REST API와 HTTP 메서드 표 재등장)
