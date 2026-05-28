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

---

## 🙋 은미 정수 (2026-05-29) — 막혔다가 푼 것

### API란?

**API = 두 프로그램끼리 약속한 대화 방식**. 은미 표현: "내가 가진 자원을 다른 사람이 가져다 쓸 수 있게 하는 거" ✅ 정답.

인스타 본사가 API 공개 → 외부 앱(사진 편집 앱 등)이 "이 사용자 게시물 가져갈게" 요청 → 인스타 API가 응답. 외부 앱은 인스타 내부 코드 몰라도 **API 약속만 알면 사용 가능**.

### REST API = HTTP 4메서드 + URL로 만든 깔끔한 통로

마인크래프트 명령어 비유: `/give @s diamond` (POST 비슷), `/list` (GET 비슷). 모든 게임·앱이 비슷한 명령어 규칙이면 새 게임 와도 빠르게 이해 = **REST의 매력**.

### URI vs URL

사실상 같이 씀.

| | 풀이름 | 뜻 |
|---|---|---|
| URL | Uniform Resource **Locator** | 자원의 **위치** |
| URI | Uniform Resource **Identifier** | 자원의 **식별자** |

→ URL이 URI의 한 종류. 실무에선 같다고 봐도 됨.

### Endpoint = API URL 1개 = 서버 한 기능 출입구 (게이트)

은미 직감 ✅: "게이트 같은 거". GitHub 예시:

```
github.com/yuneunmi814-cmyk                          ← 프로필 Endpoint
github.com/yuneunmi814-cmyk/yeardream-wiki           ← 레포 Endpoint  
github.com/yuneunmi814-cmyk/yeardream-wiki/issues   ← 이슈 Endpoint
```

인스타 비유:
- "프로필 보기" 게이트 = `GET /users/유저ID`
- "DM 보내기" 게이트 = `POST /messages`
- "좋아요" 게이트 = `POST /posts/123/like`

**모든 URL 1개 = Endpoint 1개**. 끝 지점(end point) — 서버에서 일이 처리되는 그 지점.

### Open API + Rate Limit (2026-05-29 추가)

**Open API = 누구나 쓸 수 있게 공개된 API**.

대표 예:
- **행정안전부 주소찾기 API** — 무료
- **카카오 지도 API** — 사이트에 카카오맵 띄움
- **OpenWeather API** — 날씨
- **Claude API** — Anthropic (은미 일상 사용)

**API Key**: 긴 문자열 발급. 누가 쓰는지 추적·과금용.

→ 너가 데이터 공개하면 = **너도 Open API 제공자**.

**Rate Limit (요율 제한)**:
- 분당/일당 호출 횟수 제한
- 무료: 분당 10회·일 1000회 등
- 초과 시 **HTTP 429 Too Many Requests** (Day 3 [[HTTP-상태코드]])

**Rate Limit 관리 6전략**:
1. **호출 빈도 ↓** — 진짜 필요할 때만
2. **캐싱** — 같은 요청은 [[캐시]]에서 (Redis)
3. **배치 처리** — 여러 요청 묶기
4. **백오프 (Exponential Backoff)** — 429 받으면 1·2·4·8초 점점 길게 재시도
5. **유료 플랜** — 한도 증가
6. **모니터링 대시보드** — 사용량 추적·임박 알림

**Python 코드 (단순)**:
```python
import time
for i in range(100):
    response = call_claude_api(prompt)
    time.sleep(0.5)   # 호출 간격 조정
```

### Exponential Backoff (지수 백오프) — 2026-05-29 추가

**Backoff = 뒤로 물러나기 + Exponential = 두 배씩 증가**.
→ 재시도 간격을 **1·2·4·8·16·32초** 점점 두 배.

**흐름**:
```
1차 → 429 → 1초 대기
2차 → 429 → 2초 대기
3차 → 429 → 4초 대기
4차 → 429 → 8초 대기
5차 → 200 OK ✅
```

**비유**: 카톡 답장 안 오는 친구한테 5·10·20·40초 간격 늘려서 → 친구 회복할 시간.

### Redis 응답 캐싱 — 2026-05-29 추가

```python
def get_weather(city):
    cached = redis.get(f"weather:{city}")
    if cached:
        return cached                                # ← 캐시 Hit
    
    response = openweather_api(city)
    redis.set(f"weather:{city}", response, ex=600)   # 10분 저장
    return response
```

→ 같은 요청 오면 API 안 가고 Redis에서. **Rate Limit 회피 + 빠름**.

### 백오프 라이브러리 — 2026-05-29 추가

**Python `tenacity`** ⭐:
```python
from tenacity import retry, wait_exponential

@retry(wait=wait_exponential(multiplier=1, min=1, max=60))
def call_api():
    return openweather_api(...)
# 실패 시 1·2·4·8·16·32·60초 자동 재시도
```

**JavaScript**: `axios-retry`, `p-retry`

→ 직접 짜지 말고 라이브러리. 안전·검증됨.

### 사용량 대시보드 도구 — 2026-05-29 추가

| 도구 | 용도 |
|---|---|
| **Cloudflare Analytics** ⭐ (은미 이미 사용) | 웹사이트 트래픽·요청 |
| **AWS CloudWatch** | AWS 서비스 모니터링 |
| **Datadog** | 종합 (유료) |
| **Grafana** | 오픈소스 |
| **API 콘솔** | Anthropic·OpenAI 각자 |

**알림**: 한도 80% → Slack/이메일 / 에러율 5% → 전화

→ Stage 3·4에서 직접 다룰 패턴.

### PUT vs PATCH 상세 (2026-05-29 추가)

- **PUT** = 전체 교체 (필드 다 새로 적기)
- **PATCH** = 부분 수정 (특정 필드만)

게시물 `{"title":"안녕", "content":"잘 지내요"}`:
- PUT: `{"title":"안녕!", "content":"잘 지내요"}` 전체 다시
- PATCH: `{"title":"안녕!"}` 바꿀 부분만

---

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
