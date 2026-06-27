# Containerization

## Overview
컨테이너화(Containerization)는 애플리케이션과 그 실행에 필요한 모든 것(코드, 런타임, 라이브러리, 설정)을 컨테이너라는 격리된 단위로 패키징하는 기술이다. "내 컴퓨터에서는 되는데" 문제를 근본적으로 해결한다.

## VM vs Container

`
[VM]
┌─────────────────────────────────┐
│ App A  │ App B  │ App C        │
│ Bins   │ Bins   │ Bins         │
│ Guest OS│Guest OS│Guest OS     │  ← 각자 OS 보유 (수 GB)
│───────────────────────────────│
│          Hypervisor            │
│          Host OS               │
└─────────────────────────────────┘

[Container]
┌─────────────────────────────────┐
│ App A  │ App B  │ App C        │
│ Bins   │ Bins   │ Bins         │  ← OS 공유 (수 MB)
│───────────────────────────────│
│          Container Runtime     │
│          Host OS               │
└─────────────────────────────────┘
`

## Docker 핵심 개념

| 개념 | 설명 |
|---|---|
| **Image** | 컨테이너의 읽기 전용 템플릿 (레이어 기반) |
| **Container** | 이미지의 실행 인스턴스 |
| **Dockerfile** | 이미지 빌드 명세 |
| **Registry** | 이미지 저장소 (Docker Hub, ECR) |
| **Volume** | 컨테이너 외부 영구 데이터 저장 |

## Kubernetes 핵심 개념

| 개념 | 설명 |
|---|---|
| **Pod** | 컨테이너 실행 최소 단위 (1+개 컨테이너) |
| **Deployment** | Pod 복제본 관리, 롤링 업데이트 |
| **Service** | Pod 접근을 위한 안정적 네트워크 엔드포인트 |
| **Ingress** | 외부 트래픽을 Service로 라우팅 |
| **ConfigMap/Secret** | 환경 설정·비밀 값 분리 |

## Related Terms
- [[CI-CD-Pipeline]] — 컨테이너 이미지가 CI/CD의 배포 단위
- [[Infrastructure-as-Code]] — Kubernetes 리소스도 YAML 코드로 관리

## References
- [Docker 공식 문서](https://docs.docker.com/)
- [Kubernetes 공식 문서](https://kubernetes.io/docs/)
