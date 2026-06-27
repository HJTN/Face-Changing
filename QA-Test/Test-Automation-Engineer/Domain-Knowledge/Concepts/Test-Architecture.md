# Test Architecture

## Overview
테스트 아키텍처는 자동화 테스트 시스템의 구조·패턴·원칙을 정의한다. 단순 스크립트 작성이 아닌, 유지보수 가능하고 확장 가능한 테스트 시스템을 설계하는 것이다.

## 테스트 자동화 아키텍처 원칙

### 1. 레이어드 아키텍처

`
[테스트 레이어]        — 시나리오·검증 로직
       ↓
[비즈니스 레이어]       — 비즈니스 언어 추상화 (create_user, place_order)
       ↓
[Page Object 레이어]   — UI 요소 추상화 (click_login_button)
       ↓
[드라이버/클라이언트]   — Playwright, requests, DB 연결
`

### 2. Screenplay Pattern (SOLID 적용)
- 역할(Actor) → 능력(Ability) → 태스크(Task) → 질문(Question)
- 단일 책임 원칙 적용, 큰 Page Object 분해에 유용

### 3. 데이터 관리 전략
- **테스트 독립성**: 각 테스트가 자체 데이터 준비·정리
- **데이터 빌더 패턴**: 유연한 테스트 데이터 생성
`python
user = UserBuilder().with_admin_role().with_verified_email().build()
`
- **환경 격리**: 테스트 전용 DB 또는 트랜잭션 롤백

## 병렬 실행 전략

`yaml
# pytest-xdist 설정
pytest -n auto  # CPU 코어 수만큼 병렬 실행
`
- 테스트 간 공유 상태 없어야 함 (공유 상태 = 병렬화 방해)
- CI에서 여러 Worker에 테스트 분산

## Related Terms
- [[Automation-Frameworks]] — 아키텍처의 기술적 구현 도구
- [[Automation-Best-Practices]] — 아키텍처 설계 시 따를 원칙

## References
- [Martin Fowler — PageObject](https://martinfowler.com/bliki/PageObject.html)
- [Screenplay Pattern](https://serenity-js.org/handbook/design/screenplay-pattern/)
