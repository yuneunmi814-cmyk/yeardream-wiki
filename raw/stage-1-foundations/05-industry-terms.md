---
source_type: lecture_material
source_file: 수업자료_현업에서의_용어_노하우.pdf
extracted_by: Claude (vision OCR)
extraction_date: 2026-05-27
stage: 1
chapter: 05
total_slides: 32
note: |
  원본 "PDF"는 슬라이드를 JPEG로 변환해 zip으로 묶은 아카이브로, 텍스트 레이어가
  없어 일반 PDF 텍스트 추출이 불가. 이 파일은 슬라이드 이미지를 Claude vision으로
  직접 읽어 텍스트로 옮긴 추출본. 시리즈 "00 개발자가 알려주는 IT의 A to Z"의 06강(마지막).
---

# 06 / 현업에서의 용어 노하우

## 목차

현업에서의 알쓸신잡

1. Version Control
2. 기획과 플로우 차트
3. 오픈소스
4. 클라우드
5. SaaS

---

## 01. Version Control

### Version Control 정의

> **전체 프로젝트를 개발, 출시 단계의 코드를 관리하는 방법**

### Version Control 개념

개발, 출시, 버그 수정 등의 모든 프로젝트 관리 과정

**카카오톡 공개 업데이트 노트 — 예시**

```
[v9.9.0]
• 오픈채팅 홈 아이콘 추가
  : 채팅목록 상단에 추가된 아이콘으로 오픈채팅 홈에 바로 진입할 수 있어요.
• 내프로필 QR 개선
  : 친구추가 화면에서 내프로필 QR을 확인하고 카카오프렌즈로 꾸며보세요.
• 오픈채팅 송금 기능 추가
  : 오픈채팅방에서 상대방의 프로필을 선택해 송금할 수 있어요.
• 이미지 편집기 개선
  : 편집 도구에서 화살표를 그리거나 글자를 입력할 수 있어요.
  : 친구에게 받은 사진을 편집 후 공유해보세요.
* 보이스룸 공감 아이템 추가
  : 공감 아이템을 설정하여 감정을 표현해보세요.
• 이모티콘 즐겨찾기 개수 확대
  : 최대 120개의 이모티콘을 즐겨찾기 할 수 있어요.
```

- 출시나 개발을 할 때 어떠한 기능들이 있는지 관리
- 문제가 발생시 이전 내용으로 돌리기도 함

### Version Control - Git

(git 공식 사이트 캡처: "fast-version-control")
> *Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency. Git is easy to learn and has a tiny footprint with lightning fast performance. It outclasses SCM tools like Subversion, CVS, Perforce, and ClearCase with features like cheap local branching, convenient staging areas, and multiple workflows.*

> **다양한 버전 컨트롤 프로그램이 존재했지만 현재는 Git이 천하통일을 했다고 해도 무방하다**

### Git 을 대표하는 두 서비스

Git을 편리하게 서버 입장에서 사용 편리하게 해주는 두 개의 대표적인 서비스

| 서비스 | 특징 |
|---|---|
| **GitHub** | 마이크로소프트에 8조원에 매각 |
| **Bitbucket** | Bitbucket의 회사 ATLASSIAN 의 공동창업자는 호주 부호 6위에 오름 |

### Version Control - Git 의 효용

관리를 버전 별로 나누어 테스트 작업, 출시버전, 제작 버전 등으로 편리하게 나누어 작업 가능

- 리눅스 OS를 만든 리누스 토발즈 제작
- 누가 코드를 작성했는지 확인 가능
- 협업에 매우 용이

### Version Control — 설탕 비유

```
[설탕 1스푼] → [설탕 2스푼] → [설탕 3스푼]
```

> **언제든 설탕 1스푼 내지는 2, 3스푼으로 이동할 수 있다**

---

## 02. 기획과 플로우 차트

### 기획과 플로우 차트 정의

> **어떤 서비스를 만들 것인지 핵심적인 흐름을 데이터와 함께 보여주는 것**

### 쇼핑몰의 핵심 로직

```
[상품 페이지 접속] → [상품 구매] → [상품 배송]
```

**쇼핑몰의 가장 핵심이 될 만한 프로세스**

### 핵심 로직의 빈 곳 발견 — 배송 정보는 어떻게?

- 위 핵심 로직에서의 배송 정보 누락
- 3단계 프로세스에선 정보 획득 과정이 없음
- 로그인 혹은 회원 가입을 통한 회원정보 획득

### 보완된 플로우

```
[로그인] → [상품페이지] → [상품 구매] → [배송]
```

**로그인 과정을 추가해, 배송에 필요한 정보를 자연스럽게 획득**

