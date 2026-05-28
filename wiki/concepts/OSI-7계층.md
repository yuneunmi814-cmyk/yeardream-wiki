---
type: concept
aliases: [OSI, OSI 7 Layer, Open System Interconnection, 7계층]
stage: 1
first_seen: 2026-05-28
last_updated: 2026-05-28
sources: 1
related: [[TCP-IP-4계층]], [[HTTP-프로토콜]], [[TCP-UDP]], [[IP-주소]]
---

# OSI 7계층

## 한 줄 정의

**네트워크 통신을 7개의 추상화 계층으로 나눈 국제 표준 모델** (1984년 ISO 제정). 실제 인터넷은 [[TCP-IP-4계층]]으로 동작하지만, 개념 이해는 OSI가 표준.

## 핵심 아이디어

각 계층은 **자기 위·아래만 신경 씀**. HTTP(7층)는 광섬유 케이블(1층)이 어떻게 동작하는지 몰라도 됨. **추상화 = 복잡성 관리**.

### 7계층 전체

| 계층 | 이름 | 데이터 단위 | 예시 프로토콜 | 역할 |
|---|---|---|---|---|
| **7** | 응용 (Application) | Data | HTTP·SMTP·SSH·DNS·FTP | 사용자 서비스 |
| **6** | 표현 (Presentation) | Data | JPEG·MPEG·ASCII | 인코딩·암호화 |
| **5** | 세션 (Session) | Data | SSL·TLS·NetBIOS | 세션 관리 |
| **4** | 전송 (Transport) | Segment | TCP·UDP | 종단 간 신뢰성 |
| **3** | 네트워크 (Network) | Packet | IP·ICMP·ARP | 경로 설정 (IP) |
| **2** | 데이터링크 (DataLink) | Frame | Ethernet·Wi-Fi | MAC 주소 |
| **1** | 물리 (Physical) | Bit | 전압·케이블 | 전기 신호 |

### 캡슐화 (Encapsulation)

위에서 아래로 가면서 각 계층이 자기 헤더를 붙임:

```
사용자: "Hello"

응용  → [HTTP Header][Hello]
전송  → [TCP H][HTTP H][Hello]
인터넷 → [IP H][TCP H][HTTP H][Hello]
링크  → [Frame H][IP H][TCP H][HTTP H][Hello][CRC]
물리  → 01010101...
```

수신 측은 **역캡슐화** — 양파 까듯이 헤더 떼면서 위 계층으로 전달.

## 왜 중요한가

- **강의 전체의 골격** — Day 3 4강이 모두 이 모델 기반
- **실무 디버깅** — 네트워크 문제 발생 시 "몇 층에서 끊겼나" 추적
- **프로토콜 이해** — 각 프로토콜이 몇 층인지 알면 동작 원리 추론

## 자주 헷갈리는 것

### OSI 7계층 vs [[TCP-IP-4계층]]

- OSI는 **이론·교육용**
- TCP/IP는 **실제 인터넷 구조** (실무)
- OSI 5·6·7 → TCP/IP 응용 1개로 통합
- OSI 1·2 → TCP/IP 네트워크 액세스 1개로 통합

### 암기 트릭

영어 첫글자: **A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing
(Application·Presentation·Session·Transport·Network·DataLink·Physical)

## 일상 비유: 택배 시스템

- **7층 (응용)** = 보내는 사람의 의도 ("선물 보낼래")
- **4층 (전송)** = 택배회사 박스 + 추적번호
- **3층 (네트워크)** = 주소지 라벨 + 허브 경로
- **2층 (데이터링크)** = 트럭 + 번호판
- **1층 (물리)** = 실제 도로

각 단계는 자기 일만 — 트럭 기사는 박스 안 내용 모름.

## 관련 페이지

- [[TCP-IP-4계층]] — 실용 버전
- [[HTTP-프로토콜]] — 7층 대표
- [[TCP-UDP]] — 4층 대표
- [[IP-주소]] — 3층 핵심
- [[SSL-TLS]] — 5·6층

## 출처

- [[1주차-3일차-00-네트워크-개요]] (챕터 7)
- [[1주차-3일차-02-인터넷과-HTTP]] (TCP/IP 비교)
