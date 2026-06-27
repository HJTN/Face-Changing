# Data Warehousing Concepts

## Overview
데이터 웨어하우스(DW)는 여러 소스의 데이터를 통합·정제해 분석·리포팅을 위해 최적화된 중앙 저장소다. OLTP 시스템과 분리되어 비즈니스 의사결정을 지원한다.

## DW vs Data Lake vs Data Lakehouse

| 항목 | Data Warehouse | Data Lake | Data Lakehouse |
|---|---|---|---|
| 데이터 형태 | 정형 (Schema-on-write) | 정형·반정형·비정형 | 정형 + 반정형 |
| 스키마 | 사전 정의 | Schema-on-read | Schema-on-write 옵션 |
| 성능 | 빠른 쿼리 | 느림 (원시 데이터) | 빠름 |
| 비용 | 높음 | 낮음 | 중간 |
| 도구 | Snowflake, BigQuery | AWS S3, Azure ADLS | Databricks, Delta Lake |

## DW 아키텍처 구성

`
[Source Systems]
  OLTP DB, SaaS 앱, 로그, 외부 데이터
         ↓ ETL/ELT
[Staging Area]      ← 원시 데이터 임시 보관
         ↓ 변환
[Data Warehouse]    ← 정제·통합된 데이터 (Star/Snowflake Schema)
         ↓
[Data Mart]         ← 부서별 특화 뷰 (마케팅 DM, 재무 DM)
         ↓
[BI 도구]           ← Tableau, Power BI, Looker
`

## 현대 클라우드 DW

| 플랫폼 | 강점 |
|---|---|
| **Snowflake** | 스토리지·컴퓨트 분리, 데이터 공유 |
| **BigQuery** | 서버리스, 페타바이트 쿼리 빠름, GCP 통합 |
| **Redshift** | AWS 생태계 통합, Spectrum으로 S3 직접 쿼리 |
| **Synapse** | Azure 통합, Power BI 최적화 |

## Related Terms
- [[Dashboard-Design]] — DW 데이터를 시각화하는 최종 레이어
- [[Data-Modeling]] — DW의 스키마 설계 방법론

## References
- [Kimball Group — Data Warehouse Concepts](https://www.kimballgroup.com/)
