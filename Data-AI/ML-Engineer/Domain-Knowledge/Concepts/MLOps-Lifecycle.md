# MLOps Lifecycle

## Overview
MLOps(Machine Learning Operations)는 ML 모델의 개발·배포·모니터링·재훈련을 자동화하고 신뢰성 있게 운영하기 위한 방법론이다. DevOps 원칙을 ML에 적용한 개념이다.

## MLOps 성숙도 수준

| 수준 | 설명 | 자동화 수준 |
|---|---|---|
| **Level 0** | 수동 프로세스 | 없음 |
| **Level 1** | ML 파이프라인 자동화 | 모델 훈련 자동화 |
| **Level 2** | CI/CD 파이프라인 | 코드 변경 시 자동 재훈련·배포 |

## ML 라이프사이클

`
[비즈니스 목표 정의]
        ↓
[데이터 수집·준비]  → 피처 스토어 (Feature Store)
        ↓
[모델 훈련·실험]   → 실험 추적 (MLflow, W&B)
        ↓
[모델 평가·검증]   → 자동화된 성능 임계값 체크
        ↓
[모델 레지스트리]  → 버전 관리, A/B 배포 준비
        ↓
[서빙·배포]       → REST API, gRPC, Batch
        ↓
[모니터링]        → 데이터 드리프트, 모델 성능 추적
        ↓
[재훈련 트리거]   → 드리프트 감지 시 자동 재훈련
`

## 주요 MLOps 도구

| 역할 | 도구 |
|---|---|
| 실험 추적 | MLflow, Weights & Biases, Neptune.ai |
| 피처 스토어 | Feast, Tecton, AWS SageMaker Feature Store |
| 파이프라인 오케스트레이션 | Kubeflow, Airflow, ZenML |
| 모델 서빙 | BentoML, Seldon, TensorFlow Serving, Triton |
| 모니터링 | Evidently AI, Arize AI, Grafana |

## Related Terms
- [[Model-Training-and-Serving]] — MLOps 파이프라인의 핵심 두 단계
- [[ML-Engineering-Principles]] — MLOps를 가이드하는 원칙

## References
- [MLOps Principles](https://ml-ops.org/)
- [Google MLOps Whitepaper](https://cloud.google.com/resources/mlops-whitepaper)
