# Activity Log

위키의 모든 활동(ingest, query, lint, synthesis)이 시간순으로 기록되는 로그.

포맷:
```
## [YYYY-MM-DD] {ingest|query|lint|synthesis} | 짧은 제목
- 영향받은 파일: ...
- 메모: ...
```

`grep "^## \[" wiki/log.md | tail -10` 으로 최근 활동 확인 가능.

---

## [2026-05-27] ingest | 이어드림스쿨 모집공고 PDF (중기부 공고 제2026-244호)
- 영향받은 파일: wiki/curriculum.md, wiki/program-overview.md (신규), wiki/index.md, wiki/log.md
- 메모: 위키 첫 ingest. 권역 4개 확정(강원=원주/경상=대구/전라=전주/충청=천안), OT 5/21~22 1박2일, 단계별 시작일 추산 기재(공고에 명시 X), 상시 프로그램 4→6개 확장(채용연계/부트캠프 교류 추가), 인센티브 3종(교육지원비/자기계발 포상금/국외연수) 신규 기록. 사업자 등록 상태(프로젝트윤365) 신청제외 5번 조항 해당 → 결정 보류 상태로 program-overview에 트래킹. AI 실무 심화과정은 별도 메모로만 보관(기본과정 확정).

## [2026-05-27] update | 본인 정보 확정 (수도권 대면 + 사업 지속)
- 영향받은 파일: wiki/curriculum.md, wiki/program-overview.md, wiki/log.md
- 메모: 본인 권역=수도권(서울) 전 대면, 오렌지타워 한강. 프로젝트윤365는 계속 운영 결정(휴·폐업 X). 사업이 시간 자유로워 인턴십 등 부가 프로그램 참여 옵션 열어둠. 공고 5번 조항 충돌 소지는 사실 기록만, 판단·권유 보류.

## [2026-05-27] ingest | 이어드림스쿨 6기 개강 안내 공지 (2026.05.22 발송)
- 영향받은 파일: wiki/curriculum.md, wiki/program-overview.md, wiki/log.md
- 메모: 6기 확정(PDF 1~5기까지만 언급), **본 개강 5/26(화)** (기존 추산 5/22에서 4일 미뤄짐), 운영시간 9~17시(PDF 9~18시에서 변경), 일일 일정 6교시 추가, 좌석 2개월 고정=분반=Stage 3 트랙 분기 시점 7월 말경 마일스톤 명시, 디스코드 닉네임 양식(`이름/기본/서울`), 지문 등록, 수강 홈페이지 매일 9시 콘텐츠 오픈, 운영진 02-6954-1105~6. 첫날 액션 4개 program-overview "본인 적용"에 체크리스트화. 공지 원문 → raw/external/6th-cohort-kickoff.md 저장.

## [2026-05-27] ingest | 이어드림스쿨 6기 교육생 혜택·지원 안내 (2026.05.26 공지)
- 영향받은 파일: raw/external/6th-cohort-benefits.md (신규), wiki/program-overview.md, wiki/curriculum.md, wiki/log.md
- 메모: PDF 인센티브 3종(교육지원비/자기계발 포상금/국외연수)이 6기 확정 금액·기준으로 구체화. **수료 기준 출석 80%+이수 80% 신규 명시**. 테스트 4주 단위 4회·2회씩 합산(1~5등 50만/6~15등 30만/16~25등 10만), 산업특화 팀 1~3등 100/70/50만, 캐글 메달 50만, 인턴십 월 50만×2개월, 조기 취·창업 50만+12/31까지 수강, 해외연수 12월 초 미국·싱가포르·일본 1개국, 우수 졸업생 부상=에어팟 맥스. 수도권 본인 출석일 15,000원(월말 집계 익월 초 입금). 본인 적용은 사실 메모만 — 조기 취·창업 적용 요건은 프로젝트윤365 운영 상태와 맞물려 운영진 추가 확인 필요로 표기.

## [2026-05-27] ingest | Week 1 Day 1 — IT 리터러시 6모듈 (PDF 6종, 199p)
- 영향받은 파일: wiki/lectures/week-01-day-1.md (신규), wiki/concepts/{computer-basics,app-web-services,library-vs-framework,rest-api,seo,industry-terms}.md (6개 신규), wiki/index.md, wiki/curriculum.md, wiki/log.md
- 메모: 첫 강의 ingest. PDF 6개 = 컴퓨터의 이해(22p)/앱웹서비스(38p)/라이브러리·프레임워크(21p)/DB·REST API(52p)/SEO(34p)/현업용어(32p). PDF 6개 중 5개는 이미지 슬라이드라 텍스트 추출 실패 → 강의 노트로 보충 필요로 표기. "현업 용어 노하우"만 텍스트 잘 잡힘(Git/플로우차트/오픈소스/클라우드/SaaS 5개 하위). 사용자 배경(SwiftUI/Cloudflare/Claude Code)상 대부분 친숙한 IT 리터러시 입문 → 복습 + 빈틈(REST 설계·IoC·오픈소스 라이선스·SEO 메타) 메우기 모드 권장. 인스타 콘텐츠 후보 6개 lecture에 명시. industry-terms는 5개 하위주제 묶음, 후속 강의에서 Git·클라우드 등 재등장 시 별도 페이지로 분리 누적 예정.

