---
type: concept
aliases: [Python, 파이썬, py]
stage: 1
first_seen: 2026-05-28
last_updated: 2026-05-28
sources: 1
related: [[변수]], [[자료형]], [[리스트]], [[조건문]]
---

# Python

## 한 줄 정의

**1991년 등장한 고급 인터프리터 언어**. 가독성·간결함 우선 철학. AI·데이터 분석·자동화의 사실상 표준.

## 핵심 아이디어

### 왜 Python인가

- **가독성**: 문법이 영어에 가까움. `if score >= 90 :` 그대로 읽힘
- **인터프리터**: 컴파일 없이 즉시 실행
- **거대 생태계**: 수십만 패키지 (PyPI)
- **AI/ML 표준**: TensorFlow·PyTorch·scikit-learn 다 Python

### 사용자(은미) 적용 영역

- **AI 분석가/서비스개발자 트랙** (Stage 3) 핵심 언어
- **데이터 분석**: pandas·numpy·matplotlib
- **AI Agent / LLM**: LangChain·Claude API
- **자동화**: 크롤링·스크래핑·반복 작업
- **프로젝트윤365**: 클라이언트 솔루션의 백엔드 가능성

→ Day 4 ~ Stage 4까지 거의 매일 손에 닿음.

### Python의 4가지 기본 자료형

| 자료형 | 영문 | 예시 | 변경 가능 |
|---|---|---|---|
| **숫자** | `int`·`float`·`complex` | `3`, `3.14`, `3+4j` | (불변) |
| **문자열** | `str` | `"Hello"`, `'안녕'` | ❌ |
| **리스트** | `list` | `[1, 2, 3]` | ✅ |
| **논리** | `bool` | `True`, `False` | (불변) |

→ Day 4 강의에서 4개 다 등장. 후속 강의에서 dict·tuple·set 추가 예상.

### Python의 특징적 문법

**들여쓰기 = 문법**:
```python
if x > 0 :
    print("양수")        # 들여쓰기로 if 블록 구분
print("끝")              # 들여쓰기 풀면 if 밖
```

→ SwiftUI·JavaScript처럼 `{}` 안 씀. 들여쓰기 안 맞으면 IndentationError.

**스네이크 표기법 (PEP 8 표준)**:
```python
user_name = "yoon"        # 스네이크 (Python 권장)
userName = "yoon"         # 카멜 (Python 비권장, Swift·JS 흔함)
```

## 왜 중요한가

- **사용자 학기 후반 주력 언어** — Stage 2~4에서 매일
- **AI 시대 lingua franca** — 거의 모든 AI 도구가 Python 우선
- **콘텐츠 자산** — yoon.ai.lab 시리즈 1순위 (Python 비전공자 친화 콘텐츠)

## 자주 헷갈리는 것

### Python vs JavaScript vs Swift (사용자 경험 기준)

| | Python | JavaScript | Swift |
|---|---|---|---|
| **변수 선언** | `x = 5` | `let x = 5` | `let x = 5` |
| **타입** | 동적 | 동적 | 정적 (명시) |
| **블록 구분** | 들여쓰기 | `{}` | `{}` |
| **표기법** | 스네이크 | 카멜 | 카멜 |
| **세미콜론** | ❌ | 선택 | ❌ |

### Python 2 vs Python 3

**Python 2는 2020년 EOL**. 신규 프로젝트는 무조건 **Python 3** (현재 3.12+).
강의·이 위키 모두 Python 3 기준.

### "Python은 느리다"

맞기도 틀리기도. 순수 Python은 C++보다 느림. 하지만:
- numpy·pandas는 C로 구현 → 빠름
- AI 라이브러리(PyTorch·TensorFlow)는 GPU 활용
- 실무 속도는 충분

## 개발 환경

### 사용자 추천 동선

- **Jupyter Notebook / Lab**: 데이터 분석·시각화 (셀 단위 실행)
- **VS Code + Python 확장**: 일반 코딩 (사용자 이미 Claude Code 일상)
- **Terminal `python3`**: 빠른 테스트

### Python 버전 확인

```bash
python3 --version          # macOS 기본
which python3              # 위치 확인
```

### 패키지 관리

```bash
pip install numpy          # 단일 설치
pip install -r requirements.txt   # 일괄 설치
```

## 코드/실습 예시 — Hello Python

```python
# 1. Hello World
print("Hello, Python!")

# 2. 변수·연산
name = "은미"
year = 2026
print(f"{name}, {year}")        # f-string (강의 미커버, 매우 유용)

# 3. 자료형 4종
print(type(3))                   # <class 'int'>
print(type(3.14))                # <class 'float'>
print(type("hi"))                # <class 'str'>
print(type([1, 2, 3]))           # <class 'list'>
print(type(True))                # <class 'bool'>

# 4. 조건문
score = 85
if score >= 90 :
    print("A")
elif score >= 75 :
    print("B")
else :
    print("C 이하")
```

## 콘텐츠 자산화

- **"비전공자가 Python을 시작하는 5분"** ⭐ — 4 자료형 + 변수 + print
- **"Python vs Swift vs JS 한 페이지 비교"** — 사용자 SwiftUI 경험 활용
- **"파이썬 입문자 흔한 실수 7가지"** — `=`/`==`, 인덱스 0, 들여쓰기, 형 변환, `is`/`==`, mutable default, `print`/`return`

## 관련 페이지

- [[변수]] — Python 코드의 기초
- [[자료형]] — 4종 기본 자료형
- [[리스트]] — 가변 시퀀스
- [[조건문]] — 분기 구조

## 출처

- [[1주차-4일차-00-기초-자료형]]
- [[1주차-4일차-01-조건문]]
- [[1주차-4일차-02-리스트]]
