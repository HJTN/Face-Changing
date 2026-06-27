# Network Security Architecture

## Overview
네트워크 보안 아키텍처는 조직의 네트워크를 사이버 위협으로부터 보호하기 위한 보안 통제 요소들의 체계적 배치 방식이다.

## 전통적 경계 보안 (Perimeter Security)

`
인터넷 ──→ [방화벽] ──→ DMZ ──→ [내부 방화벽] ──→ 내부 네트워크
                ↑
            "성벽 모델": 내부는 신뢰, 외부는 불신
`

### DMZ (비무장지대) 구성
- 외부 접근 서비스 (웹서버, 메일서버, DNS) 배치
- 내외부 방화벽 사이 격리 구간
- 내부 네트워크와 직접 통신 불가

## 현대적 보안 아키텍처: SASE

**SASE (Secure Access Service Edge)**:
- 네트워크 + 보안을 클라우드에서 통합 제공
- SD-WAN + CASB + ZTNA + FWaaS + SWG

### SD-WAN (Software-Defined WAN)
- 소프트웨어로 WAN 경로 제어
- 인터넷 회선 + MPLS 혼용으로 비용 최적화
- 애플리케이션별 트래픽 경로 자동 선택

## 주요 네트워크 보안 도구

| 도구 | 역할 |
|---|---|
| **SIEM** | 로그 수집·분석·위협 탐지 (Splunk, IBM QRadar) |
| **SOAR** | 보안 대응 자동화 (Playbook 기반) |
| **NAC** | 네트워크 접근 제어 (비인가 디바이스 차단) |
| **Honeypot** | 공격자 유인·분석 |

## Related Terms
- [[Defense-in-Depth]] — 보안 아키텍처의 설계 원칙
- [[Zero-Trust-Security]] — 경계 보안을 대체하는 현대적 모델

## References
- [Gartner SASE](https://www.gartner.com/en/information-technology/glossary/secure-access-service-edge)
