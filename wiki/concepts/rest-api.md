---
type: concept
aliases: [REST API, RESTful, RESTful API, API, Open API, Application Programming Interface]
stage: 1
first_seen: 2026-05-26
last_updated: 2026-05-27
sources: 2
related: [[HTTP-프로토콜]], [[데이터베이스-기초]], [[앱-웹-서비스]], [[파싱]], [[동기-vs-비동기]]
---

# REST API

## 한 줄 정의

**API** = "프로그램끼리(Code 끼리) 대화를 하도록 도와주는 일" — Application Programming Interface.
**REST API** = "약속된 지정된 주소(URI)를 가지고 있고, 각 주소에 기능(함수)을 가지고 있는 형태" — 강의 본문 정의.

## 핵심 아이디어

### API의 본질 (강의 재정의)

> "네트워크를 통한 기능호출" (강의 본문 02 자료)

다른 프로그램의 기능을 **내가 호출할 수 있는 형태로 노출**한 것.

### REST API 동작 그림

```
약속된 주소: https://school.elice.io/courses/26028/info
                       ↓
[프론트엔드(요청)] — GET — [백엔드(응답)] — GET
```

→ HTTP 메서드 자세히는 [[HTTP-프로토콜]] 참조.

### 로그인 API 예시

```
[ID/PW 로그인]  ──→  [로그인 API]
       ↑                  ↓
 [로그인 성공]  ←──  [로그인 정보 DB 조회]
```

요청 형태:
```
[클라이언트] ── Shoppingmall.com/login (POST, 아이디/비밀번호) ──→ [DB]
```

### GET API — 국가별 사이트 패턴

같은 endpoint 패턴, 국가코드만 다름:

| URL | 결과 |
|-----|------|
| `https://www.apple.com/kr/` | 한국 사이트 (iPad 이미지) |
| `https://www.apple.com/jp/` | 일본 사이트 (iPhone 14 이미지) |

```
https://www.apple.com/{국가코드}/
```

→ **URL 패턴 = 자원 식별 규칙**. RESTful 설계의 핵심.

## Open API

> 외부에 공개되어 누구나 사용할 수 있는 API

### 강의 사례 — 행정안전부 주소찾기 API

| 항목 | 내용 |
|------|------|
| 분류 | 통신 - 우정 |
| 관리부서 | 주소정책과 |
| API 유형 | LINK |
| 활용신청 | 7544건 |
| 등록 | 2016-10-31 |
| **데이터 포맷** | **JSON + XML** |
| URL | http://www.juso.go.kr/openIndexPage.do |
| **비용** | **무료** |

→ 콘텐츠 후보: "행정안전부 무료 Open API 모음" (juso.go.kr · 공공데이터포털 등)

## REST API 설계 원칙 (강의 + 일반 보강)

강의에서 명시:
- **약속된 URI** = 자원을 식별
- **메서드별 기능** = GET·POST·PUT·PATCH·DELETE ([[HTTP-프로토콜]])

보강 (강의 미언급, 일반 지식):
- **자원 중심 URL**: `/users/42` (행위가 아닌 자원 표현)
- **HTTP 메서드로 의도 표현**: 메서드 이름이 동작을 말해줌
- **무상태(Stateless)**: 각 요청은 독립적, 서버가 클라이언트 상태 저장 X
- **표현(Representation)**: 같은 자원도 JSON·XML 등 다양한 형식 가능

## URI vs URL (강의 본문 메모 + 보강)

강의 본문:
> "URI는 서버에서의 특정 리소스 식별자를 지칭하고, URL은 우리가 흔히 사용하는 웹 사이트의 주소를 뜻한다. URI가 URL보다 더 큰 의미라는 것만 기억하고 넘어가자"

**보강**: 정확히는 **URI = URL ∪ URN**.
- URL: 자원의 **위치** (예: `https://example.com/page`)
- URN: 자원의 **이름** (예: `urn:isbn:0451450523` — 위치 무관)
- URI: 둘을 포괄하는 상위 개념

실무에선 URL과 URI를 거의 동의어로 사용.

## 왜 중요한가

- **Stage 3 AI 서비스개발자 트랙 핵심 토대**
- **AI Agent 개발의 일상**: 도구·외부 시스템 연결은 결국 REST API 호출
- **1인 컨설팅에서 사실상 매번 부딪힘** — 외부 API 통합, 자체 백엔드 설계
- 사용자는 Meta 광고 API·Cloudflare 등 **REST 사용 경험은 풍부** → **REST 설계** 단계가 새 영역

## 자주 헷갈리는 것

- **REST vs RESTful**: REST는 원칙(2000년 Roy Fielding 박사논문), RESTful은 그 원칙을 따르는 API. 실무에선 거의 같은 의미.
- **REST vs GraphQL**: REST는 자원 중심·다중 엔드포인트, GraphQL은 쿼리 중심·단일 엔드포인트
- **POST vs PUT**: POST=생성, PUT=전체 교체. PATCH가 부분 수정. ([[HTTP-프로토콜]] PUT vs PATCH 보강 참조)
- **API ⊃ REST API**: 모든 REST는 API지만, 모든 API가 REST는 아님 (GraphQL, gRPC, SOAP 등)

## 코드/실습 예시

(강의 진행·실습 후 보충)

## 관련 페이지

- [[HTTP-프로토콜]] — REST API의 메서드 토대
- [[데이터베이스-기초]] — REST API 뒤의 저장 계층
- [[앱-웹-서비스]] — REST API가 작동하는 WAS 구조
- [[파싱]] — REST 응답(JSON/XML) 파싱
- [[동기-vs-비동기]] — REST 호출의 두 모드

## 출처

- [[lectures/1주차-1일차]]
- `raw/stage-1-foundations/[수업자료] 데이터베이스와 REST API.pdf` (52p, 시리즈 03강)
- `raw/stage-1-foundations/[수업자료] 앱_웹 서비스를 위한 모든 것.pdf` (38p, 시리즈 02강에서도 REST 등장)
- `raw/stage-1-foundations/02-database-REST-API.md` (Vision OCR 추출본)
- `raw/stage-1-foundations/01-app-web-service.md` (Vision OCR 추출본)
