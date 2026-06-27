# Secure SDLC (Software Development Lifecycle)

## Overview
Secure SDLC(보안 내재화 개발 방법론)는 소프트웨어 개발 생명주기의 각 단계에 보안 활동을 통합해 취약점을 사후가 아닌 설계·개발 단계에서 제거하는 접근 방식이다.

## Secure SDLC 단계별 보안 활동

| 단계 | 보안 활동 | 도구 |
|---|---|---|
| **요구사항** | 보안 요구사항 정의, 개인정보 영향 평가(PIA) | OWASP ASVS |
| **설계** | 위협 모델링, 아키텍처 보안 리뷰 | STRIDE, Threat Dragon |
| **개발** | 시큐어 코딩 가이드라인, SAST | Checkmarx, SonarQube |
| **빌드** | 소프트웨어 컴포지션 분석(SCA) | Snyk, OWASP Dependency-Check |
| **테스트** | DAST, 침투 테스트, 퍼징 | OWASP ZAP, Burp Suite |
| **배포** | 보안 설정 리뷰, 시크릿 스캔 | Trivy, truffleHog |
| **운영** | 취약점 모니터링, SIEM, IR | Splunk, PagerDuty |

## DevSecOps (보안 자동화)

`
Pull Request → SAST (정적 분석) → 빌드 → SCA (의존성 취약점) → 
배포 → DAST (동적 분석) → 프로덕션 → WAF + 모니터링
`

## OWASP Top 10 (2021)

| 순위 | 취약점 |
|---|---|
| 1 | Broken Access Control |
| 2 | Cryptographic Failures |
| 3 | Injection (SQLi, NoSQLi, LDAPi) |
| 4 | Insecure Design |
| 5 | Security Misconfiguration |
| 6 | Vulnerable Components |
| 7 | Authentication Failures |
| 8 | Integrity Failures |
| 9 | Logging & Monitoring Failures |
| 10 | SSRF |

## Related Terms
- [[Threat-Modeling]] — Secure SDLC 설계 단계의 핵심 활동
- [[Defense-in-Depth]] — Secure SDLC의 운영 단계 원칙

## References
- [OWASP Top 10 (2021)](https://owasp.org/Top10/)
- [Microsoft SDL](https://www.microsoft.com/en-us/securityengineering/sdl)
