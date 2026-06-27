# Clean Architecture

## Overview
Clean Architecture는 Robert C. Martin(Uncle Bob)이 제안한 소프트웨어 설계 원칙으로, 비즈니스 로직을 외부 의존성(DB, UI, 프레임워크)으로부터 독립시키는 것을 목표로 한다.

## 동심원 구조

`
┌─────────────────────────────────────┐
│  Frameworks & Drivers               │  ← DB, UI, Web, 외부 도구
│  ┌─────────────────────────────┐   │
│  │  Interface Adapters          │   │  ← Controllers, Gateways, Presenters
│  │  ┌───────────────────────┐  │   │
│  │  │  Application Business │  │   │  ← Use Cases
│  │  │  ┌─────────────────┐  │  │   │
│  │  │  │  Enterprise BL  │  │  │   │  ← Entities (핵심 비즈니스 규칙)
│  │  │  └─────────────────┘  │  │   │
│  │  └───────────────────────┘  │   │
│  └─────────────────────────────┘   │
└─────────────────────────────────────┘
의존성 방향: 항상 안쪽을 향함 (Dependency Rule)
`

## 핵심 레이어

| 레이어 | 역할 | 예시 |
|---|---|---|
| **Entities** | 핵심 비즈니스 규칙 | User, Order, Payment |
| **Use Cases** | 애플리케이션 특유 비즈니스 로직 | CreateOrder, ProcessPayment |
| **Interface Adapters** | 데이터 변환·중계 | UserController, UserRepository 구현체 |
| **Frameworks & Drivers** | 외부 도구 | Spring, PostgreSQL, React |

## Dependency Inversion Principle
`java
// Use Case는 인터페이스에 의존 (추상)
class CreateOrderUseCase {
    private final OrderRepository repository; // 인터페이스
    // ...
}

// 외부 레이어가 구현체 제공
class JpaOrderRepository implements OrderRepository { ... }
`

## 장단점
- **장점**: 비즈니스 로직 독립 테스트, DB/프레임워크 교체 용이
- **단점**: 보일러플레이트 많음, 간단한 앱에는 과도한 복잡도

## Related Terms
- [[SOLID-Principles]] — Clean Architecture의 이론적 기반
- [[Domain-Driven-Design]] — Entity 설계 방법론

## References
- [Clean Architecture — Uncle Bob (2017)](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)
