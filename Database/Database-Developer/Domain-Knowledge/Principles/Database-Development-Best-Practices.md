# Database Development Best Practices

## Overview
데이터베이스 개발 모범 사례는 데이터 무결성·성능·유지보수성을 장기적으로 유지하기 위한 원칙이다.

## 스키마 설계 원칙

### 1. Explicit Over Implicit
`sql
-- 나쁜 예: status를 숫자로
status INT  -- 1=활성, 2=비활성, 3=정지???

-- 좋은 예: Enum 또는 CHECK 제약
status VARCHAR(20) CHECK (status IN ('active', 'inactive', 'suspended'))
`

### 2. 기본키는 Surrogate Key + 자연키 유니크 제약
`sql
CREATE TABLE products (
  id BIGSERIAL PRIMARY KEY,              -- Surrogate Key
  sku VARCHAR(50) UNIQUE NOT NULL,       -- Natural Key (비즈니스 식별자)
  name VARCHAR(200) NOT NULL,
  created_at TIMESTAMPTZ DEFAULT NOW()
);
`

### 3. NULL 사용 최소화
- NULL은 "없음", "모름", "해당없음" 세 가지 의미로 해석되어 혼란
- NOT NULL + 기본값 또는 별도 테이블 분리

## 마이그레이션 원칙

### 순방향 호환 마이그레이션 (Backward Compatible)
`sql
-- 안전한 변경 (운영 중 적용 가능)
ALTER TABLE users ADD COLUMN nickname VARCHAR(100);

-- 위험한 변경 (다운타임 필요 또는 단계적 처리 필요)
ALTER TABLE users RENAME COLUMN name TO full_name;
`

### 마이그레이션 도구
- Flyway, Liquibase (Java 생태계)
- Alembic (Python)
- Prisma Migrate (TypeScript)

## SQL 안티패턴

- SELECT * 사용 금지 → 필요한 컬럼만 명시
- 조건 없는 UPDATE, DELETE 금지 → WHERE 절 항상 확인
- 비즈니스 로직을 트리거에 넣지 않기 → 추적 어려움

## Related Terms
- [[Database-Design-Patterns]] — 모범 사례의 구조적 기반
- [[Query-Optimization]] — 잘 설계된 스키마가 최적화의 전제

## References
- [PostgreSQL Best Practices](https://wiki.postgresql.org/wiki/Don%27t_Do_This)
