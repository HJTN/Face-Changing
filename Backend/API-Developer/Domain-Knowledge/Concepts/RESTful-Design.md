# RESTful API Design

## Overview
REST(Representational State Transfer)는 Roy Fielding이 2000년 논문에서 정의한 웹 API 설계 아키텍처 스타일이다. 리소스 중심 URI, HTTP 메서드, 상태 비저장성을 핵심으로 한다.

## 6가지 REST 제약조건

1. **Client-Server** — UI와 데이터 저장 분리
2. **Stateless** — 요청에 필요한 모든 정보 포함, 서버는 세션 저장 안 함
3. **Cacheable** — 응답에 캐시 가능 여부 명시
4. **Uniform Interface** — 일관된 인터페이스 (자원 식별, 표현을 통한 조작)
5. **Layered System** — 클라이언트는 중간 서버를 인식하지 않음
6. **Code on Demand** (선택) — 서버가 실행 코드를 클라이언트에 전송

## REST API 설계 규칙

### URI 설계
`
✅ GET    /users          → 유저 목록
✅ GET    /users/{id}     → 특정 유저
✅ POST   /users          → 유저 생성
✅ PUT    /users/{id}     → 유저 전체 수정
✅ PATCH  /users/{id}     → 유저 부분 수정
✅ DELETE /users/{id}     → 유저 삭제

❌ GET /getUsers          → 동사 사용 금지
❌ POST /users/delete     → HTTP 메서드로 행위 표현
`

### HTTP 상태 코드
| 코드 | 의미 | 사용 상황 |
|---|---|---|
| 200 | OK | 성공 |
| 201 | Created | POST 성공, 자원 생성됨 |
| 204 | No Content | DELETE 성공, 응답 본문 없음 |
| 400 | Bad Request | 잘못된 요청 파라미터 |
| 401 | Unauthorized | 인증 필요 |
| 403 | Forbidden | 권한 없음 |
| 404 | Not Found | 자원 없음 |
| 429 | Too Many Requests | Rate Limit 초과 |
| 500 | Internal Server Error | 서버 오류 |

## REST vs GraphQL vs gRPC

| 기준 | REST | GraphQL | gRPC |
|---|---|---|---|
| 데이터 패칭 | 여러 엔드포인트 | 단일 엔드포인트 | 스트리밍 가능 |
| 오버패칭 | 있음 | 없음 | 없음 |
| 캐싱 | HTTP 캐시 활용 | 복잡 | 어려움 |
| 사용 상황 | 일반 API | 유연한 클라이언트 | 마이크로서비스 내부 |

## Related Terms
- [[API-Security]] — 인증·인가·Rate Limiting 전략
- [[API-Versioning]] — Breaking Change 없이 API 진화
- [[OpenAPI-Swagger]] — REST API 명세 도구

## References
- [Roy Fielding의 REST 논문](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
- [RESTful API Design Best Practices](https://restfulapi.net/)
