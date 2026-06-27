# Threat Modeling

## Overview
위협 모델링(Threat Modeling)은 시스템의 잠재적 보안 위협을 체계적으로 식별·분석하고 대응 방안을 설계하는 방법론이다. 개발 초기에 수행할수록 수정 비용이 낮아진다.

## STRIDE 프레임워크 (Microsoft)

| 위협 | 설명 | 대응 |
|---|---|---|
| **S**poofing | 다른 사용자나 시스템으로 위장 | 인증 (MFA, 디지털 서명) |
| **T**ampering | 데이터 무단 변조 | 무결성 검증 (HMAC, 디지털 서명) |
| **R**epudiation | 행위 부인 ("나 안 했어") | 감사 로그, 부인방지 서명 |
| **I**nformation Disclosure | 민감 정보 유출 | 암호화, 접근 제어 |
| **D**enial of Service | 서비스 중단 | Rate Limiting, 스케일링 |
| **E**levation of Privilege | 권한 상승 | 최소 권한 원칙, RBAC |

## DREAD 위협 평가 점수

| 기준 | 설명 |
|---|---|
| **D**amage | 피해 규모 (1-10) |
| **R**eproducibility | 재현 가능성 |
| **E**xploitability | 공격 난이도 |
| **A**ffected Users | 영향 받는 사용자 수 |
| **D**iscoverability | 발견 용이성 |

## 위협 모델링 프로세스

1. **다이어그램** — DFD (Data Flow Diagram)로 시스템 구성요소, 데이터 흐름, 신뢰 경계 표시
2. **위협 식별** — STRIDE 체계로 각 구성요소의 잠재 위협 나열
3. **위협 완화** — 각 위협에 대한 대응 방안 설계
4. **검증** — 대응이 충분한지 확인

## 도구
- **Microsoft Threat Modeling Tool** — STRIDE 자동화
- **OWASP Threat Dragon** — 오픈소스 위협 모델링
- **Draw.io** — DFD 다이어그램 작성

## Related Terms
- [[Secure-SDLC]] — 위협 모델링을 개발 프로세스에 통합
- [[Defense-in-Depth]] — 위협 모델링 결과를 계층적 방어로 구현

## References
- [OWASP Threat Modeling](https://owasp.org/www-community/Threat_Modeling)
- [Microsoft Threat Modeling](https://learn.microsoft.com/en-us/azure/security/develop/threat-modeling-tool)
