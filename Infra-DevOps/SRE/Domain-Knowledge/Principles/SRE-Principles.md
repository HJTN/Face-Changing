# SRE Principles

## Overview
SRE(Site Reliability Engineering)는 Google이 2003년 시작한 운영 방식으로, 소프트웨어 엔지니어링 원칙을 인프라·운영에 적용해 대규모 시스템의 신뢰성을 확보한다.

## 5대 핵심 원칙

### 1. Embracing Risk (위험 수용)
- 100% 가용성은 불가능하고 비용도 지나치게 크다
- SLO로 "충분히 신뢰할 수 있는" 수준 정의 → [[Error-Budget]]으로 혁신과 안정성 균형

### 2. Eliminating Toil (토일 제거)
- 수동·반복·자동화 가능한 작업(Toil)을 50% 이하로 유지
- 토일이 50% 초과 시 엔지니어링 역량이 낭비됨

### 3. Monitoring Distributed Systems (모니터링)
- 4 Golden Signals: **Latency, Traffic, Errors, Saturation**
- Alerting 원칙: 사람이 개입해야 할 상황에만 알람, 나머지는 자동 처리

### 4. Release Engineering (릴리즈 엔지니어링)
- 배포를 엔지니어링 문제로 다룸
- Canary Release, Blue-Green, Progressive Delivery

### 5. Simplicity (단순성)
- 복잡한 시스템은 장애가 많다
- 기능 삭제도 신뢰성 개선 방법
- "소프트웨어 엔트로피"를 관리하라

## 4 Golden Signals 상세

| Signal | 의미 | 측정 방법 |
|---|---|---|
| **Latency** | 요청 처리 시간 (성공/실패 분리) | P50, P95, P99 |
| **Traffic** | 시스템 부하 | RPS, DAU |
| **Errors** | 실패 요청 비율 | 5xx%, Exception Rate |
| **Saturation** | 리소스 포화도 | CPU 80%+, 디스크 90%+ |

## Related Terms
- [[Service-Level-Management]] — SRE의 SLI/SLO/SLA 체계
- [[Error-Budget]] — SRE의 혁신-신뢰성 균형 도구

## References
- [Google SRE Book (무료 온라인)](https://sre.google/sre-book/table-of-contents/)
- [Google SRE Workbook](https://sre.google/workbook/table-of-contents/)
