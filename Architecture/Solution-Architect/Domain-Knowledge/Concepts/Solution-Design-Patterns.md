# Solution Design Patterns

## Overview
솔루션 설계 패턴은 특정 비즈니스·기술 문제를 해결하기 위해 반복적으로 적용되는 검증된 설계 방식이다. 솔루션 아키텍트는 여러 패턴을 조합해 최적 솔루션을 설계한다.

## 통합 패턴 (Integration Patterns)

### ESB (Enterprise Service Bus)
`
[App A] ─→ [ESB] ←─ [App B]
[App C] ─→ [ESB] ←─ [App D]
         중앙 버스
`
- 메시지 라우팅·변환·오케스트레이션 중앙화
- 장점: 중앙 제어 / 단점: 단일 장애 지점, 병목

### API-Led Connectivity (MuleSoft 방식)
`
[외부 시스템] → Experience API
                      ↓
              Process API (비즈니스 로직)
                      ↓
              System API (백엔드 시스템)
`

### Event-Driven Integration
- Kafka·RabbitMQ로 시스템 간 비동기 이벤트 통신
- 결합도 최소화, 확장성 우수

## 클라우드 마이그레이션 패턴 (6Rs)

| 전략 | 설명 |
|---|---|
| **Rehost** (Lift & Shift) | 그대로 클라우드로 이전 |
| **Replatform** | 최소 변경으로 클라우드 혜택 |
| **Repurchase** | SaaS 제품으로 교체 |
| **Refactor** | 클라우드 네이티브로 재설계 |
| **Retire** | 사용하지 않는 시스템 종료 |
| **Retain** | 현재 유지 (아직 이전 불가) |

## Related Terms
- [[Enterprise-Architecture]] — 패턴이 적용되는 전체 EA 맥락
- [[Solution-Architecture-Principles]] — 패턴 선택의 원칙

## References
- [AWS Migration Strategies](https://aws.amazon.com/blogs/enterprise-strategy/6-strategies-for-migrating-applications-to-the-cloud/)
