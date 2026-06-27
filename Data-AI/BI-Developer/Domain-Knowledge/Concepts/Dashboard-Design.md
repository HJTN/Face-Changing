# Dashboard Design

## Overview
대시보드는 비즈니스 KPI·지표를 한눈에 파악할 수 있게 시각화한 화면이다. BI 개발자는 데이터의 정확성뿐만 아니라 사용자가 실제로 데이터를 이해하고 행동할 수 있는 대시보드를 설계해야 한다.

## 대시보드 유형

| 유형 | 목적 | 업데이트 주기 |
|---|---|---|
| **Executive Dashboard** | C레벨 KPI 요약 | 일/주간 |
| **Operational Dashboard** | 실시간 운영 현황 | 분/시간 |
| **Analytical Dashboard** | 심층 분석, 드릴다운 | 일간 |

## Stephen Few의 대시보드 설계 원칙

### 1. 단일 화면에 모든 핵심 정보
- 스크롤 최소화, 한 눈에 전체 파악 가능해야 함
- 5±2 원칙: 인간이 동시에 처리할 수 있는 정보 덩어리는 7개 이하

### 2. 정보 계층 구조
- 가장 중요한 KPI → 요약 → 세부 → 드릴다운
- F패턴: 좌상단에 가장 중요한 정보 배치

### 3. 일관된 시각 언어
- 같은 지표에는 항상 같은 색상
- 증가=초록, 감소=빨강 (단, 문화권 고려)

### 4. 데이터 vs 잉크 최소화
- 불필요한 격자선·3D 효과·그림자 제거
- 레이블을 차트 내부에 직접 배치 (범례 최소화)

## BI 도구 특성

| 도구 | 특성 |
|---|---|
| **Tableau** | 드래그앤드롭, 유연한 시각화, 고급 분석 |
| **Power BI** | Microsoft 통합, 비용 효율, Copilot AI 분석 |
| **Looker** | SQL 기반, 데이터 모델(LookML), Google Cloud 통합 |
| **Apache Superset** | 오픈소스, 개발자 친화 |

## Related Terms
- [[Data-Warehousing-Concepts]] — 대시보드에 데이터를 제공하는 백엔드
- [[Data-Visualization]] — 대시보드 구성 요소인 개별 시각화 기법

## References
- [Stephen Few — Show Me the Numbers](https://www.perceptualedge.com/books.php)
