# Cloud Native Architecture

## Overview
클라우드 네이티브 아키텍처는 클라우드 환경의 탄력성·확장성·자동화를 최대한 활용하도록 처음부터 설계된 시스템 구조다. 단순히 클라우드에서 실행되는 것(Cloud-Hosted)이 아닌, 클라우드를 위해 설계된 것(Cloud-Native)을 의미한다.

## 핵심 패턴

### Microservices
- 기능을 독립 배포 가능한 서비스로 분리
- 서비스별 독립 스케일링, 독립 기술 스택 가능

### Containers & Orchestration
- Docker 컨테이너로 불변 인프라(Immutable Infrastructure) 실현
- Kubernetes로 컨테이너 스케줄링·복구·스케일링 자동화

### Serverless
- 서버 관리 없이 함수 단위 실행
- 이벤트 기반 처리, 자동 스케일링

### Service Mesh
- Istio, Linkerd로 서비스 간 통신 제어
- 트래픽 관리, 보안, 관찰 가능성을 인프라 레이어에서 처리

### Observability
- Metrics (Prometheus) + Logs (ELK Stack) + Traces (Jaeger)
- 분산 시스템에서 문제 진단을 위한 3대 신호

## CNCF (Cloud Native Computing Foundation) 랜드스케이프
- 1,000개 이상의 오픈소스 프로젝트
- 핵심: Kubernetes, Prometheus, Envoy, Fluentd, Jaeger

## Related Terms
- [[Cloud-Service-Models]] — 클라우드 네이티브를 구현하는 서비스 레이어
- [[Well-Architected-Framework]] — 클라우드 네이티브 설계 평가 기준

## References
- [CNCF Cloud Native Definition](https://github.com/cncf/toc/blob/main/DEFINITION.md)
