# Machine Learning Fundamentals

## Overview
머신러닝(ML)은 명시적으로 프로그래밍하지 않고 데이터에서 패턴을 학습해 예측·분류·군집화 등의 작업을 수행하는 알고리즘 분야다.

## ML 학습 유형

### Supervised Learning (지도 학습)
- 레이블(정답)이 있는 데이터로 학습
- **분류 (Classification)**: 스팸 필터, 이미지 분류, 사기 탐지
- **회귀 (Regression)**: 주가 예측, 집값 예측

### Unsupervised Learning (비지도 학습)
- 레이블 없이 데이터 내 패턴 발견
- **군집화 (Clustering)**: 고객 세그멘테이션 (K-Means, DBSCAN)
- **차원 축소**: PCA, t-SNE (고차원 데이터 시각화)

### Reinforcement Learning (강화 학습)
- 에이전트가 환경과 상호작용하며 보상 극대화
- 게임 AI, 로봇 제어, 추천 시스템

## 주요 알고리즘

| 알고리즘 | 유형 | 강점 |
|---|---|---|
| **Linear/Logistic Regression** | 지도 | 해석 가능, 빠름 |
| **Decision Tree / Random Forest** | 지도 | 비선형, 특성 중요도 |
| **XGBoost / LightGBM** | 지도 | 경진대회 최강, 표 형식 데이터 |
| **Neural Network / Deep Learning** | 지도 | 이미지·텍스트·음성 |
| **K-Means** | 비지도 | 빠른 군집화 |
| **SVM** | 지도 | 소규모 고차원 데이터 |

## 모델 평가 지표

| 지표 | 사용 상황 |
|---|---|
| **Accuracy** | 클래스 균형 분류 |
| **Precision / Recall / F1** | 불균형 분류 (사기 탐지) |
| **AUC-ROC** | 분류 전반적 성능 |
| **RMSE / MAE** | 회귀 오차 |
| **R²** | 회귀 설명력 |

## Related Terms
- [[Statistical-Modeling]] — ML의 통계적 기반
- [[MLOps-Lifecycle]] — ML 모델을 프로덕션으로 가져가는 방법

## References
- [Hands-On Machine Learning with Scikit-Learn — Aurélien Géron](https://www.oreilly.com/library/view/hands-on-machine-learning/9781098125967/)
