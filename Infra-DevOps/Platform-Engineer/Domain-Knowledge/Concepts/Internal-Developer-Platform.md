# Internal Developer Platform (IDP)

## Overview
IDP(내부 개발자 플랫폼)는 인프라·운영 작업을 추상화해 개발자가 셀프서비스로 개발 환경·배포·모니터링을 이용할 수 있게 하는 플랫폼이다. Platform Engineering 팀의 핵심 산출물이다.

## IDP가 해결하는 문제

### 문제: 인지 부하(Cognitive Load)
개발자가 앱 개발에 집중해야 하는데, 다음 모두를 알아야 한다:
- Kubernetes YAML 작성
- Helm Chart 커스터마이징
- CI/CD 파이프라인 설정
- 모니터링 대시보드 설정
- 보안 스캔 통과 방법

### 해결: Golden Path (황금 경로)
- 플랫폼 팀이 검증된 표준 경로 제공
- 개발자는 앱 코드만 작성하면 나머지는 플랫폼이 처리

## IDP 핵심 구성요소

| 구성요소 | 역할 | 도구 예시 |
|---|---|---|
| **Self-Service Portal** | 개발자 진입점 | Backstage (Spotify OSS) |
| **CI/CD Orchestration** | 파이프라인 추상화 | GitHub Actions, Tekton |
| **Environments** | Dev/Staging/Prod 환경 제공 | Kubernetes Namespaces |
| **Secrets Management** | 비밀 값 안전 관리 | Vault, AWS Secrets Manager |
| **Observability** | 모니터링 자동 설정 | Prometheus, Grafana |
| **Service Catalog** | 검증된 서비스 템플릿 | Backstage Software Catalog |

## Related Terms
- [[Platform-Engineering]] — IDP를 만드는 팀과 원칙
- [[Golden-Path-Principle]] — IDP 설계의 핵심 철학

## References
- [Backstage — Spotify](https://backstage.io/)
- [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/)
