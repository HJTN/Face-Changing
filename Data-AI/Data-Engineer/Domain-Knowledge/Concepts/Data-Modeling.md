# Data Modeling

## Overview
데이터 모델링은 비즈니스 데이터를 데이터베이스·데이터 웨어하우스에 어떻게 구조화할지 정의하는 과정이다. 좋은 데이터 모델은 쿼리 성능·데이터 일관성·이해 가능성을 결정한다.

## 데이터 웨어하우스 모델링

### Star Schema (스타 스키마)
`
             [Dim_Date]
                 |
[Dim_Product] — [Fact_Sales] — [Dim_Customer]
                 |
             [Dim_Store]
`
- **Fact Table**: 측정값 (매출액, 수량, 비용)
- **Dimension Table**: 맥락 (날짜, 고객, 상품, 지점)
- 장점: 쿼리 단순, 성능 우수
- 단점: 데이터 중복

### Snowflake Schema
- Star Schema의 Dimension을 추가로 정규화
- 데이터 중복 감소, 쿼리 복잡도 증가

### One Big Table (OBT)
- 모든 데이터를 하나의 넓은 테이블로 denormalize
- 현대 컬럼형 DW (BigQuery, Snowflake)에서 성능 우수
- dbt에서 많이 사용

## OLTP vs OLAP

| 항목 | OLTP | OLAP |
|---|---|---|
| 목적 | 트랜잭션 처리 | 분석·리포팅 |
| 쿼리 패턴 | 단건 CRUD | 대용량 집계 |
| 정규화 | 높음 (3NF) | 낮음 (Star Schema) |
| 예시 | MySQL, PostgreSQL | Snowflake, BigQuery |

## dbt (data build tool)
- SQL로 DW 내 데이터 변환 정의
- 데이터 모델을 코드로 버전 관리
- 의존성 DAG 자동 생성, 테스트 내장

## Related Terms
- [[Data-Pipeline-Architecture]] — 모델링된 데이터를 적재하는 파이프라인
- [[Data-Engineering-Best-Practices]] — 모델링 설계 원칙

## References
- [dbt Documentation](https://docs.getdbt.com/)
- [Kimball Group — Dimensional Modeling](https://www.kimballgroup.com/data-warehouse-business-intelligence-resources/kimball-techniques/dimensional-modeling-techniques/)
