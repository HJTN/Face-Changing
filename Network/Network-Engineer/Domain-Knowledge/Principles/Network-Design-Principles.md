# Network Design Principles

## Overview
네트워크 설계는 성능·가용성·보안·확장성·관리 용이성의 균형을 맞추는 엔지니어링 과제다.

## 핵심 설계 원칙

### 1. Hierarchical Design (계층적 설계)
3계층 구조로 복잡도를 관리한다:
- **Core Layer** — 고속 스위칭, 트래픽 집중 처리
- **Distribution Layer** — 정책 적용, 라우팅
- **Access Layer** — 엔드 디바이스 연결

### 2. Redundancy (이중화)
단일 장애 지점(SPOF) 제거:
- 링크 이중화: 두 개 업링크 (Link Aggregation or Dual-homing)
- 장비 이중화: HSRP/VRRP로 게이트웨이 이중화
- ISP 이중화: 두 개 ISP 회선 (BGP Multi-homing)

### 3. Scalability (확장성)
- IP 주소 계획: 서브넷 여유 공간 확보
- 모듈식 설계: 새 부서·건물 추가 시 기존 네트워크 영향 최소화

### 4. Security by Design
- 최소 권한 VLAN 분리
- ACL(Access Control List)로 트래픽 필터링
- 네트워크 세그먼트화로 침해 범위 제한

### 5. Manageability (관리 용이성)
- 일관된 네이밍 컨벤션 (sw-floor1-01, rt-core-01)
- 네트워크 다이어그램 항상 최신 유지
- SNMP/NetFlow로 트래픽 가시성 확보

## 문서화 원칙
- L2 다이어그램: 스위치·포트·VLAN 연결
- L3 다이어그램: 라우터·IP 대역·라우팅 프로토콜

## Related Terms
- [[Network-Architecture]] — 원칙이 적용되는 전체 구조
- [[Routing-and-Switching]] — 원칙의 기술적 구현

## References
- [Cisco Design Zone](https://www.cisco.com/c/en/us/solutions/enterprise/design-zone.html)
