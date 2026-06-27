# ACID and Transaction Management

## Overview
ACID는 데이터베이스 트랜잭션이 안전하게 처리되도록 보장하는 4가지 특성이다. 금융·예약·재고 등 데이터 정확성이 중요한 시스템에서 핵심 요구사항이다.

## ACID 4가지 특성

### A — Atomicity (원자성)
트랜잭션 내의 모든 연산은 전부 성공하거나 전부 실패한다.
`sql
BEGIN TRANSACTION;
  UPDATE accounts SET balance = balance - 100 WHERE id = 1; -- 출금
  UPDATE accounts SET balance = balance + 100 WHERE id = 2; -- 입금
COMMIT; -- 둘 다 성공해야 커밋, 하나라도 실패하면 ROLLBACK
`

### C — Consistency (일관성)
트랜잭션 전후 DB는 항상 유효한 상태를 유지한다. (제약조건·외래키 항상 성립)

### I — Isolation (격리성)
동시에 실행되는 트랜잭션들이 서로 간섭하지 않는다.

### D — Durability (지속성)
커밋된 트랜잭션은 시스템 장애 후에도 영구 보존된다. (WAL, Redo Log)

## 트랜잭션 격리 수준

| 격리 수준 | Dirty Read | Non-Repeatable Read | Phantom Read | 성능 |
|---|---|---|---|---|
| **Read Uncommitted** | 발생 | 발생 | 발생 | 최고 |
| **Read Committed** | 방지 | 발생 | 발생 | 높음 |
| **Repeatable Read** | 방지 | 방지 | 발생 | 보통 |
| **Serializable** | 방지 | 방지 | 방지 | 낮음 |

PostgreSQL 기본: Read Committed / MySQL InnoDB 기본: Repeatable Read

## ACID vs BASE (NoSQL)
- **BASE**: Basically Available, Soft state, Eventually consistent
- 완전한 일관성보다 가용성·성능 우선 (SNS 좋아요 카운터 등)

## Related Terms
- [[Database-Architecture]] — ACID가 지원되는 DB 유형 선택
- [[Data-Reliability-Engineering]] — ACID를 넘어 시스템 신뢰성 관리

## References
- [PostgreSQL — Transactions](https://www.postgresql.org/docs/current/tutorial-transactions.html)
