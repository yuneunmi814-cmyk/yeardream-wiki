---
type: external-resource
category: textbook
title: "Operating System Concepts, 10th Edition"
authors: [Abraham Silberschatz, Peter Baer Galvin, Greg Gagne]
year: 2018
publisher: Wiley
pages: 1278
size_mb: 31
language: English
nickname: "공룡책"
source_pdf: raw/external/operating-system-concepts-10th.pdf
ingested: 2026-05-27
related: [[운영체제]], [[1주차-2일차]]
---

# 📚 공룡책 — Operating System Concepts 10판

> CS 학부 OS 과목의 사실상 글로벌 표준 교과서. 옛 표지에 공룡 그림이 있어서 "공룡책(Dinosaur Book)"이라 불림.

---

## 책 메타

| 항목 | 값 |
|------|-----|
| **저자** | Abraham Silberschatz · Peter Baer Galvin · Greg Gagne |
| **판수** | 10th Edition |
| **출간** | 2018, Wiley |
| **분량** | 1,278 페이지 |
| **파일** | 31MB, 영문 PDF |
| **위치** | `raw/external/operating-system-concepts-10th.pdf` |

---

## 학습 다짐 ⭐

**강의자 지시: "운영체제 PDF 3번 읽기" = 이 책 1278p 전체를 학기 동안 3번**

→ 학기 6개월 (2026.05 ~ 2026.11)에 점진적으로:
- **1차** (예습): 강의 들으면서 해당 챕터만 가볍게
- **2차** (정독): 전체 통독, 빈칸 회상
- **3차** (복습): 시험·과제 직전 + 부족한 부분 집중

→ [[학습-워크플로우]] 사이클 + 챕터 단위 분할 필요.

→ 진척 추적: [[1주차-2일차-라이브-노트]] 액션 아이템.

---

## 전체 구조 (10부, 21챕터)

### PART 1 — OVERVIEW
- **Ch.1 Introduction**
- **Ch.2 Operating-System Structures**

### PART 2 — PROCESS MANAGEMENT
- **Ch.3 Processes**
- **Ch.4 Threads & Concurrency**
- **Ch.5 CPU Scheduling**

### PART 3 — PROCESS SYNCHRONIZATION
- **Ch.6 Synchronization Tools**
- **Ch.7 Synchronization Examples**
- **Ch.8 Deadlocks**

### PART 4 — MEMORY MANAGEMENT
- **Ch.9 Main Memory**
- **Ch.10 Virtual Memory**

### PART 5 — STORAGE MANAGEMENT
- **Ch.11 Mass-Storage Structure**
- **Ch.12 I/O Systems**

### PART 6 — FILE SYSTEM
- **Ch.13 File-System Interface**
- **Ch.14 File-System Implementation**
- **Ch.15 File-System Internals**

### PART 7 — SECURITY AND PROTECTION
- **Ch.16 Security**
- **Ch.17 Protection**

### PART 8 — ADVANCED TOPICS
- **Ch.18 Virtual Machines**
- **Ch.19 Networks and Distributed Systems**

### PART 9 — CASE STUDIES
- **Ch.20 The Linux System** ⭐
- **Ch.21 Windows**

### PART 10 — APPENDICES
- (BSD UNIX, FreeBSD, Mach 등 부록)

---

## 이어드림 Day 2 강의 ↔ 공룡책 매핑 ⭐

강의 8강이 이 책의 압축판. 같이 공부하면 강의=얕은 버전, 책=깊은 버전.

| 이어드림 강의 | 공룡책 챕터 | 비고 |
|---|---|---|
| [[1주차-2일차-00-운영체제-소개]] | **Ch.1** Introduction + Ch.2 OS Structures | 1:1 |
| [[1주차-2일차-01-프로세스]] | **Ch.3** Processes + Ch.4 Threads + Ch.5 CPU Scheduling + Ch.6~7 Synchronization + Ch.8 Deadlocks | 5챕터 압축 |
| [[1주차-2일차-02-메모리]] | **Ch.9** Main Memory + **Ch.10** Virtual Memory | 2챕터 |
| [[1주차-2일차-03-파일-시스템]] | Ch.11 Mass-Storage + Ch.12 I/O + **Ch.13~15** File System | 5챕터 압축 |
| [[1주차-2일차-04-리눅스-입문]] | **Ch.20** The Linux System | Case study |
| [[1주차-2일차-05-리눅스-파일-시스템]] | Ch.20 + Ch.13~15 | 교차 |
| [[1주차-2일차-06-리눅스-명령어]] | Ch.20 | Linux 챕터 |
| [[1주차-2일차-07-프로세스와-네트워크]] | Ch.20 + **Ch.19** Networks | 네트워크 추가 |

