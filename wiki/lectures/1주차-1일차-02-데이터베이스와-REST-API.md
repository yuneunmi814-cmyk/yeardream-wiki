---
type: lecture-textbook
stage: 1
week: 1
day: 1
chapter: 02
series: "개발자가 알려주는 IT의 A to Z"
date_rewritten: 2026-05-27
source: raw/stage-1-foundations/02-database-REST-API.md
source_pdf: raw/stage-1-foundations/[수업자료] 데이터베이스와 REST API.pdf
total_slides: 52
disclaimer: "✦ 마크는 LLM(Claude) 보강. 강의 영상으로 검증 필요."
---

# 02 / 데이터베이스와 REST API — 교재 버전

> **4섹션 구조** → [[_meta/학습-워크플로우]]

---

## 🚀 예습 (5분용)

### 한 줄 요약

**DB = 분류해서 저장한 데이터의 총합**. CRUD(저장·검색·수정·삭제)로 조작. **REST API = URI + HTTP 메서드로 DB를 외부에 노출**.

### 핵심 단어 5~7개

- [[데이터베이스-기초]] — DB 통합 노트
- [[REST-API]] — REST API 정의
- **CRUD** — Create·Read·Update·Delete
- **Query / SQL** — DB 명령어
- **Primary Key** — RDB 고유값
- **RDB vs NoSQL** — 양대 패러다임
- **Open API** — 외부 공개 API (행정안전부 주소찾기)

### 큰 그림

```
[클라이언트] → REST API → [Back-end] → SQL → [DB]
                                              ├─ RDB (MySQL·PostgreSQL)
                                              └─ NoSQL (MongoDB·Redis)
```

→ Day 1 시리즈 **3강 (가장 두꺼움, 52p)**. 2강의 "서버" 뒷편 본격 펼침.

---

## 📖 본문 (정독용)

### 챕터 1. DB 정의 + 일상 (슬라이드 1~4)

**키워드 (강의 본문)**:
- DB = **기록하고 조합하는 모든 데이터들의 총합**
- 일상: 통장 입·출금 기록, 도서관 도서 검색
- 은행앱 결제내역 조회 4단계: 앱 열기 → 서버 접속 → DB 검색 → 결과 확인
- 도서관 관리 정보: 보유 여부·책 정보·대여 중인지·누가 대여·반납 예정

✦ **강의자 풀이 추정**
DB의 본질 = **기록 + 조합**. 단순 저장과 차이.

사용자(은미)가 매일 쓰는 모든 앱(카톡·인스타·쿠팡·이어드림 플랫폼) 뒤엔 다 DB. 의식 못 할 뿐. 위키 자체도 일종의 개인 DB.

**🎯 핵심 메시지**: DB = 기록 + 조합 가능한 데이터 창고. 모든 디지털 서비스의 뒷편.

---

### 챕터 2. CRUD + 테이블 (슬라이드 5~9)

**키워드 (강의 본문)**:
- **CRUD**: 저장 → 검색 → 수정 → 삭제 (Create·Read·Update·Delete)
- **테이블 (상품)**: 상품번호·상품종류·가격
- **테이블 (회원)**: 회원번호·이름·아이디·주소
- **테이블 본질**: "데이터를 분류하기 좋게 저장. 사람이 분류하기 쉽게가 중요"

✦ **강의자 풀이 추정**
DB의 4기능 = **CRUD**. [[lectures/1주차-1일차-01-앱-웹-서비스|2강 HTTP 메서드]]와 1:1 매핑:

| HTTP | CRUD | SQL |
|------|------|-----|
| POST | Create | INSERT |
| GET | Read | SELECT |
| PUT/PATCH | Update | UPDATE |
| DELETE | Delete | DELETE |

**테이블** = 엑셀 시트와 유사. 행(row) + 열(column).
- 엑셀: 사람이 보고 클릭
- DB: 프로그램이 SQL로 조작 → 수만 건도 빠름

**🎯 핵심 메시지**: DB 4기능 = CRUD. HTTP 메서드와 1:1 매핑. 테이블이 기본 단위.

⚠️ **흔한 오해**: "DB = 엑셀이랑 똑같다" → 데이터 구조는 비슷하지만 다중 사용자·트랜잭션·인덱싱·관계 등 엑셀에 없는 강력한 기능 다수.

---

### 챕터 3. Query + 검색 + 정렬 (슬라이드 10~15)

