# Test Automation Best Practices

## Overview
테스트 자동화 모범 사례는 자동화의 함정(취약한 테스트, 유지보수 부담, ROI 부족)을 피하고 지속적으로 가치를 제공하는 자동화 시스템을 구축하기 위한 원칙이다.

## 핵심 원칙

### 1. FIRST 원칙 (단위 테스트)
- **Fast**: 테스트는 빨라야 함 (단위 테스트: ms 단위)
- **Isolated**: 다른 테스트에 의존하지 않음
- **Repeatable**: 반복 실행 시 항상 같은 결과
- **Self-validating**: 테스트가 자체적으로 성공/실패 판단
- **Timely**: 프로덕션 코드와 함께 작성

### 2. Flaky Test 근절
Flaky Test(비결정론적 테스트): 같은 코드에서 실행 시마다 성공/실패가 달라지는 테스트
- 원인: 경쟁 조건(Race Condition), 외부 API 의존, 하드코딩된 sleep
- 해결: 명시적 대기(Explicit Wait), 목(Mock), 테스트 격리

`python
# 나쁜 예: sleep으로 기다리기
time.sleep(3)
assert page.get_text() == "완료"

# 좋은 예: 조건 충족 시까지 대기
page.wait_for_selector("[data-status='완료']")
assert page.get_text() == "완료"
`

### 3. AAA 패턴 (Arrange-Act-Assert)
`python
def test_order_total():
    # Arrange: 사전 조건 설정
    cart = Cart()
    cart.add_item(Product(price=1000), qty=2)

    # Act: 테스트할 행동 실행
    total = cart.calculate_total()

    # Assert: 결과 검증
    assert total == 2000
`

### 4. 테스트 유지보수성
- 테스트 코드도 프로덕션 코드와 동일한 품질 기준
- 중복 최소화 (DRY), 명확한 테스트 이름
- 실패 메시지가 원인을 즉시 알려줘야 함

## 무엇을 자동화할 것인가
- **자동화 우선**: 반복 실행, 회귀 테스트, 경계값 테스트, API 계약
- **수동 우선**: 탐색적 테스트, 사용성 테스트, 일회성 기능

## Related Terms
- [[Automation-Frameworks]] — 원칙을 구현하는 기술 도구
- [[Test-Architecture]] — 원칙이 반영된 전체 시스템 설계

## References
- [Google Testing Blog](https://testing.googleblog.com/)
