# Enterprise Architecture

## Overview
엔터프라이즈 아키텍처(EA)는 조직의 비즈니스 전략·프로세스·기술을 통합적으로 설계하고 정렬하는 프레임워크다. 솔루션 아키텍트는 EA를 기반으로 개별 솔루션을 설계한다.

## 주요 EA 프레임워크

### TOGAF (The Open Group Architecture Framework)
- 가장 널리 사용되는 EA 프레임워크
- **ADM (Architecture Development Method)**: 9단계 반복 프로세스
  - Architecture Vision → Business → Information Systems → Technology → Opportunities → Migration → Implementation → Change Management
- 인증: TOGAF 9 Foundation / Practitioner

### Zachman Framework
- EA를 6×6 매트릭스로 표현
- 관점(누가·무엇·어떻게·어디서·언제·왜) × 추상화 수준

## EA 4개 도메인

| 도메인 | 설명 | 산출물 |
|---|---|---|
| **Business Architecture** | 비즈니스 전략·프로세스·조직 구조 | 비즈니스 역량 맵, 프로세스 모델 |
| **Information Architecture** | 데이터·정보 자산 구조 | 데이터 모델, 데이터 흐름도 |
| **Application Architecture** | 애플리케이션·시스템 구조 | 애플리케이션 포트폴리오, 통합 지도 |
| **Technology Architecture** | 인프라·기술 표준 | 기술 스택, 인프라 다이어그램 |

## EA vs 솔루션 아키텍처

`
EA: 조직 전체의 큰 그림
  "어떤 시스템이 있어야 하는가?"
  
솔루션 아키텍처: 특정 프로젝트·시스템의 설계
  "이 시스템을 어떻게 만들 것인가?"
`

## Related Terms
- [[Solution-Design-Patterns]] — EA 맥락에서 솔루션을 설계하는 패턴
- [[Solution-Architecture-Principles]] — 솔루션 아키텍트의 설계 원칙

## References
- [TOGAF Standard](https://www.opengroup.org/togaf)
