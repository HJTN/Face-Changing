# Database Design Patterns

## Overview
데이터베이스 설계 패턴은 반복적으로 나타나는 데이터 모델링 문제에 대한 검증된 해결책이다. 올바른 패턴 선택이 성능·확장성·유지보수성을 결정한다.

## 정규화 (Normalization)

### 목적: 데이터 중복 제거, 무결성 확보

| 정규형 | 조건 | 효과 |
|---|---|---|
| **1NF** | 원자값, 중복 행 없음 | 기본 구조 |
| **2NF** | 1NF + 부분 함수 종속 제거 | 복합 키 의존성 제거 |
| **3NF** | 2NF + 이행 함수 종속 제거 | 간접 의존성 제거 |
| **BCNF** | 모든 결정자가 후보키 | 더 강한 3NF |

### 언제 비정규화하는가
- 읽기 성능이 쓰기 일관성보다 중요할 때
- 조인 비용이 너무 높을 때
- 분석/리포팅 데이터 웨어하우스

## 주요 데이터 모델 패턴

### Entity-Attribute-Value (EAV)
- 동적 속성 처리 (속성 수가 불확실한 경우)
- 문제: 쿼리 복잡도, 타입 검증 어려움
- 대안: JSONB 컬럼 (PostgreSQL)

### Polymorphic Association
- 여러 테이블과 관계를 가지는 단일 테이블
`sql
-- comments 테이블이 posts와 videos 둘 다 참조
comments(id, commentable_type, commentable_id, body)
-- commentable_type: 'Post' or 'Video'
`

### Self-Referencing (계층 구조)
`sql
-- 카테고리 트리
categories(id, name, parent_id REFERENCES categories(id))
-- 쿼리: WITH RECURSIVE CTE
`

### Soft Delete
`sql
-- 실제 삭제 대신 플래그 처리
ALTER TABLE users ADD COLUMN deleted_at TIMESTAMP;
-- 조회 시: WHERE deleted_at IS NULL
`

## Related Terms
- [[Query-Optimization]] — 설계 패턴과 함께 성능 결정
- [[ACID-and-Transaction-Management]] — 패턴 적용 시 트랜잭션 고려

## References
- [SQL Antipatterns — Bill Karwin](https://pragprog.com/titles/bksqla/sql-antipatterns/)
