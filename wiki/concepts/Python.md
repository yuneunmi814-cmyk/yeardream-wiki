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

---

## 🙋 은미 정수 (2026-05-29) — "AI 모델 = Python으로 만든다"의 정확한 뜻

**오해**: ChatGPT·Gemini·Claude **전체가** Python으로 만든 것? → **부분 정답**.

**정확히**:

```
[모델 학습]          → Python (PyTorch·TensorFlow) ⭐  ← 여기가 핵심
       ↓
[모델 파일 .bin]
       ↓
[실제 서비스 (서빙)]  → C++·CUDA로 빠르게 최적화
[API 서버]           → Python·Go·Rust 섞임
[웹 인터페이스]       → TypeScript·React (chat.openai.com)
```

**핵심**: **AI 연구·개발자가 매일 손에 쓰는 언어 = Python**. 모델 자체는 Python으로 태어남. 그래서 Stage 3 AI 다루려면 Python 필수.

**비유**: 요리(모델 학습) = 셰프 한식 손맛 / 배달(서비스) = 배달앱·오토바이 다양. 손맛은 한식이지 배달까지 한식 아님.

### AI 도구 묶음 — PyTorch · TensorFlow · `.bin` · CUDA

| 도구 | 발음 | 정체 |
|---|---|---|
| **PyTorch** | 파이토치 | Meta 2016. AI 모델 만드는 Python 라이브러리. GPT·Claude 다 이거 |
| **TensorFlow** | 텐서플로우 | Google 2015. 산업·배포 친화. Google 제품들 |
| **`.bin` 파일** | 바이너리 | 학습 결과(가중치·파라미터) 저장 파일. 0/1로 된 모델 본체 |
| **CUDA** | 쿠다 | NVIDIA GPU 프로그래밍 도구. GPU = CPU보다 수천 배 빠른 병렬 처리 |
| **C++** | 씨플플 | 1985 등장. 속도 최우선 언어. AI 추론·게임·OS |

### AI 흐름 — 어디서 어떤 언어?

```
[모델 설계·학습]    → Python + PyTorch + CUDA (GPU)
        ↓
[모델 파일 .bin]    → 학습된 가중치 저장
        ↓
[실제 답변 (추론)]  → C++ + CUDA (속도 최우선)
[API 서버]         → Python (FastAPI) + Go·Rust (트래픽 보조)
[웹 인터페이스]     → TypeScript + React
```

**왜 Python 안 쓰고 C++?**: Python = 사람 친화(빠른 개발), C++ = 컴퓨터 친화(빠른 실행). **학습엔 Python, 추론엔 C++**.

---

## 🙋 은미 정수 2 (2026-05-29) — pip + python-dotenv

### pip = Python의 apt (배달 드론) ⭐

| | 리눅스 | Python |
|---|---|---|
| 패키지 매니저 | apt (가족 비유: 심부름꾼 삼촌) | **pip** |
| 저장소 | (Ubuntu 저장소) | **PyPI** (파이파이) |
| 명령어 | `sudo apt install ...` | `pip install ...` |

→ apt와 pip은 같은 패턴. 단 pip은 sudo 거의 필요 없음 (가상환경 안에서).

### python-dotenv — `.env` 파일 자동 로딩

⚠️ **흔한 오해**: `.env.py` 파일 ❌. **python-dotenv는 라이브러리 이름**.

**왜 필요?**:
- 터미널 `export 변수=값`은 휘발성 (터미널 끄면 사라짐)
- `.env` 파일에 영구 저장하고 Python이 자동 읽게 하기

**사용법** (2줄로 끝):

```python
import os
from dotenv import load_dotenv

load_dotenv()                              # .env 파일 자동 로딩

my_password = os.environ.get("DB_PASSWORD") # 비밀번호 꺼내기
```

**설치**:
```bash
pip install python-dotenv
```

**비유** (Gemini): 카톡 "자동 로그인 정보 저장" 체크 → 앱이 켜질 때 자동으로 정보 읽음.

### 미션 2와의 연결 ⭐

너 [[미션-2-크롤링-자동화]] 도전 시 첫날 만나는 패턴:

