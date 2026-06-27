# Incident Response Principles

## Overview
인시던트 대응(Incident Response, IR)은 보안 사고가 발생했을 때 피해를 최소화하고 정상 운영을 빠르게 복구하기 위한 체계적 프로세스다. 사고 후 대응이 아닌, 사전 계획이 핵심이다.

## IR 6단계 프로세스 (NIST SP 800-61)

`
1. Preparation (준비)
   → IRP 수립, 팀 구성, 도구 준비, 교육·훈련

2. Identification (탐지·분류)
   → 보안 이벤트 탐지, 사고 여부 판단, 심각도 분류

3. Containment (격리)
   → 피해 확산 차단
   단기: 감염 시스템 네트워크 분리
   장기: 취약점 패치 없이 격리 유지

4. Eradication (제거)
   → 악성코드·백도어 제거, 취약점 패치

5. Recovery (복구)
   → 시스템 복구, 서비스 재시작, 모니터링 강화

6. Lessons Learned (교훈 도출)
   → 포스트모템, 재발 방지, IRP 업데이트
`

## 사고 심각도 분류

| 등급 | 기준 | 대응 시간 |
|---|---|---|
| **P1 (Critical)** | 데이터 유출, 랜섬웨어, 서비스 전면 중단 | 즉시 |
| **P2 (High)** | 권한 상승, 내부 시스템 침해 | 1시간 이내 |
| **P3 (Medium)** | 제한적 침해, 의심스러운 활동 | 4시간 이내 |
| **P4 (Low)** | 정책 위반, 포트 스캔 | 24시간 이내 |

## 포렌식 원칙

### Chain of Custody (증거 연속성)
- 증거 수집부터 분석·보고까지 모든 처리 과정 기록
- 법적 소송 시 증거 무결성 입증 필요

### 휘발성 순서 (Order of Volatility)
`
가장 먼저 수집: CPU 레지스터, 메모리 → 네트워크 연결 → 프로세스
나중에 수집: 로그 파일 → 디스크 이미지
`

## Related Terms
- [[SOC-Operations]] — 사고를 탐지하고 초기 분류하는 팀
- [[Threat-Intelligence]] — 사고 원인 파악과 귀속에 활용

## References
- [NIST SP 800-61 — Computer Security Incident Handling Guide](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf)
