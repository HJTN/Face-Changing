# Query Optimization

## Overview
쿼리 최적화는 데이터베이스 쿼리의 실행 속도와 자원 사용량을 줄이는 기법이다. 느린 쿼리(Slow Query) 하나가 전체 시스템 성능에 영향을 미칠 수 있다.

## 쿼리 실행 계획 분석

`sql
-- PostgreSQL
EXPLAIN ANALYZE SELECT * FROM orders WHERE customer_id = 123;

-- 결과 읽는 법
Seq Scan   → 전체 테이블 스캔 (느림, 인덱스 필요)
Index Scan → 인덱스 사용 (빠름)
Cost=0.00..1234.56  → 예상 비용
rows=1000  → 예상 반환 행 수
actual time=0.123 → 실제 소요 시간 (ms)
`

## 인덱스 전략

### 언제 인덱스를 추가하는가
- WHERE 조건에 자주 사용되는 컬럼
- JOIN ON 조건에 사용되는 외래키
- ORDER BY, GROUP BY에 사용되는 컬럼

### 인덱스 종류
| 유형 | 사용 사례 |
|---|---|
| **B-tree** | 기본 인덱스, 범위 쿼리 (=, <, >, BETWEEN) |
| **Hash** | 등호 조건만 (=), 범위 쿼리 불가 |
| **GIN** | 배열, JSONB, 전문 검색 (PostgreSQL) |
| **Composite** | 여러 컬럼 동시 조건 |
| **Partial** | WHERE 조건부 인덱스 (특정 행만) |
| **Covering** | SELECT 컬럼까지 인덱스에 포함 (Index-only scan) |

## N+1 쿼리 문제

`python
# 나쁜 예: N+1 쿼리
for post in Post.all():  # 1번 쿼리
    print(post.author.name)  # N번 쿼리 (게시글 수만큼)

# 좋은 예: JOIN으로 해결
posts = Post.includes(:author).all()  # 2번 쿼리 (Eager Loading)
`

## Related Terms
- [[Database-Design-Patterns]] — 좋은 설계가 최적화의 기반
- [[ACID-and-Transaction-Management]] — 최적화 시 트랜잭션 격리 고려

## References
- [Use the Index, Luke](https://use-the-index-luke.com/)
- [EXPLAIN ANALYZE Guide](https://www.postgresql.org/docs/current/sql-explain.html)
