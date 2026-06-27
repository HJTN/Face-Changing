# Shift-Left Testing

## Overview
Shift-Left Testing은 테스트 활동을 개발 라이프사이클의 가능한 한 초기(왼쪽)로 이동시키는 원칙이다. 결함은 늦게 발견할수록 수정 비용이 기하급수적으로 증가한다.

## 결함 수정 비용 (상대적)

`
요구사항 단계: 1배
설계 단계:     5배
개발 단계:    10배
테스트 단계:  20배
프로덕션:    100배
`

## Shift-Left 실천 방법

### 1. 요구사항 단계에서 테스트
- QA가 요구사항 리뷰에 참여
- 모호한 요구사항 → 질문으로 명확화
- 수락 기준(Acceptance Criteria) 초기 정의

### 2. TDD (Test-Driven Development)
`
Red → Green → Refactor
실패하는 테스트 작성 → 테스트 통과하는 최소 코드 → 리팩터링
`

### 3. BDD (Behavior-Driven Development)
- Given-When-Then 시나리오로 비즈니스 요구사항 표현
`
Given 장바구니에 상품이 있을 때
When 주문 버튼을 클릭하면
Then 주문 확인 화면이 표시되어야 한다
`
- 개발자·QA·PM이 공통 언어 사용 (Cucumber, Behave)

### 4. CI에서 자동 테스트
- 코드 커밋 시마다 단위·통합 테스트 자동 실행
- 테스트 실패 시 머지 차단

## QA의 역할 변화
- 전통적: 완성된 소프트웨어 검수 ("Gate Keeper")
- 현대적: 개발 과정 전반에서 품질 문화 형성 ("Quality Coach")

## Related Terms
- [[Testing-Types]] — Shift-Left 원칙이 적용되는 테스트 유형들
- [[Test-Design-Techniques]] — 초기 단계에서 테스트를 설계하는 기법

## References
- [The Benefits of Shift-Left Testing — IBM](https://www.ibm.com/topics/shift-left-testing)
