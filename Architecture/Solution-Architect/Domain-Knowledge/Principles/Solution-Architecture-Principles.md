# Solution Architecture Principles

## Overview
솔루션 아키텍처 원칙은 솔루션 아키텍트가 시스템을 설계할 때 따르는 핵심 가이드라인이다. 기술적 우수성과 비즈니스 가치를 동시에 달성하는 것이 목표다.

## 핵심 설계 원칙

### 1. Fit for Purpose (목적 적합성)
- 최고의 기술이 아닌 목적에 맞는 기술 선택
- "이 솔루션이 비즈니스 문제를 해결하는가?" 항상 자문
- 필요 이상의 복잡성 추가 금지

### 2. Total Cost of Ownership (TCO) 고려
- 라이선스·인프라·개발·운영·교육 비용 모두 고려
- 단기 개발 비용만 보지 말고 5년 TCO 계산

### 3. Vendor Independence
- 가능한 오픈 표준 사용 (lock-in 최소화)
- 특정 벤더 기술을 추상화 레이어 뒤에 숨김

### 4. Security by Design
- 보안을 나중에 추가가 아닌 설계에 내재화
- 데이터 분류·암호화·접근 제어를 초기에 정의

### 5. Scalability and Resilience
- 예상 부하의 3-10배 처리 가능한 아키텍처
- 단일 장애 지점(SPOF) 제거

## 솔루션 아키텍트의 역할

### 기술 브리지 (Technical Bridge)
- 비즈니스 이해관계자 ↔ 개발팀 사이의 통역가
- 비즈니스 요구사항을 기술 명세로, 기술 제약을 비즈니스 언어로 번역

### 솔루션 아키텍처 문서 (SAD)
- 아키텍처 개요, 시스템 다이어그램
- 기술 선택 이유 (ADR)
- 비기능적 요구사항 (성능·가용성·보안)
- 위험 및 제약사항

## Related Terms
- [[Enterprise-Architecture]] — 솔루션 아키텍처가 놓이는 EA 맥락
- [[Solution-Design-Patterns]] — 원칙을 실현하는 구체적 패턴

## References
- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
- [TOGAF Solution Architecture](https://pubs.opengroup.org/architecture/togaf9-doc/arch/)
