# Cloud Service Models

## Overview
클라우드 서비스 모델은 클라우드 공급자가 관리하는 범위에 따라 IaaS·PaaS·SaaS·FaaS로 구분된다. 무엇을 직접 관리하고 무엇을 위임할지 결정하는 기준이다.

## 서비스 모델 비교

`
책임 범위 (아래로 내려갈수록 공급자가 더 많이 관리)

               개발자 관리    공급자 관리
On-Premises:   ████████████   없음
IaaS:          ████████       ████ (하드웨어, 네트워크, 스토리지)
PaaS:          ████           ████████ (+OS, 런타임, 미들웨어)
FaaS:          ██             ██████████ (+서버 관리, 스케일링)
SaaS:          없음            ████████████ (전체)
`

## 각 모델 상세

### IaaS (Infrastructure as a Service)
- AWS EC2, Google Compute Engine, Azure VMs
- VM, 스토리지, 네트워킹 제공
- 사용 시: 기존 앱 리프트앤시프트, 세밀한 OS 제어 필요

### PaaS (Platform as a Service)
- AWS Elastic Beanstalk, Google App Engine, Heroku
- OS·런타임 관리 불필요, 코드만 배포
- 사용 시: 빠른 개발, 인프라 전문가 없는 팀

### FaaS (Function as a Service) / Serverless
- AWS Lambda, Google Cloud Functions, Azure Functions
- 함수 단위 실행, 유휴 시 비용 없음
- 사용 시: 이벤트 기반 처리, 변동 부하

### SaaS (Software as a Service)
- Gmail, Salesforce, Slack
- 최종 사용자 소프트웨어

## 클라우드 주요 벤더

| 벤더 | 시장점유율 | 강점 |
|---|---|---|
| **AWS** | ~33% | 가장 풍부한 서비스, 성숙한 생태계 |
| **Azure** | ~22% | 엔터프라이즈, Microsoft 통합 |
| **GCP** | ~11% | 데이터/AI, Kubernetes 원조 |

## Related Terms
- [[Cloud-Native-Architecture]] — 클라우드 모델을 최대한 활용하는 설계
- [[Well-Architected-Framework]] — AWS의 클라우드 설계 모범 사례

## References
- [AWS Cloud Computing Concepts](https://aws.amazon.com/what-is-cloud-computing/)
