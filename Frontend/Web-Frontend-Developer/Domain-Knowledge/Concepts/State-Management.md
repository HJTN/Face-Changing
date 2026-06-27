# State Management

## Overview
상태 관리(State Management)는 애플리케이션 내의 데이터(상태)를 저장하고 변경하며 컴포넌트 간에 공유하는 방법론이다. UI의 복잡도가 높아질수록 상태 관리가 아키텍처의 핵심이 된다.

## 상태의 종류

| 종류 | 설명 | 예시 |
|---|---|---|
| **Local State** | 특정 컴포넌트에만 필요 | 모달 열림/닫힘, 인풋 값 |
| **Shared State** | 여러 컴포넌트가 공유 | 장바구니, 로그인 유저 정보 |
| **Server State** | 서버에서 패칭한 데이터 | 상품 목록, 댓글 |
| **URL State** | URL 파라미터·쿼리 | 현재 페이지, 필터 조건 |

## 상태 관리 솔루션

### 내장 솔루션
- **React useState** — 로컬 상태 (단순 컴포넌트)
- **React useReducer** — 복잡한 로컬 상태 로직
- **React Context API** — 컴포넌트 트리 전체에 상태 공유

### 외부 라이브러리
| 라이브러리 | 특징 | 추천 상황 |
|---|---|---|
| **Redux Toolkit** | 예측 가능, DevTools 강력 | 대규모 앱, 팀 협업 |
| **Zustand** | 간단한 API, 보일러플레이트 없음 | 중소규모 앱 |
| **Jotai / Recoil** | 원자 단위 상태 | 세분화된 상태 관리 |
| **TanStack Query** | 서버 상태 전문 | API 데이터 캐싱·동기화 |

## Flux 패턴 (Redux의 기반)
`
Action → Dispatcher → Store → View
           ↑______________________↓ (사용자 이벤트)
`

## Related Terms
- [[Component-Architecture]] — 상태를 어느 컴포넌트에 둘지 결정하는 설계
- [[Browser-Rendering-Pipeline]] — 상태 변경이 렌더링을 트리거하는 과정

## References
- [Redux Toolkit 공식 문서](https://redux-toolkit.js.org/)
- [TanStack Query](https://tanstack.com/query/latest)