```python
# crawl.py
from dotenv import load_dotenv
import os

load_dotenv()                              # GitHub 토큰·API 키 로딩
github_token = os.environ.get("GITHUB_TOKEN")

# 크롤링 + git push
```

```
.env 파일 (gitignore에 등록):
GITHUB_TOKEN=ghp_xxxxx
API_KEY=xxxxx
```

→ **cron + python-dotenv** = 자동화 표준 패턴.

### 콘텐츠 자산화

- **"Python 첫날 배우는 보안 패턴 1개"** — yoon.ai.lab
- **"apt vs pip 5초 비교"** — prompt.by.yoon

### uv — pip 차세대 (2026-05-29 강사 추천)

**uv** = Astral 회사 (Ruff 만든 곳)의 Python 도구. **pip의 10~100배 빠름**.

**왜?**:
- 의존성 관리 자동
- 가상환경 자동 생성
- 강사 PRISMA-KB도 `uv run python ...` 사용 = 현업 진입

**설치** (강사 명령어):
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
uv --version
```

`curl` 옵션 풀이:
- `-L` 리다이렉트 따라가기
- `-s` silent
- `-S` 에러는 표시
- `-f` 서버 에러 시 종료
- `| sh` 다운로드한 스크립트 즉시 실행

### 개발환경 세팅 체크리스트 (2026-05-29 강사 권고)

> "개발환경 세팅 많이 해보는 거 추천. 잘 연습 많이하기"

| # | 항목 | 도구 |
|---|---|---|
| 1 | 터미널 | zsh + oh-my-zsh |
| 2 | 에디터 | VS Code / Cursor |
| 3 | 언어 | Python 3.12 / Node.js |
| 4 | **패키지 매니저** | **uv** ⭐ / pip / npm |
| 5 | 가상환경 | uv / venv |
| 6 | 버전 관리 | Git + SSH 키 |
| 7 | **컨테이너** | **Docker Desktop** ⭐ |
| 8 | DB | PostgreSQL·Redis (Docker) |
| 9 | 클라우드 CLI | AWS·GCP·Cloudflare |
| 10 | AI 도구 | Claude Code / Copilot / Cursor |

→ **Stage 2 진입 첫 도전 = Python 가상환경 + Jupyter 셋업**.

### class (클래스) 미리보기 — "프로그래밍 90% 이해" (2026-05-29 강사)

> "class를 이해하면 프로그래밍의 90%는 이해한 거다"

**한 줄**: 데이터(변수) + 행동(함수)를 묶은 **설계도**.

**붕어빵 비유**:
```python
# class = 붕어빵 틀 (설계도)
class 붕어빵:
    팥 = "들어있음"
    
    def 굽기(self):
        return "익었다"

# 객체(인스턴스) = 틀로 찍은 진짜 붕어빵
내붕어빵 = 붕어빵()
print(내붕어빵.팥)    # "들어있음"
내붕어빵.굽기()       # "익었다"
```

**왜 90%?**:
- 모던 코드 거의 다 **객체 지향(OOP)** 기반
- Python·Swift·Java·JS 다 class
- AI 모델 = PyTorch `nn.Module` class
- Django·FastAPI = class 기반

→ **Stage 1 지금**: 단어 인식만. **Stage 2 본격 학습**.

### 자주 만나는 에러 2개 (Day 4 실습 기준, 2026-05-29)

#### TypeError — 인자 개수 안 맞음

```python
print(type(3,14))    # ❌ type()은 1 또는 3개
# TypeError: type() takes 1 or 3 arguments

