# Statistical Analysis

## Overview
통계 분석은 데이터에서 패턴·관계·인사이트를 발견하기 위해 수학적 방법을 적용하는 과정이다. 데이터 분석가의 핵심 도구로, 결론이 통계적으로 유의한지 검증하는 역할을 한다.

## 기술 통계 (Descriptive Statistics)

### 중심 경향 측도
- **평균 (Mean)**: 합계 ÷ 개수. 이상값에 민감
- **중앙값 (Median)**: 정렬 후 중간값. 이상값에 강건
- **최빈값 (Mode)**: 가장 자주 나타나는 값

### 분산 측도
- **분산 (Variance)**: 평균으로부터의 거리의 제곱 평균
- **표준편차 (Std Dev)**: 분산의 제곱근. 데이터 퍼짐 정도
- **IQR (사분위 범위)**: Q3 - Q1. 이상값에 강건한 분산 측도

## 추론 통계 (Inferential Statistics)

### 가설 검정 프로세스
`
1. 귀무가설(H0) 설정: "두 그룹 간 차이 없음"
2. 유의수준 설정: α = 0.05 (5% 오류 허용)
3. 검정 통계량 계산
4. p-value 계산
5. p < α이면 H0 기각 (통계적으로 유의미한 차이 있음)
`

### 주요 통계 검정
| 검정 | 사용 상황 |
|---|---|
| **t-test** | 두 그룹 평균 비교 |
| **ANOVA** | 세 개 이상 그룹 평균 비교 |
| **Chi-square** | 범주형 변수 독립성 검정 |
| **Pearson 상관** | 두 연속 변수 간 선형 관계 |

## A/B 테스트에서의 통계
- **샘플 크기 계산**: 검정력(Power=0.8)·유의수준(α=0.05)·최소 효과 크기 기반
- **다중 검정 문제**: A/B/C/D 테스트 시 Bonferroni 보정 적용

## Related Terms
- [[Data-Visualization]] — 통계 결과를 시각화하는 방법
- [[Data-Driven-Decision-Making]] — 통계 분석의 최종 목적

## References
- [Statistics for Data Scientists — 무료 e-book](https://www.statlearning.com/)
