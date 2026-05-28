---
type: concept
aliases: [JSON Web Token, 제이더블유티]
stage: 1
first_seen: 2026-05-28
last_updated: 2026-05-28
sources: 1
related: [[인증과-인가]], [[토큰]], [[해시]], [[쿠키]], [[세션]]
---

# JWT (JSON Web Token)

## 한 줄 정의

**JSON 형식의 인증 토큰**. 모던 웹·앱 인증의 사실상 표준. 점(.)으로 구분된 Header·Payload·Signature 3 파트.

## 핵심 아이디어

[[세션]]의 **분산 환경 약점** 해결책. 서버에 저장 안 함 → 스케일 아웃 친화.

### 구조

```
eyJhbGc...  .  eyJzdWIi...  .  SflKxwRJ...
└ Header ┘    └ Payload ┘    └ Signature ┘
```

**1. Header** (Base64 인코딩):
```json
{ "alg": "HS256", "typ": "JWT" }
```

**2. Payload** — Claims:
```json
{
  "sub": "1234567890",
  "name": "John Doe",
  "iat": 1516239022,
  "exp": 1516242622,
  "role": "admin"
}
```

⚠️ **Base64만 적용 = 누구나 디코드 가능**. 비밀번호 ❌.

**3. Signature**:
```
HMACSHA256(
  base64UrlEncode(header) + "." + base64UrlEncode(payload),
  your-256-bit-secret
)
```

서버 시크릿 키로 서명. **위변조 시 검증 실패**.

### 동작 흐름

```
1. 사용자 로그인 (ID·PW)
2. 서버: JWT 발급
3. 클라이언트: 토큰 저장 (LocalStorage·HttpOnly Cookie 등)
4. 매 요청: Authorization: Bearer <JWT>
5. 서버: 서명 검증만 (DB 조회 ❌)
6. 응답
```

### Refresh Token 보완

```
Access Token  → 짧은 만료 (15분~1시간)
Refresh Token → 긴 만료 (2주 등)

Access 만료 → Refresh로 새 Access 발급 (재로그인 ❌)
Refresh 만료 → 그때만 재로그인
```

## 왜 중요한가

- **분산·다플랫폼 표준** — 마이크로서비스·SPA·iOS·Android 다 JWT
- **서버 stateless 유지** → 스케일 아웃 친화
- **사용자 적용** — 프로젝트윤365 iOS 앱·클라이언트 솔루션 인증 1순위 ⭐⭐

## 자주 헷갈리는 것

### "JWT는 암호화"

**서명만**. Payload는 누구나 디코드 가능. 민감 정보 넣지 말 것.

### "JWT가 무조건 [[세션]]보다 낫다"

작은 서비스·단일 서버는 **세션이 더 안전·간단**. JWT는 분산·다플랫폼 시 진가.

### "한 번 발급한 JWT 취소 어렵다"

서명만 검증하니 **블랙리스트** 없으면 만료까지 유효. → Refresh Token으로 Access 짧게 + 블랙리스트 DB 병행이 흔한 절충.

## 일상 비유: 영화관 손목 밴드 (위변조 방지 시일)

- **Header**: 어느 영화관 (HS256 = 어느 보안 회사)
- **Payload**: 좌석 번호·시간 — **누구나 볼 수 있음**
- **Signature**: 영화관 도장 — **위조 시 들통**

손님이 좌석 마음대로 바꿔도 도장이 안 맞아서 입장 거부. 영화관은 **도장만 확인**, 손님 명단 DB 조회 ❌ → 빠름.

## 실무 적용 (사용자 프로젝트윤365)

- iOS 앱 ↔ 백엔드 API 인증
- 클라이언트 솔루션의 권한 관리
- SPA (Single Page App) 로그인 유지
- 다중 도메인 SSO (Single Sign-On)

## 콘텐츠 자산화

- "JWT 한 컷" — aaa.bbb.ccc 구조 (yoon.ai.lab 최우선)
- "JWT Payload는 비밀이 아니다"
- "Refresh Token이 등장한 이유"

## 관련 페이지

- [[인증과-인가]] — JWT는 인증 후 발급
- [[토큰]] — JWT는 토큰의 일종
- [[해시]] — Signature에 HMAC-SHA256 사용
- [[쿠키]] — JWT 저장 방법 중 하나 (HttpOnly Cookie)

## 출처

- [[1주차-3일차-03-보안]] (챕터 6)
