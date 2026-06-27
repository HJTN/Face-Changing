# Domain-Driven Design (DDD)

## Overview
DDD(도메인 주도 설계)는 Eric Evans가 2003년 저서에서 제안한 복잡한 소프트웨어를 도메인 모델 중심으로 설계하는 방법론이다. 비즈니스 전문가와 개발자가 공유 언어(Ubiquitous Language)로 소통하는 것이 핵심이다.

## 전략적 설계

### Bounded Context (경계 컨텍스트)
- 특정 도메인 모델이 유효한 경계
- 마이크로서비스 경계 결정의 핵심 기준
`
[주문 컨텍스트]       [배송 컨텍스트]
 - Order (주문 중심)  - Shipment (배송 중심)
 - Customer (구매자)  - Recipient (수취인)
 
 같은 개념이지만 컨텍스트마다 다른 의미·속성을 가짐
`

### Context Map
- Bounded Context 간 관계를 다이어그램으로 표현
- 관계 유형: Upstream/Downstream, Shared Kernel, Anti-Corruption Layer

### Ubiquitous Language (보편 언어)
- 개발자·도메인 전문가가 동일한 용어 사용
- 코드에 비즈니스 용어를 직접 반영

## 전술적 설계

### Entity
- 식별자(ID)로 구별되는 객체
- 예: 주문(orderId), 사용자(userId)

### Value Object
- 식별자 없이 속성으로 구별
- 불변(Immutable)
- 예: 주소(시·도·상세주소), 금액(값·통화)

### Aggregate
- Entity + Value Object의 묶음, 단일 트랜잭션 경계
- Aggregate Root를 통해서만 접근

### Domain Event
- 도메인에서 발생한 의미 있는 사건
- 예: OrderPlaced, PaymentCompleted, UserRegistered

### Repository
- Aggregate를 저장·조회하는 인터페이스 (구현 세부사항 숨김)

## Related Terms
- [[Architecture-Patterns]] — DDD로 정의한 Bounded Context = 마이크로서비스 경계
- [[Clean-Architecture]] — DDD Entity = Clean Architecture Entity

## References
- [Eric Evans — Domain-Driven Design (The Blue Book)](https://www.domainlanguage.com/ddd/)
- [Vaughn Vernon — Implementing Domain-Driven Design](https://vaughnvernon.com/)
