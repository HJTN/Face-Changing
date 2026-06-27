# Data Visualization

## Overview
데이터 시각화는 데이터를 차트·그래프·대시보드로 표현해 패턴·트렌드·이상값을 직관적으로 이해할 수 있게 하는 기법이다. "천 마디 말보다 한 장의 차트"가 더 효과적으로 인사이트를 전달한다.

## 차트 유형 선택 가이드

| 목적 | 최적 차트 | 예시 |
|---|---|---|
| **비교** | Bar Chart (막대) | 월별 매출 비교 |
| **트렌드** | Line Chart (선) | 일별 방문자 추이 |
| **분포** | Histogram, Box Plot | 사용자 연령 분포 |
| **비율** | Pie Chart, Donut | 카테고리별 매출 비율 |
| **관계** | Scatter Plot | 광고비 vs 매출 상관관계 |
| **지리** | Map Chart | 지역별 매출 분포 |
| **구성 변화** | Stacked Bar | 시간별 카테고리 구성 변화 |

## Edward Tufte의 데이터-잉크 비율 원칙

**Data-Ink Ratio = 데이터를 표현하는 잉크 / 전체 잉크**

- 비율을 최대화하라: 불필요한 장식·격자선·3D 효과 제거
- Chartjunk (차트 쓰레기) 제거: 데이터와 무관한 시각 요소

`
나쁜 예: 3D 파이차트, 화려한 배경, 너무 많은 색상
좋은 예: 깔끔한 막대 차트, 데이터 레이블 직접 표시, 최소한의 격자선
`

## 도구별 특성
| 도구 | 특성 | 사용 상황 |
|---|---|---|
| **Tableau** | 드래그앤드롭, 강력한 대시보드 | 비개발자, 비즈니스 분석 |
| **Power BI** | Microsoft 생태계 통합 | 엔터프라이즈 |
| **Python (Matplotlib/Seaborn/Plotly)** | 커스터마이징, 자동화 | 데이터 과학자 |
| **Looker** | SQL 기반, 비즈니스 인텔리전스 | 데이터 팀 |

## Related Terms
- [[Statistical-Analysis]] — 시각화로 표현할 통계 결과
- [[Dashboard-Design]] — 여러 시각화를 결합한 대시보드 설계

## References
- [Edward Tufte — The Visual Display of Quantitative Information](https://www.edwardtufte.com/tufte/books_vdqi)