## [2026-05-27] ingest | SEO Vision OCR 추출본 (5번째 강의자료 상세화) + raw 경로 정정
- 영향받은 파일: wiki/concepts/seo.md (풀 업데이트), wiki/concepts/{crawling,parsing,indexing}.md (3개 신규), wiki/lectures/week-01-day-1.md, wiki/concepts/{computer-basics,app-web-services,library-vs-framework,rest-api,industry-terms}.md (source 경로 정정), wiki/index.md, wiki/curriculum.md, wiki/log.md
- 메모: 사용자가 SEO 슬라이드를 Vision OCR로 텍스트 추출한 마크다운(seo-search-engine-optimization.md, 295줄) ingest. 이전 stub이었던 seo.md를 풀 알맹이로 교체 + 사용자 제안대로 crawling/parsing/indexing 3개 별도 페이지로 분리. 강의 척추 = 구글 검색엔진 3단계(크롤링→색인→검색결과). 핵심: SEO=색인 단계 노출 효율 작업(마케터 영역), 크롤링 합법·불법 회색지대(美 2022 항소법원 합법 + 韓 여기어때 무죄·정보통신망법 48조), 공식 우회=구글 트렌드·네이버 데이터랩, 파싱 포켓몬 빵 비유, site:naver.com 색인 확인 트릭, 다나와 HTML 가격 추출 예시. 부수 처리: raw 폴더 구조 변경 발견 — week-01/ 폴더가 사라지고 stage-1-foundations/ 직속으로 PDF 이동됨 → 기존 lecture·concepts 6개의 source 경로 일괄 정정.

## [2026-05-27] ingest | 컴퓨터의 이해 + 앱·웹 서비스 + DB·REST API Vision OCR 추출본 (3개)
- 영향받은 파일: wiki/concepts/{computer-basics,app-web-services,rest-api}.md (풀 업데이트), wiki/concepts/{http-protocol,synchronous-vs-asynchronous,database-basics}.md (3개 신규), wiki/concepts/{seo,crawling,parsing,indexing}.md (raw 파일명 prefix 정정), wiki/lectures/week-01-day-1.md, wiki/index.md, wiki/curriculum.md, wiki/log.md
- 메모: 사용자가 명시한 00·01 외에 02도 함께 발견 → 일괄 ingest. 강의는 "개발자가 알려주는 IT의 A to Z" 6강 시리즈로 정렬 확인(00 컴퓨터/01 앱웹/02 DB·REST/03 라이브러리(OCR 대기)/04 SEO/05 현업용어). 디지털 명함 앱이 시리즈 러닝 예제로 일관 사용됨. 신규 멘탈 모델 3개: HTTP 메서드↔CRUD 매핑·동기/비동기 영업사원 비유·물리삭제 vs 논리삭제. ⚠️ 강의 본문 부정확 진술 2개 발견(PUT vs PATCH 보안 이슈 설명, URI vs URL 정의) → http-protocol·rest-api 페이지에 "강의 본문 + 보강" 형식으로 정정 표기. raw 04-SEO prefix 갱신에 따라 seo/crawling/parsing/indexing source 경로도 일괄 정정. 콘텐츠 후보 다수 추가(명함 앱 CRUD, 영업사원 비유, 물리/논리 삭제, juso.go.kr Open API, PUT vs PATCH 정정). 03 라이브러리·프레임워크 OCR 대기.

## [2026-05-27] ingest | 03 라이브러리·프레임워크 + 05 현업용어 Vision OCR 추출본 (6강 시리즈 OCR 100%)
- 영향받은 파일: wiki/concepts/library-vs-framework.md (풀 업데이트), wiki/concepts/industry-terms.md (누적), wiki/lectures/week-01-day-1.md, wiki/curriculum.md, wiki/log.md
- 메모: library-vs-framework는 stub → 알맹이 풀 교체. 강의 핵심 비유 = **빵틀(프레임워크) vs 도구 모음(라이브러리)**. 라이브러리 = package, 예시 Chart.js·Passport.js / 프레임워크 예시 Django. ⚠️ 강의 본문엔 **IoC·Hollywood Principle 단어 자체가 없음** — "강의 본문 + 보강" 형식으로 분리 표기(PUT vs PATCH 패턴 동일). 신규 발견: **팀 버너스리·info.cern.ch·웹의 역사**가 라이브러리 자료 도입부에 등장 → 1998 vs 2008 네이버 비교로 웹 복잡화 = 라이브러리·프레임워크 등장 배경 설명 흐름. 라이브러리 vs API 비교(공통=재사용, 차이=네트워크 너머)도 강의 명시. industry-terms는 sources 1→2 누적: 카카오톡 v9.9.0 업데이트 노트(VC), 카카오톡 OSS Notice Apache License 2.0 예시(오픈소스 라이선스 실 사례), AWS/Azure/Google Cloud 3대 명시, 미스터리 박스 분기 플로우차트(쇼핑몰 외 추가 예시) 추가. 콘텐츠 후보: 빵틀 비유, 라이브러리 vs API 한 줄, 팀 버너스리 무료 공개 결정, 카카오톡 OSS Notice. 6강 시리즈 OCR 100% 완료 — Week 1 Day 1 알맹이 확보 단계 종료.