**키워드 (강의 본문)**:
- 신발 매진 케이스: 단순 가격·종류 컬럼만으론 부족. **매진 여부 컬럼 필요**
- **검색 (Select)**: 신상품·핫딜·가격 낮은순·추천상품 다 검색 쿼리
- **Query** = DB 명령어
- **정렬**: 특정 값 기준 정렬 (등록일자 최신순 등)

✦ **강의자 풀이 추정**
SQL 예시:
```sql
-- 매진 안 된 상품만
SELECT * FROM products WHERE 매진 = false;

-- 최근 7일 신상품 최신순 20개
SELECT * FROM products
WHERE created_at > NOW() - 7 days
ORDER BY created_at DESC LIMIT 20;
```

쇼핑몰의 모든 메뉴(신상품·핫딜·가격순) = 같은 테이블에 조건만 다른 쿼리.

**🎯 핵심 메시지**: Query = DB 명령어 (SQL). 검색의 모든 메뉴가 사실 쿼리 조건의 차이.

⚠️ **흔한 오해**: "SQL은 옛 기술" → 50년 된 SQL이 여전히 모든 백엔드의 90%. AI 분석가 트랙은 SQL 거의 필수.

---

### 챕터 4. 데이터 타입 + 수정 (슬라이드 16~19)

**키워드 (강의 본문)**:

| 분류 | 타입 |
|------|------|
| 숫자 | Int·float·double |
| 문자 | String |
| 문자 | Boolean (참/거짓) |
| 시간 | Time·Datetime |

- 신발 매진 = `매진(Boolean)` 컬럼 추가

✦ **강의자 풀이 추정**
컬럼마다 타입 미리 지정. 잘못 지정하면 데이터 손실·계산 오류.

일반적 매핑:
- 회원번호·가격(원) → Int
- 이름·주소·전화번호 → String (전화번호도 String!)
- 매진 여부·활성 계정 → Boolean
- 가입일·결제 시각 → Datetime

⚠️ **흔한 오해 1**: "전화번호는 Int" → String 표준. 010이 Int면 사라짐.

⚠️ **흔한 오해 2**: "Boolean = 문자" → 강의 분류엔 문자지만 일반적으로 **별도 분류**.

⚠️ **흔한 오해 3**: "가격은 Float" → Int(원 단위). 부동소수점 오차 때문에 돈 계산엔 Float 피함.

**🎯 핵심 메시지**: 컬럼 타입 미리 지정 필수. 전화번호=String, 돈=Int.

---

### 챕터 5. 물리삭제 vs 논리삭제 ⭐ (슬라이드 20~22)

**키워드 (강의 본문)**:
- **물리 삭제**: DB에서 row 자체 제거
- **논리 삭제**: 데이터 안 지우고 `매진=True` 플래그 표시

✦ **강의자 풀이 추정**
**실무 핵심 패턴**:

| 방식 | 장점 | 단점 |
|------|------|------|
| 물리 삭제 | 깨끗 | 복구 불가, 통계 불가, 법적 의무 위반 가능 |
| 논리 삭제 | 복구·통계·법적 보존 | DB 크기 증가, 모든 쿼리에 `WHERE is_deleted=false` 추가 |

→ **현대 서비스 표준 = 논리 삭제** + 일정 기간(30일·1년) 후 백그라운드 물리 삭제.

실무 컬럼명: `deleted_at(datetime)` 또는 `is_deleted(boolean)`.

**🎯 핵심 메시지**: 물리 삭제 = 즉시 영구 / 논리 삭제 = 플래그만. 현대 표준은 논리 삭제.

⚠️ **흔한 오해**: "DELETE 누르면 무조건 영구 삭제" → 대부분 논리 삭제. 카톡 "모든 대화상대에서 삭제"도 일정 기간 카카오 서버에 남음.

📎 자세히: [[데이터베이스-기초]]

---

### 챕터 6. 서버 오류 3종 (슬라이드 23~25)

**키워드 (강의 본문)**:
"서버가 터졌어요" 3종:
1. **트래픽 과부하** — 다수 동시 접속
2. **백엔드 코드의 버그**
3. **DB 접속 오류** — 서버 살아있지만 DB 연결 실패

✦ **강의자 풀이 추정**
사용자에겐 다 같이 "안 됨"이지만 백엔드 진단·대응 완전 다름:

