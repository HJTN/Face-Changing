# Architecture Patterns

## Overview
아키텍처 패턴은 소프트웨어 시스템의 전체 구조를 조직화하는 검증된 설계 방식이다. 모듈·서비스·컴포넌트 간의 관계와 통신 방식을 정의한다.

## 주요 아키텍처 패턴

### Layered (N-Tier) Architecture
`
Presentation → Business Logic → Data Access → Database
`
- 각 레이어는 바로 아래 레이어에만 의존
- 장점: 단순, 이해 쉬움 / 단점: 확장성 한계, 성능

### Microservices Architecture
`
[API Gateway]
    ↓
[User Service] [Order Service] [Payment Service] [Notification Service]
    ↓               ↓                ↓                  ↓
  [DB]            [DB]             [DB]               [DB]
`
- 서비스별 독립 배포, 독립 스케일링, 독립 기술 스택
- 장점: 유연성 / 단점: 분산 시스템 복잡도

### Event-Driven Architecture
`
Producer → [Event Broker (Kafka)] → Consumer
`
- 이벤트를 통한 비동기 통신, 결합도 감소
- 장점: 확장성, 독립성 / 단점: 복잡한 디버깅

### CQRS (Command Query Responsibility Segregation)
- 읽기(Query)와 쓰기(Command) 모델 분리
- 읽기: 최적화된 Read DB, 쓰기: 정규화된 Write DB

### Event Sourcing
- 현재 상태 저장 대신 이벤트 이력 저장
- 어느 시점의 상태도 재현 가능
- CQRS와 자주 함께 사용

## 마이크로서비스 통신 패턴

| 패턴 | 설명 | 사용 상황 |
|---|---|---|
| **Circuit Breaker** | 오류 서비스 호출 차단해 장애 전파 방지 | 동기 서비스 간 통신 |
| **API Gateway** | 단일 진입점, 인증·로드밸런싱 | 클라이언트-서비스 통신 |
| **Saga** | 분산 트랜잭션 관리 (보상 트랜잭션) | MSA 트랜잭션 |
| **Sidecar** | 보조 기능을 별도 컨테이너로 분리 | 서비스 메시 |

## Related Terms
- [[Domain-Driven-Design]] — 마이크로서비스 경계를 정의하는 방법론
- [[Architecture-Decision-Making]] — 패턴 선택의 의사결정 방법

## References
- [Mark Richards — Fundamentals of Software Architecture](https://www.oreilly.com/library/view/fundamentals-of-software/9781492043447/)
