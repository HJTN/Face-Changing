# CI/CD Pipeline

## Overview
CI/CD는 코드 변경부터 프로덕션 배포까지의 과정을 자동화하는 파이프라인이다. CI(Continuous Integration)는 코드 통합과 검증을, CD(Continuous Delivery/Deployment)는 배포 자동화를 담당한다.

## CI/CD 파이프라인 단계

`
개발자 Push → 트리거
        ↓
[Build]   소스 컴파일, 의존성 설치
        ↓
[Test]    단위 테스트, 통합 테스트, 린팅
        ↓
[SAST]   정적 보안 분석 (SonarQube, Snyk)
        ↓
[Build Image] Docker 이미지 빌드 & 레지스트리 Push
        ↓
[Deploy to Staging]  스테이징 환경 배포
        ↓
[E2E Test]  통합·UI 테스트
        ↓
[Deploy to Production]  프로덕션 배포 (자동 or 승인 후)
`

## CI vs CD 구분

| 구분 | 의미 | 핵심 |
|---|---|---|
| **CI** (Continuous Integration) | 코드를 자주 병합하고 자동으로 검증 | 빠른 피드백 |
| **CD** (Continuous Delivery) | 언제든 배포 가능한 상태 유지 | 수동 프로덕션 배포 |
| **CD** (Continuous Deployment) | 테스트 통과 즉시 자동 프로덕션 배포 | 완전 자동화 |

## 주요 도구

| 카테고리 | 도구 |
|---|---|
| CI/CD 플랫폼 | GitHub Actions, GitLab CI, Jenkins, CircleCI |
| 컨테이너 레지스트리 | Docker Hub, AWS ECR, GitHub Container Registry |
| 아티팩트 저장소 | Nexus, Artifactory |
| 배포 | ArgoCD, Flux (GitOps), AWS CodeDeploy |

## Related Terms
- [[Containerization]] — CI/CD에서 Docker로 일관된 빌드 환경
- [[Infrastructure-as-Code]] — 파이프라인 자체도 코드로 관리

## References
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [DORA Metrics](https://dora.dev/guides/dora-metrics-four-keys/)
