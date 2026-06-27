# Data Pipeline Architecture

## Overview
데이터 파이프라인은 원천 데이터를 수집·변환·저장·서빙하는 과정이다. 데이터 엔지니어는 안정적이고 확장 가능한 파이프라인을 설계·구축·운영한다.

## 파이프라인 아키텍처 유형

### Batch Processing (배치 처리)
`
[Source DBs] ──→ [Extract] ──→ [Transform] ──→ [Load] ──→ [DW]
                                                              ↑
                                                   일정 주기 (매시간/매일)
`
- Apache Spark, dbt, Airflow
- 사용: 대용량 일괄 처리, 복잡한 변환, 비용 효율

### Streaming (스트리밍 처리)
`
[Events] ──→ [Kafka] ──→ [Flink/Spark Streaming] ──→ [Sink]
              실시간 메시지 큐        실시간 처리          저장
`
- Apache Kafka, Apache Flink, AWS Kinesis
- 사용: 실시간 이상 탐지, 실시간 대시보드

### Lambda Architecture
- 배치 레이어 + 스피드 레이어 결합
- 정확성(배치) + 저지연(스트리밍) 동시 제공

## ELT vs ETL

| 방식 | 처리 시점 | 특징 |
|---|---|---|
| **ETL** (Extract-Transform-Load) | 적재 전 변환 | 전통적, 온프렘 DW |
| **ELT** (Extract-Load-Transform) | 적재 후 변환 | 클라우드 DW (BigQuery, Snowflake) |

## 현대 데이터 스택 (Modern Data Stack)

`
수집: Fivetran / Airbyte
저장: Snowflake / BigQuery / Databricks
변환: dbt (SQL 기반 변환)
오케스트레이션: Airflow / Prefect / Dagster
시각화: Tableau / Looker / Power BI
`

## Related Terms
- [[Data-Modeling]] — 파이프라인 종점의 데이터 구조
- [[Data-Engineering-Best-Practices]] — 파이프라인 설계·운영 원칙

## References
- [Fundamentals of Data Engineering — Joe Reis](https://www.oreilly.com/library/view/fundamentals-of-data/9781098108298/)
