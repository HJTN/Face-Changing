# Network Architecture

## Overview
네트워크 아키텍처는 컴퓨터 네트워크의 구성요소(라우터·스위치·방화벽)와 그 연결 방식을 설계하는 분야다. 엔터프라이즈 네트워크부터 데이터센터·클라우드 네트워크까지 포괄한다.

## OSI 7계층 모델

| 계층 | 이름 | 프로토콜/장비 | 데이터 단위 |
|---|---|---|---|
| 7 | Application | HTTP, DNS, SMTP | 메시지 |
| 6 | Presentation | TLS/SSL, JPEG | 데이터 |
| 5 | Session | NetBIOS, RPC | 데이터 |
| 4 | Transport | TCP, UDP | 세그먼트 |
| 3 | Network | IP, ICMP, BGP | 패킷 |
| 2 | Data Link | Ethernet, Wi-Fi | 프레임 |
| 1 | Physical | 케이블, 광섬유 | 비트 |

## 네트워크 토폴로지

- **Star**: 모든 장치가 중앙 허브에 연결 (가장 일반적)
- **Mesh**: 각 노드가 여러 경로로 연결 (고가용성)
- **Spine-Leaf**: 데이터센터 표준. Spine = 코어 스위치, Leaf = 액세스 스위치

## 엔터프라이즈 네트워크 구조

`
인터넷
  ↓
방화벽 (Perimeter Firewall)
  ↓
DMZ (비무장지대 — 외부 서비스: 웹서버, 메일서버)
  ↓
방화벽 (Internal Firewall)
  ↓
내부 네트워크
├── User LAN (직원 PC)
├── Server Farm (내부 서버)
└── Management Network (관리 트래픽)
`

## Related Terms
- [[Routing-and-Switching]] — 네트워크 아키텍처의 핵심 구성요소
- [[Network-Design-Principles]] — 아키텍처 설계 원칙

## References
- [Cisco — Enterprise Network Architecture](https://www.cisco.com/c/en/us/solutions/enterprise-networks/)
