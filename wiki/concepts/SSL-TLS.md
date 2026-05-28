---
type: concept
aliases: [SSL, TLS, HTTPS, Secure Sockets Layer, Transport Layer Security]
stage: 1
first_seen: 2026-05-28
last_updated: 2026-05-28
sources: 1
related: [[HTTP-프로토콜]], [[SSH]], [[해시]], [[CORS]]
---

# SSL / TLS / HTTPS

## 한 줄 정의

**SSL/TLS** = 통신을 암호화하는 프로토콜. **HTTPS** = HTTP + TLS. 현대 웹의 사실상 강제 표준.

## 핵심 아이디어

### SSL → TLS 진화

같은 것의 다른 이름:
- SSL 1.0 → 2.0 → 3.0 → **TLS 1.0** → 1.1 → 1.2 → **1.3** (현재)
- 일반인 통칭 "SSL/TLS", 정확히는 **모두 TLS**

[[OSI-7계층]] 5·6층에 위치 (세션·표현).

### TLS 핸드셰이크 (간략)

```
1. 클라이언트: "안녕, 내가 지원하는 암호 알고리즘은 이거"
2. 서버: "이걸로 가자 + 내 인증서(public key 포함)"
3. 클라이언트: 인증서 검증 → 대칭키 만들어서 서버 public key로 암호화 → 전송
4. 서버: 자기 private key로 복호화 → 대칭키 획득
5. 양쪽 다 대칭키 보유 → 빠른 암호화 통신
```

→ **비대칭키로 시작 → 대칭키로 본 통신** (속도 위해).

### HTTPS = HTTP + TLS

```
HTTP:   GET /api ─────────────→ 서버   (평문, 누구나 봄)
HTTPS:  GET /api ═══암호화═══→ 서버   (TLS 채널, 못 봄)
```

- HTTP는 평문. 비밀번호·카드번호 그대로 노출 → 큰일
- HTTPS는 TLS 채널 위. 중간에서 못 봄
- 브라우저 주소창 자물쇠 = HTTPS

## 왜 중요한가

- **현대 웹의 강제 표준** — Chrome·Safari가 HTTP 사이트에 "위험" 경고
- **[[SEO]] 영향** — 구글이 HTTPS 우선 노출
- **모든 결제·로그인** 보호의 기초
- **사용자 적용** — Cloudflare Pages 자동 HTTPS 적용

## 자주 헷갈리는 것

### "HTTPS면 다 안전"

TLS는 **전송 구간**만 암호화. 서버 도착 후엔 서버 책임. 서버 해킹되면 그대로 노출.

### "자물쇠 = 신뢰"

Phishing 사이트도 HTTPS 가능 (인증서 무료 발급 Let's Encrypt 등장 후). **자물쇠 ≠ 안전한 사이트**. 도메인 확인 필수.

### "SSL과 TLS는 다른 것"

같은 계보. SSL이 옛 이름, TLS가 현재. 기술적으론 다 TLS 사용.

## 일상 비유: 외교 행낭 (Diplomatic Pouch)

- **HTTP** = 그냥 손편지 (누구나 읽음)
- **HTTPS/TLS** = 외교 행낭 (밀봉, 도장, 중간 검열 ❌)
- **TLS 핸드셰이크** = 양국 대사가 서로 신원·암호 합의
- **인증서** = 대사의 외교관 신분증

## 관련 페이지

- [[HTTP-프로토콜]] — HTTPS = HTTP + TLS
- [[SSH]] — 다른 보안 프로토콜
- [[해시]] — TLS 인증서 무결성에 사용
- [[CORS]] — HTTPS·HTTP 다른 Origin

## 출처

- [[1주차-3일차-01-주요-프로토콜]] (챕터 6)
