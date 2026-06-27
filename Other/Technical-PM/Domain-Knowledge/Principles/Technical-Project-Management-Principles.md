# Technical Project Management Principles

## Overview
기술 PM은 일반 PM의 역량에 기술적 이해를 더한 역할이다. 개발팀과 이해관계자 사이에서 기술 복잡성을 올바르게 전달하고 현실적인 계획을 수립하는 것이 핵심이다.

## 핵심 원칙

### 1. Technical Literacy (기술 이해력)
- 코드를 직접 작성할 필요는 없지만, 기술적 대화를 이해해야 함
- "왜 이 기능이 3주나 걸리나요?" → API 설계·DB 마이그레이션·테스트 이해
- 현실적인 일정 추정을 위한 기술 맥락 이해

### 2. Shield the Team (팀 보호)
- 외부 방해·과도한 요청으로부터 개발팀 보호
- "이 추가 요청은 다음 스프린트에 검토하겠습니다" — PM의 역할

### 3. Dependency Management (의존성 관리)
`
Feature A → Feature B → Feature C
외부 API → 내부 모듈 → UI 컴포넌트

의존성 체인 이해 → Critical Path 파악 → 병목 사전 예방
`

### 4. Estimation Honesty (추정 정직성)
- 압박으로 인한 근거 없는 일정 약속 금지
- Planning Poker, PERT 추정으로 신뢰 가능한 일정 수립
- 추정이 아닌 사실을 이해관계자에게 전달

### 5. Technical Debt Visibility
- 기술 부채가 비즈니스에 미치는 영향을 경영진에 설명
- "지금 부채를 갚지 않으면 6개월 후 신기능 개발 속도가 50% 줄어듭니다"

## 기술 PM의 독특한 역할

### 스프린트와 로드맵의 연결
- 개발팀의 스프린트 작업이 전략적 로드맵과 어떻게 연결되는지 매핑
- 스프린트 속도(Velocity)로 로드맵 달성 가능성 지속 검증

### 기술 부채 포트폴리오 관리
- 기술 부채를 항목화하고 비즈니스 영향도·수정 비용 평가
- 신기능 개발 vs 부채 상환 비율 관리 (20-30% 권장)

## Related Terms
- [[Project-Management-Fundamentals]] — 기술 PM의 PM 역량 기반
- [[Risk-Management]] — 기술 프로젝트 리스크 관리

## References
- [PMI — Technical Project Management](https://www.pmi.org/)
- [Engineering Management — Will Larson](https://lethain.com/elegant-puzzle/)
