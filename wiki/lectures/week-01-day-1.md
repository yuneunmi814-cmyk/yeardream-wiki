---
type: lecture
stage: 1
week: 1
day: 1
date: 2026-05-26
topics: [it-literacy, computer-basics, web-architecture, library-framework, database, rest-api, seo, version-control, cloud, saas, open-source]
sources:
  - raw/stage-1-foundations/[수업자료] 컴퓨터의 이해.pdf (22p)
  - raw/stage-1-foundations/00-it-literacy-computer-basics.md (Vision OCR 추출본)
  - raw/stage-1-foundations/[수업자료] 앱_웹 서비스를 위한 모든 것.pdf (38p)
  - raw/stage-1-foundations/01-app-web-service.md (Vision OCR 추출본)
  - raw/stage-1-foundations/[수업자료] 데이터베이스와 REST API.pdf (52p)
  - raw/stage-1-foundations/02-database-rest-api.md (Vision OCR 추출본)
  - raw/stage-1-foundations/[수업자료] 라이브러리와 프레임워크.pdf (21p)
  - raw/stage-1-foundations/03-libraries-frameworks.md (Vision OCR 추출본)
  - raw/stage-1-foundations/[수업자료] 검색엔진 최적화 SEO.pdf (34p)
  - raw/stage-1-foundations/04-seo-search-engine-optimization.md (Vision OCR 추출본)
  - raw/stage-1-foundations/[수업자료] 현업에서의 용어 노하우.pdf (32p)
  - raw/stage-1-foundations/05-industry-terms.md (Vision OCR 추출본)
---

# Week 1 Day 1 — IT 리터러시 입문 (6개 모듈)

> **분량 노트**: 6개 PDF 총 199p. "Day 1"이라 통칭하지만 실질적으로는 **Week 1 전체 자료 묶음**일 가능성이 높음. 실제 진도 매핑은 강의 진행 따라 갱신.
> **자료 형태 / OCR 진척 (100% 완료)**: 강의는 "개발자가 알려주는 IT의 A to Z" **6강 시리즈**.
> - 00 컴퓨터의 이해 ✅
> - 01 앱·웹 서비스 ✅
> - 02 DB·REST API ✅
> - 03 라이브러리·프레임워크 ✅
> - 04 SEO ✅
> - 05 현업 용어 노하우 ✅

## 핵심 takeaway 3개

1. **IT 리터러시 입문 = 사용자에겐 대부분 친숙**. SwiftUI 앱·Cloudflare 배포·Claude Code 일상 사용 배경상 Git/클라우드/SaaS/REST API/오픈소스 개념은 이미 작동 지식. **복습 + 빈틈 메우기 모드**가 시간 효율적.

2. **깊게 갈 만한 빈틈 4개**: REST API 설계 원칙(URL 패턴·메서드 의미), 라이브러리 vs 프레임워크의 IoC 원리, 오픈소스 라이선스(GPL/MIT/Apache 차이 — 클라이언트 솔루션 빌드 시 직접 영향), SEO 메타 태그·크롤링 합법성(콘텐츠 사업 직결).

3. **콘텐츠·사업 자산화 직결 토픽 다수**. SaaS 비즈니스 모델(Figma→Adobe 28조), 오픈소스 라이선스 함정, REST URL i18n 설계, SEO 메타 태그 — 모두 prompt.by.yoon / yoon.ai.lab 콘텐츠 후보.

## 새로 등장한 개념

- [[computer-basics]] — 0/1·기계어·프로그래밍 언어·Low/High level·OS·Front/Back-end 첫 등장
- [[app-web-services]] — WAS 구조·Endpoint·UI/UX·Grid System·디지털 명함 러닝 예제
- [[http-protocol]] — HTTP 분해·요청/응답·1요청 1응답 원칙·메서드 4종·JSON/XML
- [[synchronous-vs-asynchronous]] — 동기·비동기 (영업사원 비유)
- [[database-basics]] — CRUD·테이블·데이터 타입·물리/논리 삭제·DBMS·RDB vs NoSQL
- [[rest-api]] — REST API 정의·URI/URL·Open API (행정안전부 주소찾기)
- [[library-vs-framework]] — 빵틀 비유·웹의 역사(팀 버너스리·info.cern.ch)·Chart.js·Passport.js·Django·라이브러리 vs API
- [[seo]] — 검색엔진 최적화 (구글 3단계, 마케터 영역)
- [[crawling]] — 통째로 가져오기 (Googlebot, 다나와 HTML 예시, 한·미 법적 회색지대)
- [[parsing]] — 원하는 부분만 추출 (포켓몬 빵 비유, JSON·XML 분해)
- [[indexing]] — 색인, SEO의 직접 작업 대상 (`site:naver.com` 트릭)
- [[industry-terms]] — 현업 용어 묶음: Git / 플로우차트 / 오픈소스 / 클라우드 / SaaS

