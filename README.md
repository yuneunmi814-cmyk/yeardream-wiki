# yeardream-wiki

이어드림스쿨 AI 실무 기본과정 (2026.05 ~ 2026.11) 학습 위키.

LLM이 작성·유지하는 마크다운 기반 개인 지식 베이스. 강의 자료, 과제, 외부 자료를 ingest 하면 개념/도구/강의/프로젝트 페이지로 자동 정리되고 누적됨.

## 사용 방법

1. Obsidian으로 이 폴더를 vault로 열기
2. Claude Code를 이 폴더에서 실행 (`claude` 명령)
3. `raw/` 하위에 자료 떨어뜨리고 "ingest" 요청
4. `wiki/` 안에서 위키 페이지 확인

운영 규칙은 [`CLAUDE.md`](./CLAUDE.md) 참고.

## 구조

- `raw/` — 원본 자료 (LLM은 읽기만)
- `wiki/` — LLM이 작성·관리하는 위키 페이지
- `CLAUDE.md` — LLM 운영 규칙 (스키마)
