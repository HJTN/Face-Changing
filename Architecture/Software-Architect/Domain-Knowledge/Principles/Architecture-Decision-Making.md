# Architecture Decision Making

## Overview
소프트웨어 아키텍트의 핵심 역할은 트레이드오프(Trade-off)를 분석하고 장기적 영향을 고려한 기술 결정을 내리는 것이다. 모든 아키텍처 결정에는 장단점이 있으며, 최선의 선택은 컨텍스트에 따라 다르다.

## ADR (Architecture Decision Record)

아키텍처 결정을 문서로 기록해 미래 팀원이 이해할 수 있게 한다.

`markdown
# ADR-001: 데이터베이스 선택 — PostgreSQL vs MongoDB

## 날짜: 2026-01-15
## 상태: 결정됨

## 컨텍스트
사용자 주문·결제 데이터를 저장해야 한다.
트랜잭션 일관성이 매우 중요하고, 스키마는 비교적 안정적이다.

## 결정
PostgreSQL을 선택한다.

## 이유
- ACID 트랜잭션이 결제 데이터에 필수
- 관계형 쿼리 패턴이 주문 데이터에 자연스러움
- 팀의 PostgreSQL 경험 보유

## 결과
NoSQL 유연성을 포기하지만 데이터 일관성 보장
`

## 아키텍처 결정 프레임워크

### 트레이드오프 분석
모든 결정에서 항상 존재하는 트레이드오프:
- 성능 vs 일관성
- 단순성 vs 유연성
- 비용 vs 기능
- 개발 속도 vs 유지보수성

### Boring Technology 원칙 (Dan McKinley)
- 검증된 기술이 혁신적 기술보다 리스크가 낮다
- 새 기술 도입 시 충분한 이유가 있어야 함
- "이 문제는 새 기술 없이는 해결 불가능한가?"

## 아키텍트가 피해야 할 안티패턴

- **Ivory Tower Architect**: 현장과 괴리된 탑상공론 설계
- **Architecture by Resume**: 쓰고 싶어서 신기술 도입
- **Big Upfront Design**: 모든 것을 초기에 설계하려 함

## Related Terms
- [[Architecture-Patterns]] — 결정 대상이 되는 패턴들
- [[Domain-Driven-Design]] — 도메인을 이해하는 설계 방법론

## References
- [Documenting Architecture Decisions — Michael Nygard](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions)
- [Choose Boring Technology](https://mcfunley.com/choose-boring-technology)
