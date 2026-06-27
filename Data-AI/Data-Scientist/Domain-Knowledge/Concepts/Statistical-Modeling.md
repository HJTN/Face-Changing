# Statistical Modeling

## Overview
통계 모델링은 데이터 생성 과정에 대한 수학적 가정을 세우고 데이터로 이를 검증하는 방법론이다. ML이 예측 정확도에 집중한다면, 통계 모델링은 관계의 이해와 해석에 집중한다.

## 주요 통계 모델

### 선형 회귀 (Linear Regression)
`
Y = β₀ + β₁X₁ + β₂X₂ + ... + ε
`
- 연속 종속변수 예측
- 계수(β)의 해석: X₁이 1 증가할 때 Y가 β₁만큼 변화
- 가정: 선형성, 등분산성, 정규성, 독립성

### 로지스틱 회귀 (Logistic Regression)
- 이진 분류 (0 or 1)
- 확률을 log-odds로 변환
- 계수 해석: Odds Ratio = exp(β)

### 다변량 분석
- **PCA (주성분 분석)**: 상관된 변수를 독립 성분으로 변환, 차원 축소
- **Factor Analysis**: 잠재 요인 발견

## Bias-Variance Tradeoff

`
총 오차 = Bias² + Variance + 노이즈

High Bias (Underfitting): 모델이 너무 단순 → 훈련·테스트 모두 높은 오차
High Variance (Overfitting): 모델이 너무 복잡 → 훈련 오차 낮음, 테스트 오차 높음
`

## 교차 검증 (Cross Validation)
`
K-Fold CV (K=5):
[Train | Train | Train | Train | Test ]  ← Fold 1
[Train | Train | Train | Test  | Train]  ← Fold 2
...
평균 성능 = 5개 폴드의 평균
`

## Related Terms
- [[Machine-Learning-Fundamentals]] — 통계 모델링과 ML의 관계
- [[Scientific-Method-in-DS]] — 데이터 과학의 연구 방법론

## References
- [Introduction to Statistical Learning (ISLR) — 무료](https://www.statlearning.com/)
