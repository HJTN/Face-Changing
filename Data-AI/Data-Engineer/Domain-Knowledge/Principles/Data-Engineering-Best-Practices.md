# Data Engineering Best Practices

## Overview
데이터 엔지니어링 모범 사례는 신뢰성·유지보수성·확장성 있는 데이터 인프라를 구축하기 위한 원칙이다.

## 핵심 원칙

### 1. Idempotency (멱등성)
같은 파이프라인을 여러 번 실행해도 동일한 결과가 나와야 한다.
`sql
-- 나쁜 예: 실행할 때마다 데이터 중복 삽입
INSERT INTO sales SELECT * FROM raw_sales;

-- 좋은 예: 멱등한 방식
INSERT INTO sales
SELECT * FROM raw_sales
ON CONFLICT (id) DO UPDATE SET amount = EXCLUDED.amount;
`

### 2. Observability (관찰 가능성)
- 파이프라인 실패를 즉시 감지하고 알림
- 데이터 품질 지표 (행 수, NULL 비율, 이상값) 모니터링
- Lineage 추적: 데이터가 어디서 왔는지 추적 가능해야 함

### 3. Schema Evolution (스키마 진화)
- Upstream 스키마 변경에 파이프라인이 안전하게 대응
- Backward-compatible 변경: 컬럼 추가 (안전)
- Breaking 변경: 컬럼 제거·타입 변경 (파이프라인 사전 수정 필요)

### 4. Separation of Storage and Compute
- 데이터 저장(S3, GCS)과 처리 엔진(Spark, BigQuery)을 분리
- 비용 최적화, 독립 스케일링

### 5. Data as a Product
- 데이터셋을 내부 고객을 위한 제품으로 대우
- SLA (신선도, 정확도, 가용성) 정의 및 준수
- 문서화·소유권 명확화

## 파이프라인 테스트
- **Unit Test**: 변환 로직 단위 테스트 (dbt test)
- **Integration Test**: 소스에서 싱크까지 End-to-End 검증
- **Data Quality Test**: 행 수·고유값·NULL·범위 자동 검사

## Related Terms
- [[Data-Pipeline-Architecture]] — 원칙이 적용되는 파이프라인 구조
- [[Data-Modeling]] — 파이프라인 설계와 함께 고려

## References
- [The Data Engineering Cookbook](https://github.com/andkret/Cookbook)
