# ML Engineering Principles

## Overview
ML 엔지니어링 원칙은 실험실 수준의 ML 코드를 신뢰성 있는 프로덕션 시스템으로 만드는 방법론이다.

## 핵심 원칙

### 1. Data First
- 알고리즘보다 데이터 품질이 성능에 더 큰 영향
- 데이터 수집·레이블링·검증에 투자 우선
- Google의 "Data-Centric AI" 철학

### 2. Start Simple
- 복잡한 딥러닝 전에 단순 선형 모델로 베이스라인 확립
- 단순 모델이 충분하다면 복잡한 모델은 불필요
- "Make it work, make it right, make it fast" 순서

### 3. Reproducibility (재현성)
`python
# 항상 랜덤 시드 고정
import random, numpy as np, torch
random.seed(42); np.random.seed(42); torch.manual_seed(42)

# 환경 기록
pip freeze > requirements.txt
# Docker 이미지로 환경 완전 고정
`

### 4. Monitoring is Not Optional
- 프로덕션 ML 시스템의 가장 큰 적: **Model/Data Drift**
- 입력 데이터 분포 변화를 감지하지 못하면 모델은 조용히 망가짐
- 지표: PSI (Population Stability Index), KL Divergence

### 5. Feedback Loops
- 모델 예측 → 사용자 행동 → 훈련 데이터
- 피드백 루프가 편향을 증폭할 수 있음 (추천 시스템 에코 챔버)

## ML 기술 부채 (Technical Debt in ML)
- **Glue Code**: 다양한 ML 프레임워크를 연결하는 복잡한 접착 코드
- **Pipeline Jungle**: 여러 파이프라인이 뒤엉킨 상태
- **Undeclared Consumers**: 어디서 모델을 사용하는지 불명확

## Related Terms
- [[MLOps-Lifecycle]] — 원칙을 실현하는 운영 체계
- [[Model-Training-and-Serving]] — 원칙의 실제 적용

## References
- [Hidden Technical Debt in Machine Learning Systems (NIPS 2015)](https://papers.nips.cc/paper/2015/file/86df7dcfd896fcaf2674f757a2463eba-Paper.pdf)
