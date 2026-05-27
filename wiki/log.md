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
