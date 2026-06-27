# Zero Trust Security

## Overview
제로 트러스트(Zero Trust)는 \"절대 신뢰하지 말고, 항상 검증하라(Never Trust, Always Verify)\" 원칙에 기반한 보안 모델이다. 2010년 Forrester의 John Kindervag가 제안했으며, NIST SP 800-207로 표준화되었다.

## 전통 vs Zero Trust

| 항목 | 전통적 경계 보안 | Zero Trust |
|---|---|---|
| 전제 | 내부 = 신뢰, 외부 = 불신 | 내부도 외부도 신뢰하지 않음 |
| 접근 제어 | 네트워크 위치 기반 | ID + 디바이스 + 컨텍스트 기반 |
| 적합성 | 사무실 중심 환경 | 클라우드·원격근무 환경 |

## Zero Trust 5대 원칙

1. **명시적 검증**: 모든 요청에 대해 ID, 위치, 디바이스, 서비스, 워크로드, 이상 행동 검증
2. **최소 권한 접근**: 필요한 최소한의 권한만 부여 (Just-In-Time, Just-Enough-Access)
3. **침해 가정**: 네트워크가 이미 침해되었다고 가정하고 설계
4. **마이크로 세그멘테이션**: 네트워크를 작은 구역으로 분리, 측면 이동 차단
5. **지속적 모니터링**: 접속 후에도 지속적으로 이상 행동 감시

## ZTNA (Zero Trust Network Access) 구현

`
사용자 요청
    ↓
ID 인증 (MFA + SSO)
    ↓
디바이스 상태 확인 (패치 여부, 보안 소프트웨어)
    ↓
컨텍스트 평가 (위치, 시간, 위험도)
    ↓
최소 권한 접근 허용 (전체 네트워크 X, 특정 앱 O)
    ↓
지속적 세션 모니터링
`

## Related Terms
- [[Defense-in-Depth]] — Zero Trust를 보완하는 전통적 심층 방어
- [[Network-Security-Architecture]] — Zero Trust 구현의 실제 아키텍처

## References
- [NIST SP 800-207 — Zero Trust Architecture](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-207.pdf)
- [Microsoft Zero Trust Guidance](https://www.microsoft.com/en-us/security/business/zero-trust)