---

## 강의가 안 다루는 책의 깊은 영역 ⭐

→ 자기 학습으로 보강할 가치 큼:

### 1. Ch.6~7 Synchronization (동기화)
- **강의**: IPC 3종(메시지 큐·공유 메모리·소켓)만 간략
- **책**: mutex·semaphore·monitor·atomic operation·deadlock 회피 알고리즘 깊이
- **활용**: AI Agent 멀티 스레드·동시성 처리 시 필수. Stage 3 이후 매일 마주침

### 2. Ch.10 Virtual Memory (가상 메모리)
- **강의**: "안심 번호" 비유만
- **책**: 페이지 교체 알고리즘 (LRU·FIFO·Clock·Working Set)·TLB·Demand Paging 깊이
- **활용**: 큰 데이터 처리·캐시 시스템 설계

### 3. Ch.16~17 Security & Protection (보안)
- **강의**: ❌ 없음
- **책**: OS 보안 모델·접근 제어·암호화·인증
- **활용**: 보안·접근 제어 깊이 학습 (Stage 4 프로젝트 보안 설계 토대)

### 4. Ch.18 Virtual Machines / Ch.19 Networks and Distributed Systems
- **강의**: 컨테이너화 한 슬라이드만
- **책**: VM·하이퍼바이저·분산 합의 (Paxos·Raft) 깊이
- **활용**: AI 시대 핵심. 클라우드·MLOps·분산 학습

---

## 학습 활용 동선

### 1차 — 예습 + 강의 따라가기 (Day 2 시작 직후)
- 강의 Day 2 진도에 맞춰 해당 챕터만 가볍게
- 영문이라 부담 = 핵심 그림·표·정의만 훑기
- 강의 본문과 동일 개념은 강의 교재 신뢰, 책은 보강용

### 2차 — 정독 + 빈칸 회상 (강의 진도 후)
- Ch.1~10까지 PART 1~4 (OS 핵심)
- 챕터 끝 Exercise는 안 풀어도 OK. 본문 이해가 우선
- 강의가 안 다룬 깊은 영역(Synchronization·Virtual Memory)에 집중

### 3차 — 시험·과제 직전 + 깊은 영역 (학기 후반)
- Ch.11~21 (스토리지·보안·VM·분산·Linux 사례)
- AI 분석가·서비스개발자 트랙(Stage 3) 진입 전 보강

---

## ⚠️ 주의

### 영문 부담

1278p 영문책. 한 번에 다 못 읽음. 합리적:
- 챕터별 분할 (한 챕터 30~60p)
- 핵심 그림·표·요약 위주
- 영어 어려우면 Claude한테 챕터 요약·일상 비유 요청 ([[학습-워크플로우]] 4단계)

### Edition 차이

10판(2018)은 멀티코어·클라우드·모바일 강조. 9판(2012) 이하는 좀 옛. **10판이 현재 표준**이라 다행.

### 다른 OS 책

- **Tanenbaum의 "Modern Operating Systems"** — 공룡책의 라이벌. Tanenbaum이 더 짧고 명료, Silberschatz가 더 포괄적
- **"Operating Systems: Three Easy Pieces" (OSTEP)** — 무료 PDF, 모던하고 친근. 보조 자료로 추천

---

## 관련 페이지

- [[운영체제]] — OS 통합 노트
- [[1주차-2일차]] — Day 2 8강 인덱스
- [[1주차-2일차-라이브-노트]] — 강의자 "3번 읽기" 지시 메모
- [[학습-워크플로우]] — 학습 사이클

---

## 출처

- `raw/external/operating-system-concepts-10th.pdf` (1278p, 영문, 31MB)
- Publisher: Wiley, 2018
- ISBN: 978-1-119-32091-3 (10th edition)
