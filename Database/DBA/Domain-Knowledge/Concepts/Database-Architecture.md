# Database Architecture

## Overview
데이터베이스 아키텍처는 데이터의 저장·접근·관리 방식을 정의하는 구조다. RDBMS·NoSQL·NewSQL·분산 DB 등 다양한 선택지 중 요구사항에 맞는 아키텍처를 선택해야 한다.

## 데이터베이스 유형

### RDBMS (관계형)
- 테이블·행·열·외래키로 구조화된 데이터
- SQL로 쿼리
- **대표**: PostgreSQL, MySQL, Oracle, SQL Server
- **최적**: 트랜잭션 데이터, 복잡한 조인 필요

### NoSQL
| 유형 | 대표 | 최적 사용 |
|---|---|---|
| **Document** | MongoDB, Firestore | 유연한 스키마, 중첩 객체 |
| **Key-Value** | Redis, DynamoDB | 캐시, 세션, 단순 조회 |
| **Column-Family** | Cassandra, HBase | 시계열, 로그, 높은 쓰기 |
| **Graph** | Neo4j, Amazon Neptune | 소셜 그래프, 추천 시스템 |

### NewSQL
- RDBMS의 ACID + NoSQL의 수평 확장
- **대표**: CockroachDB, Google Spanner, TiDB
- 최적: 글로벌 분산 트랜잭션

## 데이터베이스 배포 아키텍처

### Primary-Replica (Master-Slave)
`
쓰기 → [Primary] ──복제──→ [Replica 1]
                        └──복제──→ [Replica 2]  ← 읽기
`

### 샤딩 (Sharding)
`
User ID 1-1M  → [Shard 1]
User ID 1M-2M → [Shard 2]
User ID 2M-3M → [Shard 3]
`
수평 분할로 단일 DB 한계 초과 데이터 처리

## Related Terms
- [[ACID-and-Transaction-Management]] — 관계형 DB의 핵심 보장
- [[Query-Optimization]] — 아키텍처와 함께 성능을 결정

## References
- [Use the Index, Luke — SQL 성능 튜닝](https://use-the-index-luke.com/)
