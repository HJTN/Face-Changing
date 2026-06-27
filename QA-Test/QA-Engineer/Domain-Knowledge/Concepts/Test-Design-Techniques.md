# Test Design Techniques

## Overview
테스트 설계 기법은 모든 케이스를 전수 테스트할 수 없을 때 최소한의 테스트로 최대한의 결함을 발견하기 위한 체계적 방법이다.

## 명세 기반 기법 (블랙박스)

### 동등 분할 (Equivalence Partitioning)
- 입력 값을 동등한 그룹으로 분할해 각 그룹에서 대표값 하나만 테스트
`
나이 입력: 0-17 (미성년), 18-64 (성인), 65+ (시니어)
→ 각 그룹 1개씩: 10, 30, 70 테스트
`

### 경계값 분석 (Boundary Value Analysis)
- 경계에서 버그가 가장 많이 발생
`
0-100 유효 범위:
경계값: -1, 0, 1, 99, 100, 101 테스트
`

### 결정 테이블 (Decision Table)
- 여러 조건의 조합에 따른 동작을 표로 정리
`
| 로그인 | 관리자 | 권한 있음 | 결과 |
|--------|--------|-----------|------|
|   O    |   O    |     O     | 허용 |
|   O    |   O    |     X     | 거부 |
|   O    |   X    |     O     | 허용 |
|   X    |   -    |     -     | 거부 |
`

### 상태 전이 테스트 (State Transition)
- 시스템 상태 변화를 다이어그램으로 표현하고 전이 경로 테스트
- 사용: 주문 상태, 사용자 계정 상태, 게임 레벨

## 구조 기반 기법 (화이트박스)

### 커버리지 기준
- **Statement Coverage**: 모든 코드 라인 실행
- **Branch Coverage**: 모든 if/else 분기 실행 (더 강함)
- **Path Coverage**: 모든 실행 경로 (조합 폭발로 비현실적)

## Related Terms
- [[Testing-Types]] — 각 기법이 적용되는 테스트 유형
- [[Shift-Left-Testing]] — 설계 기법을 초기 단계에 적용

## References
- [ISTQB — Test Design Techniques](https://www.istqb.org/)
