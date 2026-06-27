# BI Development Best Practices

## Overview
BI 개발 모범 사례는 신뢰성 있고 유지보수 가능한 보고서·대시보드·데이터 모델을 만들기 위한 원칙이다.

## 데이터 모델링 원칙

### Single Source of Truth (SSOT)
- 같은 지표가 여러 대시보드에서 다른 값으로 표시되는 것 방지
- 중앙 집중식 지표 정의 계층 (Metrics Layer) 필요
- 도구: dbt Metrics, Looker Explores

### Semantic Layer
`
원시 데이터 → 변환 → [Semantic Layer] → 대시보드
                       지표 정의·비즈니스 로직
                       "매출 = 확정 주문의 결제 완료 금액"
`
- BI 도구마다 다른 지표 계산식이 아닌 중앙 정의 사용
- Headless BI: AtScale, Cube.dev

## 보고서 개발 원칙

### 사용자 중심 설계
- 실제 사용자 인터뷰로 필요한 인사이트 파악 (UI/UX의 HCD 적용)
- 데이터 이상값·예외 상황에 어떻게 대응할지 고려

### 성능 최적화
- 집계 테이블(Aggregate Table) 미리 계산
- 데이터셋 크기 제한: 모든 데이터를 대시보드에 불러오지 않기
- 캐싱 전략: 자주 쓰는 쿼리 결과 캐시

### 문서화
- 각 지표의 계산 방법·출처·갱신 주기 문서화
- 데이터 사전(Data Dictionary) 유지

## 거버넌스
- 누가 어떤 데이터에 접근할 수 있는지 명확히 (Row-level Security)
- 데이터 변경 시 하위 보고서 영향 분석

## Related Terms
- [[Data-Warehousing-Concepts]] — BI의 데이터 기반
- [[Dashboard-Design]] — 원칙이 적용되는 결과물

## References
- [The Analytics Engineering Guide — dbt](https://www.getdbt.com/analytics-engineering/)
