# DevOps Culture

## Overview
DevOps는 도구보다 문화다. 개발(Dev)과 운영(Ops)의 사일로(Silo)를 허물고 공동 책임·협업·자동화·지속적 학습을 중심으로 하는 조직 철학이다.

## CALMS 프레임워크 (DevOps의 5대 원칙)

| 원칙 | 설명 | 실천 방법 |
|---|---|---|
| **Culture** | 공유 책임, 신뢰 기반 협업 | Blameless Postmortem |
| **Automation** | 반복 수동 작업 자동화 | CI/CD, IaC, 테스트 자동화 |
| **Lean** | 낭비 제거, 흐름 최적화 | 배치 크기 감소, WIP 제한 |
| **Measurement** | 데이터 기반 개선 | DORA Metrics, 모니터링 |
| **Sharing** | 지식·도구·책임 공유 | 런북, 포스트모템 공개 |

## DORA Metrics (DevOps 성과 측정)

| 지표 | 설명 | Elite 기준 |
|---|---|---|
| **Deployment Frequency** | 배포 빈도 | 주 1회 이상 |
| **Lead Time for Changes** | 코드 커밋 → 프로덕션 소요 시간 | 하루 이하 |
| **Change Failure Rate** | 배포 후 실패 비율 | 15% 이하 |
| **Time to Restore** | 장애 복구 시간 | 1시간 이하 |

## Blameless Postmortem (무결책 포스트모템)
- 장애 발생 시 개인 책임 추궁이 아닌 시스템·프로세스 개선에 집중
- 5 Whys로 근본 원인(Root Cause) 파악
- 재발 방지 Action Item 도출 및 공개

## Related Terms
- [[CI-CD-Pipeline]] — Automation 원칙의 핵심 구현
- [[Infrastructure-as-Code]] — Automation + Measurement 실현

## References
- [DORA Research Program](https://dora.dev/)
- [The Phoenix Project (Gene Kim 저)](https://itrevolution.com/product/the-phoenix-project/)