- **트래픽 과부하** → 수평 확장(Auto Scaling)·캐싱
- **코드 버그** → 롤백·핫픽스
- **DB 오류** → DB 이중화(Master/Replica)

→ 사용자 1인 사업이라 인프라 관리는 클라우드 자동화 활용.

**🎯 핵심 메시지**: 서버 오류 3종 = 트래픽·코드·DB. 진단·대응 다 다름.

📎 자세히: [[현업-용어]] 클라우드 섹션

---

### 챕터 7. API + REST URL 패턴 (슬라이드 26~31)

**키워드 (강의 본문)**:
- **API** = 프로그램끼리 대화. **A**pplication **P**rogramming **I**nterface
- 재정의: "**네트워크를 통한 기능 호출**"
- **로그인 API**: `POST shoppingmall.com/login` (ID/PW)
- **GET API 국가별**: `apple.com/kr/`·`apple.com/jp/` (같은 패턴 변수만)

✦ **강의자 풀이 추정**
**API = 사람용 UI의 프로그램 버전**. UI는 사람용 입구, API는 다른 프로그램용 입구.

같은 카페에 두 입구:
- 카운터 (UI) — 사람이 직원에게 주문
- 사이렌 오더 (API) — 앱이 카페 시스템에 주문

**RESTful URL 패턴**:
```
https://www.apple.com/{국가}/
→ 한 줄 코드가 전 세계 모든 나라 페이지 처리
```

→ 일상 사례 — `instagram.com/{username}`. 같은 패턴, username만 다름.

**🎯 핵심 메시지**: REST API = URI + HTTP 메서드. 같은 패턴 + 변수 = 글로벌 확장.

📎 자세히: [[REST-API]], [[라이브러리-vs-프레임워크]] (라이브러리 vs API)

---

### 챕터 8. Open API + DBMS + RDB vs NoSQL (슬라이드 32~36)

**키워드 (강의 본문)**:
- **Open API 사례**: 행정안전부 주소찾기 (juso.go.kr). 데이터 포맷 JSON+XML, **무료**, 활용 7544건
- **DBMS** = Database Management System. **MySQL·MariaDB·PostgreSQL·Oracle**
- **RDB** (관계형): Primary Key로 연결. B신발 구매한 A고객 예시
- **NoSQL**: 기록 단순, 대용량 처리에 유리

✦ **강의자 풀이 추정**
**Open API** = 외부 공개. 정부·기업이 제공.
- 행정안전부 주소찾기
- 공공데이터포털 (data.go.kr) 수천 개
- 기상청 날씨 / 국세청 사업자등록번호

→ 서비스 만들 때 **크롤링 대신 합법적 데이터 채널**.

**DBMS 4종**:
- MySQL (Oracle 소유, 가장 흔함)
- MariaDB (MySQL fork, 무료 보장)
- PostgreSQL (강력, AI·복잡 쿼리, 최근 인기)
- Oracle (대기업·금융)

**RDB vs NoSQL**:

| | RDB | NoSQL |
|--|-----|-------|
| 구조 | 테이블·관계 | Document·KV·Graph 등 |
| Query | SQL | 자체 문법 |
| 적합 | 회원·결제 (정합성) | 피드·캐시·로그 (대용량) |
| 예 | MySQL·PostgreSQL | MongoDB·Redis·Cassandra |

→ 현대 서비스는 **둘 다 사용**. 카톡: 회원=RDB, 메시지=NoSQL, 캐시=Redis.

**🎯 핵심 메시지**: Open API = 합법 데이터 채널. RDB vs NoSQL은 공존(역할 분담).

⚠️ **흔한 오해 1**: "NoSQL = SQL 없음" → "Not Only SQL" 약자. SQL 외 다양한 방법도 쓴다는 의미.

⚠️ **흔한 오해 2**: "NoSQL이 RDB를 대체할 것" → 2010년대 초 유행. 현재 공존.

📎 자세히: [[데이터베이스-기초]], [[REST-API]] Open API 섹션

---

## 🔄 복습 (빈칸 회상용)

### 빈칸 질문 5개

1. CRUD 4기능을 영문 풀어쓰면: C=___, R=___, U=___, D=___
2. 물리 삭제 vs 논리 삭제 — 현대 서비스 표준은? 이유 3개는?
3. 전화번호를 Int로 저장하면 안 되는 이유는?
4. RDB 4대 DBMS는? (4개)
5. apple.com/kr·/jp 같은 URL 패턴이 보여주는 설계 원칙은? (RESTful의 ___)

