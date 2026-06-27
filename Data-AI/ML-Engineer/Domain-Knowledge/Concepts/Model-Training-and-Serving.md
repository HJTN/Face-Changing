# Model Training and Serving

## Overview
ML 엔지니어의 핵심 역할은 모델을 효율적으로 훈련하고 안정적으로 서빙하는 것이다. 데이터 과학자가 만든 실험용 코드를 프로덕션 수준으로 끌어올리는 과정이다.

## 모델 훈련 최적화

### 분산 훈련 (Distributed Training)
- **Data Parallelism**: 같은 모델을 여러 GPU에 복제, 데이터 분산
- **Model Parallelism**: 거대 모델을 여러 GPU에 분할 (LLM 훈련)
- 프레임워크: PyTorch DDP, Horovod, DeepSpeed

### 하이퍼파라미터 튜닝
- **Grid Search**: 모든 조합 탐색 (소규모)
- **Random Search**: 무작위 샘플링 (대규모)
- **Bayesian Optimization**: 이전 결과로 다음 탐색 유도 (Optuna, Ray Tune)

## 모델 서빙 방식

### Online Serving (실시간)
- REST API / gRPC 엔드포인트
- 요청당 예측, 낮은 지연시간 필요
- 도구: FastAPI + BentoML, TensorFlow Serving, Triton

### Batch Serving (배치)
- 대량 데이터에 대한 오프라인 예측
- 마케팅 스코어링, 추천 사전 계산
- 도구: Spark, Airflow + 모델 로드

### Edge Serving (엣지)
- 모바일·IoT 기기에서 직접 추론
- 모델 경량화: ONNX, TFLite, CoreML 변환
- 양자화(Quantization): FP32 → INT8 (정확도 소폭 감소, 속도 4배)

## 모델 버전 관리 및 배포

| 전략 | 설명 | 위험도 |
|---|---|---|
| **Blue-Green** | 구버전 유지, 신버전 동시 배포 후 전환 | 낮음 |
| **Canary** | 트래픽 5% → 20% → 100% 단계적 전환 | 낮음 |
| **Shadow** | 신모델을 실제 요청으로 병행 실행 (로그만 저장) | 없음 |
| **A/B Test** | 두 모델에 동등 트래픽 분배, 성능 비교 | 낮음 |

## Related Terms
- [[MLOps-Lifecycle]] — 훈련·서빙을 포함하는 전체 MLOps 흐름
- [[ML-Engineering-Principles]] — 훈련·서빙 설계 원칙

## References
- [Chip Huyen — Designing Machine Learning Systems](https://www.oreilly.com/library/view/designing-machine-learning/9781098107956/)
