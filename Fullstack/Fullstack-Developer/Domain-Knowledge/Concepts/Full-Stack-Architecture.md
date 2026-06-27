# Full-Stack Architecture

## Overview
풀스택 아키텍처는 프론트엔드·백엔드·데이터베이스를 하나의 일관된 시스템으로 설계하는 관점이다. 풀스택 개발자는 각 레이어의 관심사와 경계를 이해하고 적절히 분리해야 한다.

## 전형적인 풀스택 스택 구성

### MERN (Modern JavaScript Stack)
`
MongoDB ← → Express.js ← → React ← → Node.js
  [DB]         [API]        [UI]     [런타임]
`

### T3 Stack (타입 안전 풀스택)
`
Next.js (React + SSR) + TypeScript + tRPC + Prisma + PostgreSQL
`

### 레이어별 역할
| 레이어 | 기술 | 책임 |
|---|---|---|
| **Presentation** | React, Vue, Next.js | UI 렌더링, 사용자 상호작용 |
| **API** | REST, GraphQL, tRPC | 데이터 요청/응답, 인증 |
| **Business Logic** | Node.js, Go, Java | 비즈니스 규칙 처리 |
| **Data Access** | ORM, Query Builder | DB 쿼리 추상화 |
| **Database** | PostgreSQL, MongoDB | 데이터 영구 저장 |
| **Infrastructure** | AWS, Vercel, Docker | 배포·스케일링 |

## API 통신 방식 선택

| 방식 | 특징 | 추천 상황 |
|---|---|---|
| **REST** | HTTP 표준, 캐시 활용 | 일반 CRUD API |
| **GraphQL** | 필요한 데이터만 요청 | 복잡한 데이터 요구, 다양한 클라이언트 |
| **tRPC** | TypeScript 타입 공유 | 풀스택 TypeScript 팀 |
| **WebSocket** | 실시간 양방향 통신 | 채팅, 알림, 협업 도구 |

## Related Terms
- [[End-to-End-Development]] — 전체 스택을 혼자 개발하는 실제 흐름
- [[Separation-of-Concerns]] — 레이어 분리의 이론적 기반

## References
- [T3 Stack](https://create.t3.gg/)
- [The Fullstack Web Developer Roadmap](https://roadmap.sh/full-stack)
