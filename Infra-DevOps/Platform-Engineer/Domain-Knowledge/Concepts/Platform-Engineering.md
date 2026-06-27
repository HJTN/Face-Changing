# Platform Engineering

## Overview
플랫폼 엔지니어링은 개발자의 생산성을 높이기 위해 내부 플랫폼(IDP)을 설계·구축·운영하는 분야다. 2022년 Gartner는 플랫폼 엔지니어링을 Top 10 Strategic Tech Trend로 선정했다.

## Platform Engineering vs DevOps

| 항목 | DevOps | Platform Engineering |
|---|---|---|
| 목표 | 개발·운영 통합 | 개발자 생산성 향상 |
| 접근 | 모든 개발자가 인프라 담당 | 전문 팀이 플랫폼 제공 |
| 인지 부하 | 개발자에게 분산 | 플랫폼 팀이 집중 흡수 |
| 확장성 | 팀별 도구 난립 | 표준화된 플랫폼 제공 |

## 플랫폼 팀의 역할

### 제품으로서의 플랫폼 (Platform as a Product)
- 내부 개발자를 "고객"으로 대우
- 사용성·개발자 경험(DX) 우선
- NPS(Net Promoter Score)로 내부 만족도 측정

### 팀 구성
- Platform Engineer (인프라·K8s 전문)
- Developer Advocate (개발자 피드백 수집)
- Tech Writer (플랫폼 문서화)

## 주요 책임

1. **CI/CD 표준화** — 팀별 파이프라인 차이 제거
2. **인프라 자동화** — Terraform 모듈로 셀프서비스 인프라
3. **개발자 포털** — Backstage로 서비스 카탈로그·문서화
4. **보안 내재화** — DevSecOps, 정책 자동화
5. **관찰 가능성** — 표준 모니터링 스택 제공

## Related Terms
- [[Internal-Developer-Platform]] — 플랫폼 엔지니어링의 핵심 산출물
- [[Golden-Path-Principle]] — 플랫폼 팀이 제공하는 표준 경로

## References
- [platformengineering.org](https://platformengineering.org/)
- [Team Topologies (Skelton & Pais)](https://teamtopologies.com/)
