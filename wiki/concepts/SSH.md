---
type: concept
aliases: [SSH, Secure Shell, 시큐어 셸]
stage: 1
first_seen: 2026-05-27
last_updated: 2026-05-28
sources: 2
related: [[SSL-TLS]], [[TCP-UDP]], [[1주차-2일차-07-프로세스와-네트워크]]
---

# SSH (Secure Shell)

## 한 줄 정의

**원격 호스트에 안전하게 접속하기 위한 프로토콜**. 22번 포트. Public/Private Key 쌍으로 인증·암호화.

## 핵심 아이디어

### TELNET → SSH 진화

| | TELNET | SSH |
|---|---|---|
| **등장** | 1969 | 1995 |
| **암호화** | ❌ (평문) | ✅ (강력) |
| **포트** | 23 | 22 |
| **사용** | 거의 사장 | **사실상 표준** |

### Public/Private Key 쌍

- **Public Key (공개키)**: 누구나 봐도 됨. 서버에 등록 (예: GitHub Settings)
- **Private Key (개인키)**: 본인 컴퓨터에만. **절대 노출 금지** ⚠️

### 인증 흐름

```
1. 클라이언트가 서버에 접속 요청
2. 서버: "내 public key 줄게"
3. 클라이언트: 자기 private key로 서명한 데이터 전송
4. 서버: 등록된 클라이언트 public key로 검증
5. 검증 성공 → 암호화된 채널 수립
```

### SSH 특징

- **22번 포트** (변경 가능)
- **모든 데이터 암호화**
- **트래픽 압축** (빠른 전송)
- **Public/Private Key** 또는 비밀번호 인증

## 왜 중요한가

- **개발자 일상 도구** — 서버 관리·GitHub 푸시·EC2 접속
- **사용자 일상** — Claude Code SSH 작업, 클라우드 배포
- **AI 시대에도 안 사라짐** — Day 2 [[VI-편집기]] 강의자 지시 "SSH 환경에서 vi 필수"

## 자주 헷갈리는 것

### "SSH = SSL"

다름. **SSH = 원격 접속 프로토콜**, **[[SSL-TLS]] = 통신 암호화 (HTTPS 기반)**. 다만 둘 다 Public/Private Key 사용.

### "Private Key 잃어버려도 OK"

❌ 큰일. **Private Key = 신원**. 잃으면 서버 접근 ❌, 도둑맞으면 누가 내 행세 가능. → 새 키 쌍 생성 + 서버에 새 public key 재등록.

### "비밀번호보다 SSH 키가 약하다"

반대. SSH 키가 훨씬 강함. 2048비트+ RSA·ECC는 사실상 brute force 불가.

## 일상 비유: 우리 집 열쇠

- **Public Key (현관 자물쇠)**: 누구나 봐도 됨. 집 앞에 박혀 있음
- **Private Key (열쇠)**: 본인만 가짐. **잃어버리면 큰일** ⚠️
- 자물쇠 + 열쇠 한 쌍만 맞아야 문이 열림 = SSH 인증

## 실무 적용

- `ssh user@server.com` — 원격 서버 접속
- `git push` (GitHub) — SSH 키로 인증
- AWS EC2 인스턴스 관리
- Day 2 [[1주차-2일차-07-프로세스와-네트워크]] 챕터 마지막

## 관련 페이지

- [[SSL-TLS]] — 통신 암호화 (다른 목적)
- [[TCP-UDP]] — SSH는 TCP 위
- [[1주차-2일차-07-프로세스와-네트워크]] — Day 2 SSH 챕터

## 출처

- [[1주차-2일차-07-프로세스와-네트워크]] (Day 2)
- [[1주차-3일차-01-주요-프로토콜]] (Day 3 챕터 5)
