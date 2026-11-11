---
name: round
description: 라운드 단위 개발을 진행하거나 마무리할 때 사용한다. spec → plan → 구현 → review 순서와 라운드 종료 조건을 안내한다.
---

# 라운드 단위 개발

## 문서 구조
- `docs/ROADMAP.md`: 라운드 계획. 지금 어느 라운드인지 여기서 확인한다.
- `docs/SSOT.md`: 진실의 원천. 지금 서비스의 API, 데이터 모델, 규칙.
- `docs/roundNN/`: 라운드마다 `spec.md` → `plan.md` → `review.md`.

## 진행 순서
1. ROADMAP에서 이번 라운드를 확인하고 `docs/roundNN/spec.md`를 쓴다.
2. `plan.md`에 구현 계획을 쓴다.
3. 구현한다. CLAUDE.md의 코드 규칙을 따른다.
4. verifier 에이전트로 검증하고, 문제를 고친다.
5. cleaner 에이전트로 정리하고, 결과를 `review.md`에 적는다.

## Hook에 막혔을 때
- 다른 명령으로 우회하지 말고 멈춰서 사람에게 보고한다.

## 라운드 종료 조건
하나라도 안 되면 끝났다고 보고하지 않는다.
1. `docs/roundNN/spec.md` · `plan.md` · `review.md`가 지금 코드와 맞는다.
2. `docs/SSOT.md`를 지금 코드 기준으로 고쳤다.
3. cleaner 에이전트로 죽은 코드를 정리했고, 결과를 `review.md`에 적었다.
4. 프로젝트의 테스트 · 린트 명령이 통과한다.
5. `docs/ROADMAP.md`에서 이번 라운드를 완료로 표시했다.
