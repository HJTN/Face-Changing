# Caching Strategies

## Overview
캐싱은 느린 연산(DB 쿼리, 외부 API 호출)의 결과를 빠른 저장소에 임시 보관해 반복 연산을 피하는 기법이다. 서버 응답 시간 단축과 DB 부하 감소의 핵심 도구다.

## 캐시 계층

`
클라이언트 → CDN → API Gateway → 애플리케이션 서버 → Redis → Database
[브라우저]  [엣지]  [API 캐시]   [인메모리 캐시]    [분산 캐시] [영구 저장]
`

## 캐싱 전략

### Cache-Aside (Lazy Loading)
`
읽기: Cache miss → DB 조회 → Cache 저장 → 반환
쓰기: DB 업데이트 → Cache 무효화
`
- 가장 일반적인 패턴
- 첫 요청은 항상 Cache miss (Cold Start 문제)

### Write-Through
`
쓰기: DB 업데이트 + Cache 동시 업데이트
읽기: Cache hit 보장
`
- 데이터 일관성 높음, 쓰기 지연 발생

### Write-Behind (Write-Back)
`
쓰기: Cache에만 즉시 저장 → 비동기로 DB에 배치 쓰기
`
- 쓰기 성능 최고, 데이터 손실 위험

## Redis 주요 데이터 구조 활용
| 구조 | 활용 사례 |
|---|---|
| String | 세션 토큰, 단순 카운터 |
| Hash | 유저 프로필 (필드별 접근) |
| List | 최근 본 상품, 활동 피드 |
| Set | 태그, 유니크 방문자 수 |
| Sorted Set | 리더보드, 만료 시간 기반 큐 |

## 캐시 무효화 (Cache Invalidation) — 가장 어려운 문제
- **TTL(Time-To-Live)**: 일정 시간 후 자동 만료
- **Event-Driven**: 데이터 변경 이벤트 시 캐시 삭제
- Phil Karlton: "컴퓨터 과학에서 어려운 문제는 캐시 무효화와 이름 짓기뿐이다"

## Related Terms
- [[Redis]] — 가장 널리 사용되는 캐시 솔루션
- [[Concurrency-Models]] — 캐싱과 동시성은 함께 고려해야 함

## References
- [AWS Caching Overview](https://aws.amazon.com/caching/)