### 헷갈렸던 것 ❓

빈칸 질문 다 모르겠음

---

## 💡 일상 비유

### 비유 1 — 카카오톡 친구 관리 (CRUD)

- Create: 친구 추가 (전화번호 등록)
- Read: 친구 목록·프로필 보기
- Update: 즐겨찾기 토글, 메모 수정
- Delete: 친구 차단·삭제

모든 디지털 행동 = CRUD의 조합.

### 비유 2 — 카카오톡 메시지 삭제 (물리/논리)

"모든 대화상대에게서 삭제" 누르면 채팅창에서 사라짐 = 사용자 입장 영구.
실제 카카오 서버엔 일정 기간 보관(논리 삭제) → 그 후 진짜 삭제.

---

## 검증 체크리스트

- [ ] DB vs DBMS 구분 — 강의에서 명확히 다룸?
- [ ] PostgreSQL 인기 상승 — 강의 등장?
- [ ] 로그인 토큰(JWT) — 강의에서 명시?
- [ ] NoSQL 4유형 (Document·KV·Wide-column·Graph) — 강의 깊이?
- [ ] Open API 호출 횟수 제한 — 강의 다룸?

---

## 이해 체크 (은미, 2026-05-29)

- [x] **PUT 멱등성** — 여러 번 해도 결과 같음. PUT·GET·DELETE 멱등 / POST 비멱등. **자동문 vs 결제 버튼** 비유
- [x] **헤더 vs 바디** — 헤더=메타 라벨, 바디=실제 데이터. **인스타 DM의 라벨 vs 본문**
- [x] **REST API** — HTTP 4메서드 + URL로 만든 깔끔한 통로 (`GET /users/123`)
- [x] **CRUD ↔ HTTP** — POST=C / GET=R / PUT·PATCH=U / DELETE=D
- [x] **PUT vs PATCH** — PUT 전체 교체, PATCH 부분 수정
- [x] **Query / SQL** — DB에 던지는 명령. SQL=RDB 전용. SELECT·INSERT·UPDATE·DELETE 4개 = CRUD
- [x] **RDB = 표(엑셀) 형태 DB** — PostgreSQL·MySQL·Oracle·SQLite
- [x] **Primary Key = 주민등록번호** — 유일 식별, NULL ❌
- [x] **RDB vs NoSQL** — 엑셀(정확) vs 메모장(자유). **실무는 양쪽 다 씀**
- [x] **NoSQL 4유형** — Document(MongoDB)·KV(Redis)·Wide-Column(Cassandra)·Graph(Neo4j)
- [x] **Open API** — 누구나 쓰는 공개 API. 행정안전부·카카오 지도·Claude API. **API Key로 추적·과금**
- [x] **Rate Limit** — Open API 호출 횟수 제한. 초과 시 **HTTP 429**
- [x] **DB vs DBMS** — DB=데이터 자체 / DBMS=관리 SW. 실무 거의 혼용
- [x] **PostgreSQL 인기 상승 이유** — MySQL Oracle 인수 후 PostgreSQL로 이동
- [x] **캐싱** → [[캐시]] 페이지 참조 (책상 메모지 비유)
- [x] **JWT** → [[JWT]] 페이지 참조 (영화관 손목 밴드 비유 + JSON Web Token, aaa.bbb.ccc 3파트)
- [x] **DBMS** = **Da**ta**B**ase **M**anagement **S**ystem (데이터베이스 관리 시스템)
- [x] **Supabase = PostgreSQL 기반 RDB**. SQL·테이블 작업 가능
- [x] **PK = 고유번호 = 식별번호** (주민등록번호 비유)
- [x] **추천 조합** = Python+FastAPI+**Supabase**+SwiftUI/React (Cloudflare 배포)
- [x] **Open API Rate Limit 관리 6전략**: 빈도↓·캐싱·배치·백오프·유료·모니터링
- [ ] (아직 막힌 거 있으면 여기 추가)

---

## 다음 강의

- 인덱스: [[lectures/1주차-1일차]]
- 이전: [[lectures/1주차-1일차-01-앱-웹-서비스]]
- 다음: [[lectures/1주차-1일차-03-라이브러리와-프레임워크]]