## 막혔던 부분 / 추가 학습 필요

- ⚠️ **PUT vs PATCH** — 강의는 "보안 이유로 PATCH 등장"이라 적었으나 사실은 **PUT=전체 교체 / PATCH=부분 수정**이 본질. [[http-protocol]] 보강 섹션 참조
- ⚠️ **IoC / Hollywood Principle** — 강의 본문엔 등장하지 않음. 빵틀 비유와 동일 개념이지만 AI Agent 프레임워크 선택 시 더 유용. [[library-vs-framework]] 보강 섹션 참조
- 오픈소스 라이선스 — OLIS(olis.or.kr)에서 GPL/MIT/Apache 비교 직접 해봐야 함 / 카카오톡 OSS Notice 실 예시 참고
- ✅ **6강 시리즈 OCR 100% 완료** (2026-05-27)

## 프로젝트윤365 / 인스타 콘텐츠 적용 아이디어

- **"오픈소스 라이선스 모르고 쓰면 큰일나는 케이스 3가지"** — 1인 컨설팅 클라이언트 솔루션 빌드 시 GPL 오염 위험. prompt.by.yoon 캐러셀.
- **"Figma는 왜 28조에 팔렸나 — SaaS 한 줄 설명"** — yoon.ai.lab 비즈니스 모델 시리즈.
- **"비전공자가 클라이언트한테 쇼핑몰 만들어준다면 — 플로우차트 1장"** — 강의에 등장한 쇼핑몰 로직(로그인→배송정보 자연 획득) 예시 그대로 활용. 프로젝트윤365 방법론 자산화.
- **"REST API URL로 본 글로벌 서비스 구조 (apple.com/kr vs /jp)"** — 인스타 캐러셀.
- **"디지털 명함 앱으로 보는 CRUD 한 장 설명"** — 강의 러닝 예제를 그대로 활용. POST 저장 → GET 조회 → PUT 수정 → DELETE 삭제.
- **"동기/비동기 영업사원 비유 1컷"** — 강의 비유 그대로.
- **"물리삭제 vs 논리삭제 — 매진 신발로 보기"** — 실무 결정 패턴 1컷.
- **"행정안전부 무료 Open API 모음"** — juso.go.kr 등. 비전공자가 바로 따라할 수 있는 콘텐츠.
- **"PUT vs PATCH — 비전공자 강의가 안 알려주는 진짜 차이"** — 정정 콘텐츠. 사용자 관점이 살아남.
- **"빵틀 = 프레임워크 — 비전공자가 들어도 안 까먹는 비유"** — 강의 핵심 비유 그대로 인스타 1컷.
- **"라이브러리 vs API 한 문장 차이"** — 네트워크 너머인지 여부.
- **"팀 버너스리가 웹을 무료로 공개 안 했다면?"** — yoon.ai.lab 비즈니스 모델 시리즈.
- **"카카오톡 OSS Notice 한 번도 안 본 사람 모여"** — 1인 컨설팅 클라이언트 빌드 시 OSS 표기 의무 강조.
- **"크롤링 어디까지 합법인가 — 한·미 판례로 보는 경계"** — 미국 2022 항소법원(공개데이터 합법) + 한국 여기어때 무죄(정보통신망법 48조). prompt.by.yoon 1순위 후보.
- **"검색엔진 3단계 한 장 설명 — 크롤링·색인·랭킹"** + **`site:내도메인` 트릭**. 비전공자 친화, yoon.ai.lab 후보.
- **"크롤링 안 쓰고 시장 데이터 뽑는 공식 채널 2곳"** — 구글 트렌드 + 네이버 데이터랩. 프로젝트윤365 자산.
- **포켓몬 빵 비유로 크롤링·파싱 한 번에** — 인스타 1컷 스토리.
- **클라우드 사용량 과금 vs 자체 서버 트레이드오프** — 1인 사업자가 인프라 의사결정할 때 쓰는 멘탈 모델로 자산화.
