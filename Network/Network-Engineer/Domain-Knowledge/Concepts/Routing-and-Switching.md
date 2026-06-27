# Routing and Switching

## Overview
라우팅(Routing)과 스위칭(Switching)은 네트워크에서 데이터 패킷이 올바른 목적지로 전달되는 핵심 메커니즘이다.

## 스위칭 (Switching) — Layer 2

스위치는 MAC 주소를 기반으로 같은 네트워크 내에서 프레임을 전달한다.

### 핵심 개념
- **MAC Address Table**: 포트별 MAC 주소 학습 및 저장
- **VLAN (Virtual LAN)**: 물리 네트워크를 논리적으로 분리
  `
  VLAN 10: 개발팀 PC
  VLAN 20: 재무팀 PC
  VLAN 30: 서버
  → 같은 스위치에 연결되어도 트래픽 격리
  `
- **STP (Spanning Tree Protocol)**: 루프 방지
- **Link Aggregation (LAG)**: 여러 포트를 묶어 대역폭 증가

## 라우팅 (Routing) — Layer 3

라우터는 IP 주소를 기반으로 다른 네트워크 간에 패킷을 전달한다.

### 라우팅 프로토콜
| 프로토콜 | 유형 | 사용 상황 |
|---|---|---|
| **OSPF** | IGP, Link-State | 기업 내부 네트워크 |
| **EIGRP** | IGP, Cisco 독점 | Cisco 전용 환경 |
| **BGP** | EGP, Path-Vector | 인터넷 ISP 간 라우팅 |
| **Static Route** | 수동 설정 | 소규모·예측 가능한 경로 |

### BGP (Border Gateway Protocol)
- 인터넷의 라우팅 프로토콜 (AS 간 경로 교환)
- ISP, 대형 엔터프라이즈 필수 기술
- AS(Autonomous System) 번호로 네트워크 식별

## IP 주소 체계

`
Private IP 대역 (RFC 1918):
10.0.0.0/8       → 기업 내부 (대규모)
172.16.0.0/12    → 기업 내부 (중규모)
192.168.0.0/16   → 가정·소규모 사무실

서브넷 예시:
192.168.1.0/24 → 192.168.1.1 ~ 192.168.1.254 (254개 호스트)
`

## Related Terms
- [[Network-Architecture]] — 라우팅·스위칭이 구현되는 전체 구조
- [[BGP]] — 인터넷 라우팅의 핵심 프로토콜

## References
- [Cisco — OSPF Configuration Guide](https://www.cisco.com/c/en/us/td/docs/ios/12_4/ip/configuration/guide/fipiospf.html)
