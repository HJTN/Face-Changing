# Infrastructure as Code (IaC)

## Overview
코드로서의 인프라(IaC)는 서버·네트워크·데이터베이스 등 인프라를 수동 작업이 아닌 코드로 정의하고 관리하는 방식이다. 인프라를 버전 관리·자동화·재현 가능하게 만든다.

## IaC 도구 비교

| 도구 | 방식 | 특징 | 사용 상황 |
|---|---|---|---|
| **Terraform** | 선언형, 멀티 클라우드 | HCL 언어, State 관리 | 클라우드 인프라 표준 |
| **Pulumi** | 선언형, 범용 언어 | Python/TypeScript/Go 사용 | 개발자 친화적 |
| **AWS CloudFormation** | 선언형, AWS 전용 | AWS 서비스와 완전 통합 | AWS 전용 환경 |
| **Ansible** | 절차형, 에이전트리스 | SSH 기반, YAML | 서버 설정·배포 |
| **Helm** | Kubernetes 전용 | K8s 리소스 패키징 | Kubernetes 배포 |

## Terraform 워크플로우

`ash
# 1. 초기화 (provider 플러그인 다운로드)
terraform init

# 2. 플랜 (변경사항 미리 보기)
terraform plan

# 3. 적용 (실제 인프라 생성/수정)
terraform apply

# 4. 제거
terraform destroy
`

## GitOps 원칙
IaC + Git = GitOps:
- 인프라 상태를 Git 저장소가 정의
- PR 승인 → 자동 인프라 변경 적용
- Rollback = git revert

## Related Terms
- [[CI-CD-Pipeline]] — IaC 코드 변경도 CI/CD로 자동 적용
- [[Containerization]] — Kubernetes 리소스를 IaC로 관리

## References
- [Terraform Documentation](https://developer.hashicorp.com/terraform/docs)
- [GitOps Principles](https://opengitops.dev/)
