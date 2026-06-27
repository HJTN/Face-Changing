# Data Reliability Engineering

## Overview
DRE(Data Reliability Engineering)는 SRE 원칙을 데이터 인프라에 적용한 개념이다. 데이터가 언제나 정확하고, 접근 가능하고, 신뢰할 수 있는 상태를 유지하도록 엔지니어링한다.

## 4대 데이터 신뢰성 축

### 1. Availability (가용성)
- 데이터가 필요할 때 항상 접근 가능해야 함
- 고가용성 구성: Primary-Replica, 자동 Failover
- RTO (Recovery Time Objective): 장애 후 복구까지 허용 시간
- RPO (Recovery Point Objective): 허용 가능한 최대 데이터 손실 시간

### 2. Durability (내구성)
- 커밋된 데이터는 절대 손실되어서는 안 됨
- WAL (Write-Ahead Log), 정기 백업, Point-in-Time Recovery
- 3-2-1 백업 규칙: 3개 복사본, 2가지 미디어, 1개 오프사이트

### 3. Data Quality (데이터 품질)
- **Accuracy**: 실제 값과 일치
- **Completeness**: 필수 필드 누락 없음
- **Timeliness**: 최신 데이터
- **Consistency**: 여러 소스 간 일치

### 4. Performance (성능)
- 쿼리 응답 시간 SLO 정의
- 인덱스 최적화, 쿼리 플랜 분석
- 용량 계획 (데이터 증가율 예측)

## DBA의 현대적 역할 변화
전통적 DBA → Data Reliability Engineer:
- 수동 관리 → 자동화 (스크립트, IaC)
- 단일 DB → 분산 DB (Cassandra, CockroachDB)
- 온프렘 → 클라우드 (RDS, Cloud SQL, Aurora)

## Related Terms
- [[ACID-and-Transaction-Management]] — 신뢰성의 트랜잭션 레이어
- [[Database-Architecture]] — 신뢰성 있는 아키텍처 선택 기준

## References
- [Google SRE — Data Reliability](https://sre.google/)
