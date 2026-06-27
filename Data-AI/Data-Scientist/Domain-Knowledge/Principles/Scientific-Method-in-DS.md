# Scientific Method in Data Science

## Overview
데이터 과학에서 과학적 방법론은 가설 기반 탐구·엄격한 실험 설계·재현 가능한 분석을 통해 신뢰할 수 있는 인사이트를 도출하는 원칙이다.

## 데이터 과학의 과학적 프로세스

`
[관찰] 데이터에서 흥미로운 패턴 발견
  ↓
[가설 수립] "X를 하면 Y가 증가할 것이다"
  ↓
[실험 설계] A/B 테스트, 샘플 크기 계산, 대조군 설정
  ↓
[데이터 수집] 편향 없는 데이터 수집
  ↓
[분석] 통계 검정, 모델링
  ↓
[결론] 가설 지지/기각 (p-value, 신뢰구간)
  ↓
[재현성 검증] 코드·데이터 공개, 동료 검토
`

## 핵심 원칙

### 1. Reproducibility (재현성)
- 같은 데이터·코드로 같은 결과가 나와야 함
- 랜덤 시드 고정, 환경 기록 (Docker, conda environment)
- Jupyter Notebook + Git으로 분석 버전 관리

### 2. Exploration vs Confirmation
- **탐색적 분석 (EDA)**: 가설 없이 데이터 탐색 → 가설 생성
- **확증적 분석**: 사전 정의된 가설 검정
- EDA로 발견한 패턴은 새 데이터로 검증해야 함 (HARKing 위험)

### 3. Correlation ≠ Causation
- 관찰 데이터의 상관관계는 인과관계가 아님
- 인과관계 확인: RCT, IV(도구변수), DiD(이중차분법)

### 4. Communicating Uncertainty
- 점 추정값만 제시하지 말고 신뢰구간 함께 제시
- "정확도 95%"보다 "95% CI [92.3%, 97.2%]"

## Related Terms
- [[Statistical-Modeling]] — 과학적 방법의 기술적 구현
- [[Machine-Learning-Fundamentals]] — 예측 모델의 실험적 검증

## References
- [The Art of Statistics — David Spiegelhalter](https://www.penguin.co.uk/books/317/317369/the-art-of-statistics/9780241258767.html)
