# Service Level Management

## Overview
서비스 수준 관리는 서비스 신뢰성 목표를 정의·측정·개선하는 체계다. Google SRE가 정립한 SLI/SLO/SLA 개념을 통해 신뢰성을 엔지니어링의 관점으로 접근한다.

## SLI / SLO / SLA 계층

`
SLA (Service Level Agreement)
  ↓ 외부 고객과의 계약 (법적 구속력)
SLO (Service Level Objective)
  ↓ 내부 달성 목표 (SLA보다 엄격하게 설정)
SLI (Service Level Indicator)
  ↓ 실제 측정 지표 (SLO 달성 여부의 근거)
`

### SLI (측정 지표) 예시
- **가용성**: 성공 응답 수 / 전체 요청 수 × 100%
- **지연시간**: 95th 백분위 응답 시간 < 200ms
- **처리량**: 초당 요청 수 > 1,000 RPS
- **오류율**: 5xx 응답 비율 < 0.1%

### SLO (목표) 예시
- "가용성 SLO: 99.9% (월 43.8분 다운타임 허용)"
- "P95 지연 SLO: 200ms 이하"

### SLA (계약) 예시
- "가용성 99.9% 미달 시 서비스 크레딧 10% 환불"

## 가용성 숫자 읽기

| 가용성 | 연간 다운타임 | 월간 다운타임 |
|---|---|---|
| 99% (Two 9s) | 87.6시간 | 7.2시간 |
| 99.9% (Three 9s) | 8.7시간 | 43.8분 |
| 99.99% (Four 9s) | 52.6분 | 4.4분 |
| 99.999% (Five 9s) | 5.3분 | 26.3초 |

## Related Terms
- [[Error-Budget]] — SLO를 초과한 신뢰성 여유분을 혁신에 투자
- [[Monitoring-and-Alerting]] — SLI를 실시간 측정하는 도구

## References
- [Google SRE Book — Service Level Objectives](https://sre.google/sre-book/service-level-objectives/)