### 각 단계에 필요한 데이터/기능

| 단계 | 필요한 것 |
|---|---|
| **로그인** | 회원의 이름 / 전화번호 / 주소지 정보 획득 |
| **구매** | 간편결제 (카카오페이, 네이버페이) / 카드결제 / 무통장 입금 등 |
| **배송** | 배송사 선정 및 배송과정을 제공해 주는 API 레퍼런스 체크 |

### 프로토타입 이후의 작업

- 기획팀의 상세기획 시작
- 개발자는 관련 레퍼런스, 활용할 라이브러리, API 등을 점검

### 간략한 플로우 차트 샘플 (미스터리 박스 예시)

```
[결제] → [미스터리 박스 구매완료] ──미스터리 박스 오픈──→ [상품당첨] ┬─→ [배송]
                  │                                              │
                  ↓ (확률)                                        └─→ [환불] → [상품 가격 포인트로 환불]
              [100% 환불]                                           ↓
                  │                                          [마이페이지]
                  └────── 마이페이지 정보저장 ────────────────→     ↑
                                                                  │
                                                          마이페이지 정보저장
```

여러 경로(당첨/환불/100% 환불)가 모두 **마이페이지**로 정보 저장됨.

---

## 03. 오픈소스

### 오픈소스 정의

> **프로젝트 전체 코드가 공개되어 활용할 수 있는 코드 소스**

### 오픈소스 — 특징과 라이선스

(open source 로고, Firefox, OpenOffice, blender, php, Java, MySQL, debian, WordPress, Apache, Ubuntu, Linux 등 대표 OSS 로고 모음)

- 프로젝트 전체 내용이 공유 됨.
- 많은 사람들의 기여로 프로젝트들이 진행 유지
- 무료로 사용 가능함
- 전부 무료 X. 엄연히 라이선스로 관리되어 지고 있다.

> **메모 — OLIS**: 오픈소스SW 라이선스 종합정보시스템
> https://www.olis.or.kr/license/compareGuide.do

### 오픈소스 — 운영체제 예시

**안드로이드 스마트폰도 오픈소스 운영체제**

### 오픈소스 — 라이선스 기재 의무

> **라이선스 규칙에 따라 기재하고 있는 것**

- 우리가 사용하는 어플리케이션의 메뉴들에 자신들이 사용하고 있는 오픈소스 소프트웨어들을 기재하고 있음

예시: 카카오톡 안드로이드 OSS Notice 화면
- abseil-cpp (https://github.com/abseil/abseil-cpp, Apache License 2.0)
- android - platform - cts (Apache License 2.0)
- android - platform - frameworks - base (Apache License 2.0)
- android - platform - frameworks - ex (Apache License 2.0)
- android - platform - frameworks - multidex (Apache License 2.0)
- android - platform - frameworks - opt - calendar
- ... (계속)

---

## 04. 클라우드

### 클라우드 정의

> **실물 서버 없이, 인터넷을 통해 활용하는 서버와 소프트웨어**

### 기존 서버의 단점들

- 용량 확장 및 운영의 유연성 부족
- 한번 구축한 인프라를 계속 유지하는 유지비용 발생
- 계산이 틀렸을 때의 추가비용 위험성

### 기존 서버 — 트래픽 증가 시나리오

```
[서버 트래픽 증가] → [서버 컴퓨터 증설] → [증설된 서버 유지]
```

→ **증설된 서버로 유지비용 증가**

### 클라우드 — 장점

- 유연하게 셋업 가능한 구조
- 사용한 만큼 비용을 지불하는 구조
- 365일 정상적으로 가동해야 하는 운영 부담 감소

### 클라우드 — 트래픽 변동 시나리오

```
[서버 트래픽 증가] → [서버 컴퓨터 증설] → [서버 트래픽 감소] → [증설된 컴퓨터 폐기]
```

→ **서버 증설과 폐기를 관리 부담 없이 클릭 몇 번만으로 해결 가능**

### 다양한 클라우드 서비스들

- **AWS** (Amazon Web Services)
- **Microsoft Azure**
- **Google Cloud**

---

## 05. SaaS

### SaaS — 정의

> **Software as a Service**
>
> **클라우드 기반의 소프트웨어 서비스**

### SaaS — 특징

- 파일 공유와 같은 공유의 유연성
- 소프트웨어 설치와 같은 과정을 거치지 않고 바로 사용
- Adobe 의 Figma 28조원 인수 등 SaaS 의 위력과 가능성확인
- 계속해서 확장되고 있는 주요 서비스

---

*© Elice. All Rights Reserved (원본 출처 표기)*
