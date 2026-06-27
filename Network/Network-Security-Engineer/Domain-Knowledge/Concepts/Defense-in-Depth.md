# Defense in Depth

## Overview
심층 방어(Defense in Depth)는 단일 보안 계층에 의존하지 않고 여러 겹의 보안 제어를 중첩 적용해 공격자가 모든 계층을 뚫어야만 목표에 도달할 수 있게 하는 전략이다.

## 보안 계층 구조

`
[7계층 심층 방어]

L7 데이터        — 암호화(AES-256), DLP, 데이터 분류
L6 애플리케이션  — WAF, SAST/DAST, 시큐어 코딩
L5 호스트        — EDR, 패치 관리, 최소 권한 계정
L4 내부 네트워크 — IDS/IPS, 마이크로 세그멘테이션
L3 경계          — 방화벽, DMZ, 침입 탐지
L2 물리          — 출입 통제, 잠금 장치, CCTV
L1 정책·절차     — 보안 정책, 직원 교육, 사고 대응
`

## 핵심 방어 기술

| 기술 | 역할 |
|---|---|
| **Firewall** | 네트워크 경계 트래픽 필터링 (IP, 포트 기반) |
| **NGFW (Next-Gen Firewall)** | 애플리케이션 인식, 사용자 기반 정책 |
| **WAF (Web App Firewall)** | HTTP 레이어 공격 차단 (SQLi, XSS, OWASP Top 10) |
| **IDS/IPS** | 침입 탐지/차단 시스템 |
| **DLP (Data Loss Prevention)** | 민감 데이터 유출 방지 |
| **EDR (Endpoint Detection & Response)** | 엔드포인트 위협 탐지·대응 |

## Related Terms
- [[Network-Security-Architecture]] — 심층 방어의 실제 구현 구조
- [[Zero-Trust-Security]] — 심층 방어의 현대적 진화

## References
- [NSA — Defense in Depth](https://media.defense.gov/2021/Aug/03/2002820869/-1/-1/1/CTR_CYBERSECURITY_TECHNICAL_REPORT_22.PDF)
