# Well-Architected Framework

## Overview
AWS Well-Architected Framework는 AWS가 제공하는 클라우드 아키텍처 모범 사례 가이드다. 6개 기둥으로 클라우드 워크로드의 설계·운영·개선을 평가한다. Azure·GCP도 유사한 프레임워크를 제공한다.

## 6개 기둥 (Pillars)

### 1. Operational Excellence (운영 우수성)
- 코드로 운영, 작은 변경, 실패에서 학습
- 핵심: CI/CD, Runbook, Postmortem

### 2. Security (보안)
- 모든 레이어에 보안 적용, 최소 권한 원칙, 암호화
- IAM 역할, VPC, WAF, KMS

### 3. Reliability (신뢰성)
- 장애 자동 복구, 수평 확장으로 가용성 확보
- Multi-AZ, Auto Scaling, Circuit Breaker

### 4. Performance Efficiency (성능 효율성)
- 상황에 맞는 컴퓨팅 유형 선택, 성능 지속 모니터링
- Lambda@Edge, ElastiCache, CloudFront

### 5. Cost Optimization (비용 최적화)
- 리소스 사용량 최적화, 불필요 용량 제거
- Reserved Instance, Savings Plans, Cost Explorer

### 6. Sustainability (지속 가능성, 2021 추가)
- 에너지 소비·탄소 발자국 최소화
- 효율적 코드, 불필요 리소스 제거

## 실용적 적용 방법
- AWS Well-Architected Tool로 기존 아키텍처 자가 평가
- 아키텍처 리뷰 시 체크리스트로 활용
- 신규 서비스 설계 시 6개 기둥 기준으로 검토

## Related Terms
- [[Cloud-Native-Architecture]] — WAF를 통과하는 아키텍처의 실제 구현
- [[Cloud-Service-Models]] — 기둥별 최적 서비스 선택 기준

## References
- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
