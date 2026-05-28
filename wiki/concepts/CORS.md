---
type: concept
aliases: [CORS, Cross-Origin Resource Sharing, SOP, Same-Origin Policy, Preflight]
stage: 1
first_seen: 2026-05-28
last_updated: 2026-05-28
sources: 1
related: [[HTTP-프로토콜]], [[REST-API]], [[HTTP-상태코드]]
---

# CORS / SOP

## 한 줄 정의

**SOP** (Same-Origin Policy) = 브라우저의 기본 보안 정책 ("같은 출처만 허용"). **CORS** (Cross-Origin Resource Sharing) = SOP의 **예외 허용 메커니즘**.

## 핵심 아이디어

### SOP — 브라우저 기본 차단

```
브라우저 기본 규칙:
"같은 Origin에서 온 리소스만 JavaScript가 읽을 수 있음"
```

**Origin = Scheme + Host + Port** (셋 다 일치해야 Same-Origin):

```
https://www.example.com:443/path/page.html
└─┬───┘  └────┬────────┘ └┬┘
Scheme    Host (Domain)  Port
```

### Same-Origin 판단 예 (기준: `https://www.example.com`)

| URL | 결과 | 이유 |
|---|---|---|
| `https://www.example.com` | ✅ Same-Origin | 정확히 일치 |
| `https://www.example.com:443` | ✅ Same-Origin | 443은 HTTPS 기본 |
| `http://www.example.com` | ❌ Cross-Origin | scheme 다름 |
| `https://example.com` | ❌ Cross-Origin | subdomain 다름 |
| `https://login.example.com` | ❌ Cross-Origin | subdomain 다름 |
| `https://www.example.com:70` | ❌ Cross-Origin | port 다름 |

### CORS — 명시적 허용

서버가 헤더로 "이 출처는 OK" 보내면 브라우저 통과:
```http
Access-Control-Allow-Origin: https://www.example.com
Access-Control-Allow-Methods: GET, POST, PUT, DELETE
Access-Control-Allow-Headers: Content-Type, Authorization
```

### CORS Request 2종

| | Simple Request | Preflighted Request |
|---|---|---|
| **메서드** | GET·POST·HEAD | PUT·DELETE 등 |
| **Content-Type** | text/plain, form-data, urlencoded만 | application/json 등 |
| **OPTIONS 사전 요청** | 없음 | **있음** |
| **속도** | 빠름 | 느림 (왕복 2번) |

### Preflighted 흐름

```
1. 브라우저: OPTIONS (메서드·헤더 사전 확인)
2. 서버: "그 출처·메서드·헤더 OK"
3. 브라우저: 실제 요청
```

### Same-Origin vs Same-Site

| | Same-Origin | Same-Site |
|---|---|---|
| **기준** | scheme + domain + port 모두 일치 | eTLD+1 (도메인 + .com) 일치 |
| **엄격함** | 매우 엄격 | 느슨 |
| **subdomain 차이** | Cross | Same-Site |
| **port 차이** | Cross | Same-Site |
| **scheme 차이** | Cross | Same-Site (옛 정의) |

→ **Same-Site가 더 넓은 범위**. 쿠키 `SameSite` 속성에서 활용.

## 왜 중요한가

- **웹 보안의 기둥** — XSS·CSRF 방어
- **API 개발 빈번 이슈** — 프론트엔드↔백엔드 다른 도메인이면 늘 만남
- **사용자 적용** — Cloudflare Pages 웹앱과 다른 도메인 API 호출 시 직접 마주침

## 자주 헷갈리는 것

### "CORS 에러는 서버 잘못"

절반만 맞음. **브라우저가 차단**하는 거지 서버는 실제로 응답함. 단 응답을 JavaScript가 못 읽음. 서버에 `Access-Control-Allow-Origin` 추가하면 해결.

### "CORS는 어디서나 작동"

**브라우저에서만**. Postman·curl·서버 간 통신은 CORS 무시. 그래서 백엔드끼리 통신엔 영향 없음.

### "CORS = 보안 위협 막아주는 거"

사실은 **브라우저의 기본 차단을 풀어주는** 메커니즘. 보안 자체는 SOP가 담당.

## 일상 비유: 회사 출입 화이트리스트

- **SOP** = 회사 보안 정책 ("사내 인트라넷은 사내 직원만")
- **Origin** = 회사·층 (예: "본사 3층 영업팀")
- **Cross-Origin 요청** = 외부 협력사 직원이 내부 서버 접근 시도
- **CORS 허용** = "이 협력사는 OK"로 사전 화이트리스트 등록
- **Preflighted Request** = 출입 전 "내일 OO 출입 가능?" 사전 신청

## 관련 페이지

- [[HTTP-프로토콜]] — CORS 헤더는 HTTP 헤더
- [[REST-API]] — Cross-Origin API 호출 시 마주침
- [[HTTP-상태코드]] — Preflight 응답 코드

## 출처

- [[1주차-3일차-02-인터넷과-HTTP]] (챕터 6)
