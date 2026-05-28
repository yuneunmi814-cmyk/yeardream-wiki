---
type: concept
aliases: [DNS, Domain Name System, 도메인 네임 시스템]
stage: 1
first_seen: 2026-05-28
last_updated: 2026-05-28
sources: 1
related: [[IP-주소]], [[TCP-UDP]], [[HTTP-프로토콜]]
---

# DNS (Domain Name System)

## 한 줄 정의

**도메인 이름 → IP 주소 변환 시스템**. 인터넷의 전화번호부. `www.google.com` → `142.250.207.78`.

## 핵심 아이디어

사람이 외우기 어려운 IP를 도메인으로 대체. 모든 웹 요청 직전에 일어남 (사용자는 인지 못 함).

### 조회 4단계

```
1. 브라우저:    "www.google.com IP 좀"
       ↓
2. Local DNS:   TLD(.com) 서버에 요청
       ↓
3. TLD 서버:    "Google authoritative DNS에 물어봐"
       ↓
4. Authoritative DNS: "142.250.207.78"
```

### 질의 방식 2종

- **재귀적 질의** (Recursive): Local DNS가 다 처리, 클라이언트는 답만 받음 (대부분)
- **반복적 질의** (Iterative): 클라이언트가 매번 다음 서버에 직접 물어봄

### 캐싱

각 단계에서 캐싱. 같은 도메인 또 요청하면 빠르게 응답.
- 브라우저 DNS 캐시
- OS DNS 캐시
- Local DNS 서버 캐시

## 왜 중요한가

- **모든 웹 통신의 첫 단계** — 브라우저 주소창 입력 → DNS → IP → 실제 요청
- **공용 DNS** — `1.1.1.1` (Cloudflare), `8.8.8.8` (Google) — ISP DNS보다 빠르거나 안전한 경우
- **DNS 레코드 타입** — A(IPv4), AAAA(IPv6), CNAME(별칭), MX(메일), TXT(인증)

## 자주 헷갈리는 것

### "DNS 바꾸면 인터넷 빨라진다"

일부 맞음. 공용 DNS가 ISP DNS보다 빠른 경우 있음. 단 광케이블 자체가 느리면 효과 없음.

### "DNS는 TCP?"

대부분 **UDP** (응답 짧고 빠름). 큰 응답(zone transfer 등)만 TCP.

### "도메인 IP 한 개?"

아님. 큰 사이트는 여러 IP 가짐 (로드밸런싱·CDN). DNS가 다양한 IP 중 하나 반환.

## 일상 비유: 카톡 친구 검색

`www.google.com` → IP 주소 = **친구 이름** → **전화번호**.

카톡에서 "은미" 검색 → 내부적으로 "은미의 user_id는 12345"로 변환. DNS가 도메인↔IP에 하는 일.

## 관련 페이지

- [[IP-주소]] — DNS가 변환해주는 결과물
- [[TCP-UDP]] — DNS는 UDP 사용
- [[HTTP-프로토콜]] — DNS 후 HTTP 요청

## 출처

- [[1주차-3일차-01-주요-프로토콜]] (챕터 1)
