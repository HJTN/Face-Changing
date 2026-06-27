# SOC Operations (Security Operations Center)

## Overview
SOC(보안 운영 센터)는 조직의 보안 위협을 24/7 모니터링·탐지·분석·대응하는 팀 또는 시설이다. 보안 분석가는 SOC에서 보안 이벤트를 분류하고 사고를 처리한다.

## SOC 팀 구조

| 계층 | 역할 |
|---|---|
| **Tier 1 (SOC Analyst)** | 알람 분류, 초기 분석, 에스컬레이션 |
| **Tier 2 (Incident Responder)** | 사고 조사, 포렌식, 대응 |
| **Tier 3 (Threat Hunter)** | 고급 위협 헌팅, 새 탐지 룰 개발 |
| **SOC Manager** | 팀 관리, 프로세스 개선, 보고 |

## 핵심 SOC 도구

### SIEM (Security Information and Event Management)
- 다양한 소스의 로그·이벤트를 수집·분석·상관
- 룰 기반 알람 + 이상 탐지 (ML 기반)
- **도구**: Splunk, IBM QRadar, Microsoft Sentinel

### SOAR (Security Orchestration, Automation and Response)
- 반복적인 대응 절차를 자동화 (Playbook)
- 알람 분류, 위협 인텔리전스 보강, IP 차단 자동화
- **도구**: Palo Alto XSOAR, Splunk SOAR

## SOC 알람 분류 프로세스

`
알람 수신
    ↓
초기 분류 (True Positive / False Positive?)
    ↓
    ├→ False Positive → 룰 조정 후 종결
    └→ True Positive → 심각도 분류
           ↓
    Critical/High → 즉시 에스컬레이션
    Medium/Low → 표준 대응 프로세스
`

## 주요 보안 지표
- **Dwell Time**: 침해 후 탐지까지의 시간 (업계 평균 ~200일, 목표: 24시간 이내)
- **MTTD**: 평균 탐지 시간
- **MTTR**: 평균 복구 시간

## Related Terms
- [[Threat-Intelligence]] — SOC 탐지를 강화하는 위협 정보
- [[Incident-Response-Principles]] — SOC 대응의 체계적 방법론

## References
- [SOC CMM — Security Operations Maturity Model](https://www.soc-cmm.com/)
