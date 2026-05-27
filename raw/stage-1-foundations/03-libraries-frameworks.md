---
source_type: lecture_material
source_file: 수업자료_라이브러리와_프레임워크.pdf
extracted_by: Claude (vision OCR)
extraction_date: 2026-05-27
stage: 1
chapter: 03
total_slides: 21
note: |
  원본 "PDF"는 슬라이드를 JPEG로 변환해 zip으로 묶은 아카이브로, 텍스트 레이어가
  없어 일반 PDF 텍스트 추출이 불가. 이 파일은 슬라이드 이미지를 Claude vision으로
  직접 읽어 텍스트로 옮긴 추출본. 시리즈 "00 개발자가 알려주는 IT의 A to Z"의 04강.
---

# 04 / 라이브러리와 프레임워크

## 목차

프레임워크와 라이브러리

1. 웹의 역사
2. 라이브러리
3. 프레임워크

---

## 01. 웹의 역사

### 도입

> **웹의 역사를 통해 프로그래밍의 발전 과정을 알아보자**

### 웹의 기본 구조

```
[다양한 웹 브라우저들]  ⇄  html 로 정보를 주고 받음  ⇄  [웹서버]
(Chrome, Firefox, Brave 등)

[PC, 컴퓨터]                                          [서버 컴퓨터]
```

### 세계 최초의 웹사이트 — info.cern.ch

http://info.cern.ch — home of the first website

세계 최초의 웹사이트 info.cern.ch 를 복원한 모습
http://info.cern.ch/hypertext/WWW/TheProject.html

### 팀 버너스리 경 (Tim Berners-Lee)

- 영국 물리학자
- 현재의 www(월드 와이드 웹) 의 창시자
- Html, css, http 통신, url 등 현대 웹의 초석이 되는 기술을 개발
- 연구자들 끼리 자료 공유을 위해 만든 웹을 대중에게 무료로 공개
- 인류에 대한 공헌을 인정받아 기사작위, 서울 평화상 수상

### 웹의 시각적 변화

- **1998.12.12 네이버** — 초기 검색 중심의 단순한 레이아웃
- **2008.12.12 네이버** — 뉴스, 카페, 블로그, 이미지 등 복합 포털로 진화

### 점점 커지고 복잡해지는 Web

- 점점 커져가고 복잡해져 가는 웹 프로그래밍
- 반복적으로 자주 사용되는 코드들
- 협업으로 진행되는 많은 프로젝트들
- 구조화된 체계의 필요성

→ 라이브러리와 프레임워크가 등장한 배경

---

## 02. 라이브러리

### 라이브러리 정의

> **반복해서 자주 사용하는 코드 모음**
>
> **일종의 코드로 이루어진 도구 모음**

### 라이브러리의 등장 배경과 특징

(pub.dev — Flutter Favorites 화면, Build amazing things 캡처와 함께 설명)

- 코드의 역사가 쌓이며, 자주 사용되게 되는 기능들이 발생
- 자주 사용하는 기능들을 함수로 묶어서, 선언하여 사용하는 형태로 변경
- 오픈소스의 영역에서도 활발하게 생산 공유
- 다른 말로 **package** 로 불리기도 함

### 라이브러리 예시 1 — Chart.js

```
< Bar chart >       const config = {
                      type: 'bar',
                      data: data,
                      options: {
                        scales: {
                          y: {
                            beginAtZero: true
                          }
                        }
                      }
                    };
                    const data = {
                      labels: labels,
                      datasets: [{
                        label: 'My First Dataset',
                        data: [65, 59, 80, 81, 56, 55, 40],
                        backgroundColor: [
                          'rgba(255, 99, 132, 0.2)',
                          'rgba(255, 159, 64, 0.2)',
                          'rgba(255, 205, 86, 0.2)',
                          'rgba(75, 192, 192, 0.2)',
                          'rgba(54, 162, 235, 0.2)',
                          'rgba(153, 102, 255, 0.2)',
                          'rgba(201, 203, 207, 0.2)'
                        ]
                      }]
                    };
```

> **색과 데이터 수치만 입력한 간단한 선언으로, 복잡한 Chart 를 쉽게 그려낼 수 있다.**

### 라이브러리 예시 2 — passport.js

**Passport** — Simple, unobtrusive authentication for Node.js
> *Passport is authentication middleware for Node.js. Extremely flexible and modular, Passport can be unobtrusively dropped in to any Express-based web application. A comprehensive set of strategies support authentication using a username and password, Facebook, Twitter, and more.*

- Passport.js
- 로그인, 회원가입 관리 구현을 쉽게 도와주는 라이브러리
- 우리가 아는 소셜 로그인도 쉽게 구현할 수 있도록 도와준다.
- Kakao, naver 용 passport 도 존재한다.

### 라이브러리 — 사용 이유

- 검증된 라이브러리를 잘 활용하는 것도 개발자의 능력
- 데이터 처리 관련해서는 따로 학습을 해야 할 정도로 큰 라이브러리들도 존재
- 적절하지 못한 사용으로 성능을 저하시키는 경우도 있음

### 라이브러리 — 한 문장 요약

> **프로젝트의 생산성 향상과 효율성 증진을 위해 라이브러리를 활용한다.**

### 라이브러리 vs API

(벤다이어그램으로 표현)

- **공통점**: 재사용이 가능한 코드의 반복적 활용
- **차이점**: API 는 네트워크, 통신을 통해 기능을 제공

---

## 03. 프레임워크

### 프레임워크 정의

> **프로그램을 효율적으로 짜기 위한**
>
> **Frame : 어떤 형태의 틀을 가진 형태**

### 프레임워크의 특징 — 빵틀 비유

(빵틀 사진과 함께 설명)

- 빵 모양을 만들기 위한 빵틀 처럼 코드를 작성하기 위한 구조 제시
- 공통된 규칙을 활용해야 하기 때문에 협업에 매우 유리하며, 코드 로직 자체에 집중
- 언어별로 다양한 프레임워크가 존재하며, 각각 제공하는 도구나 툴이 다름

### 프레임워크 예시 — Django

(Django Admin 페이지 캡처와 함께)

- Django 라는 프레임워크
- 파이썬 기반의 웹 페이지를 작성할때 사용
- 보통은 관리 페이지를 따로 작성해야하지만, 상당한 수준의 관리자 페이지를 Django는 제공
- 제작의 부담을 덜어준다.

---

*© Elice. All Rights Reserved (원본 출처 표기)*