print(type(3.14))    # ✅ 점으로 (3.14는 1개 인자)
```

**원인**: `.` 와 `,` 헷갈림. 한국어 키보드에서 자주.

#### SyntaxError: unterminated string literal — 따옴표 짝 안 맞음

```python
print('작은따옴표, 큰따옴표")    # ❌ 시작 '·끝 " 짝 ❌
# SyntaxError: unterminated string literal
```

**원인**: 시작 따옴표와 끝 따옴표가 다름.

**해결**:
```python
print('작은따옴표, 큰따옴표')     # ✅ 둘 다 '
print("작은따옴표, 큰따옴표")     # ✅ 둘 다 "
```

### 강사 핵심 메시지 — "에러는 늘 나는 거" ⭐⭐

> "고수는 에러를 안 내는 게 아니라 에러나면 fix it 하면 돼"
> "에러는 그냥 늘 나는 거야"

→ 5/29 오전 "고연차 vs 저연차" 메시지와 동일.
→ **에러 = 일상**. 너 매일 정수 추출 = 에러 fix 훈련 ⭐.

### .venv = 가상환경 (Virtual Environment)

**왜?**: 프로젝트 A=Django 3, 프로젝트 B=Django 5 동시 ❌ → **프로젝트별 격리 환경**.

**비유**: 이삿짐 박스처럼 프로젝트별 분리.

```bash
uv venv                        # .venv 폴더 생성
source .venv/bin/activate       # 활성화 (Mac)
deactivate                      # 비활성화

uv run python script.py         # 자동 활성화 + 실행 (1줄)
```

### pyproject.toml — 프로젝트 표준 설정 파일

**역할**: 메타데이터 + **의존성 목록** + 빌드 설정.

```toml
[project]
name = "my-project"
requires-python = ">=3.12"
dependencies = [
    "python-dotenv>=1.0.0",
    "beautifulsoup4>=4.12.0",
]
```

→ uv·pip·poetry 다 읽음. **2021 표준**.

### uv 명령어 — 강사 PRISMA-KB 패턴

```bash
uv sync                            # 의존성 일괄 설치 (이삿짐 박스 풀기)
uv add 라이브러리                   # 라이브러리 추가
uv run python script.py            # 자동 활성화 + 실행
uv run pytest                      # 테스트도 자동 환경
```

**실전 흐름**:
```bash
git clone https://github.com/dschloe/PRISMA-KB
cd PRISMA-KB
uv sync                            # ← 환경 완성
uv run python scripts/compile.py   # ← 즉시 실행
```

### JupyterLab — Jupyter Notebook 진화형

| | Notebook | **JupyterLab** ⭐ |
|---|---|---|
| 등장 | 2014 | 2018 |
| UI | 단일 노트북 | 다중 탭·파일·터미널 통합 |
| 느낌 | 메모장 | **미니 VS Code** |
| 포트 | 8888 | 8888 (같음) |

```bash
uv add jupyterlab
jupyter lab          # http://localhost:8888/lab
```

→ Stage 2 진입 시 **JupyterLab 권장** (Notebook 대신).

### 공식 문서 공부법 ⭐⭐ (강사 강조)

> **공식 = 개발자가 직접 쓴 진짜 정답. AI보다 정확. 항상 최신.**

**언어별 공식** (너 시급도 순):

| 도구 | URL | 한국어 |
|---|---|---|
| **Python** | docs.python.org/ko ⭐ | ✅ |
| **Anthropic Claude API** | docs.anthropic.com ⭐ | ❌ |
| **MDN Web Docs** | developer.mozilla.org | ✅ |
| **FastAPI** | fastapi.tiangolo.com ⭐ | ❌ |
| **Docker** | docs.docker.com | ❌ |
| **Kubernetes** | kubernetes.io/docs | ✅ |
| **Ubuntu Server** | ubuntu.com/server/docs | 일부 |

**4단계 공부법**:
1. **튜토리얼** ("Getting Started")
2. **레퍼런스** (모르는 함수 검색, **AI 묻기 전 공식 먼저**)
3. **가이드** ("Best Practices")
4. **깊이** (GitHub 소스·이슈)

**비유**:
- AI = 통역사 (편함, 100% 정확 X)
- 공식 문서 = 원어민 강의 (시간 들지만 정확)

**은미 추천 순서**:
```
지금       → docs.python.org/ko (Stage 1·2 매일)
지금       → docs.anthropic.com (Claude 일상)
Stage 2~3  → fastapi.tiangolo.com
Stage 3·4  → docker / kubernetes 공식
```

---

## 관련 페이지

- [[변수]] — Python 코드의 기초
- [[자료형]] — 4종 기본 자료형
- [[리스트]] — 가변 시퀀스
- [[조건문]] — 분기 구조

## 출처

- [[1주차-4일차-00-기초-자료형]]
- [[1주차-4일차-01-조건문]]
- [[1주차-4일차-02-리스트]]
