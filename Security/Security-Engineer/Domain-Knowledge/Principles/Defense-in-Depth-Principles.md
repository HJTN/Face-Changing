# Defense in Depth — Security Engineering Perspective

## Overview
보안 엔지니어 관점에서의 심층 방어는 단일 보안 도구나 정책에 의존하지 않고 여러 독립적인 보안 계층을 구축해 공격자가 하나를 뚫어도 다음 계층에서 막히게 하는 전략이다.

## 보안 엔지니어의 심층 방어 구현

### 1. 예방 (Prevention)
- 입력 검증, 출력 인코딩 (Injection 방지)
- 최소 권한 원칙 (Least Privilege)
- 암호화 (저장 데이터, 전송 데이터)

### 2. 탐지 (Detection)
- 로그 수집 및 SIEM 분석
- 이상 행동 탐지 (UEBA)
- 취약점 스캐닝 (주기적)

### 3. 대응 (Response)
- 인시던트 대응 플레이북
- 자동화된 차단 (SOAR)
- 포렌식 분석

### 4. 복구 (Recovery)
- 백업 및 복구 절차
- BCP (업무 연속성 계획)
- 포스트모템 및 교훈 도출

## NIST Cybersecurity Framework (CSF)

`
Identify → Protect → Detect → Respond → Recover
  자산 식별     보안 통제    이상 탐지   사고 대응   서비스 복구
`

## 보안 지표 (Security Metrics)
- MTTD (Mean Time to Detect): 위협 탐지 평균 시간
- MTTR (Mean Time to Respond): 사고 대응 평균 시간
- 취약점 평균 패치 시간

## Related Terms
- [[Threat-Modeling]] — 방어해야 할 위협 식별
- [[Secure-SDLC]] — 개발 과정에서 심층 방어 구현

## References
- [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)
