# Component Architecture

## Overview
컴포넌트 아키텍처는 UI를 독립적이고 재사용 가능한 단위(컴포넌트)로 분리하는 설계 방식이다. React, Vue, Angular 등 현대 프론트엔드 프레임워크의 핵심 개념이다.

## 컴포넌트 설계 원칙

### 1. 단일 책임 원칙 (SRP)
하나의 컴포넌트는 하나의 역할만 담당한다.
- Bad: UserCard — 유저 데이터 fetch + 표시 + 삭제 버튼 + 폼 모두 포함
- Good: UserCard (표시만) + useUser hook (데이터 fetch) + DeleteUserButton (삭제만)

### 2. Props Down, Events Up
- 부모 → 자식: Props(데이터) 전달
- 자식 → 부모: 이벤트(콜백) 전달
- 전역 상태는 Context API 또는 상태관리 라이브러리 활용

### 3. Composition over Inheritance
상속보다 컴포넌트 합성을 사용한다.
`jsx
// 합성 패턴
<Card>
  <CardHeader>...</CardHeader>
  <CardBody>...</CardBody>
</Card>
`

## 컴포넌트 유형

| 유형 | 특징 | 예시 |
|---|---|---|
| **Presentational** | UI만 담당, Props 받아 렌더링 | Button, Avatar, Badge |
| **Container** | 데이터 로직 담당, 상태 관리 | UserListContainer |
| **Layout** | 배치·여백 담당 | PageLayout, Grid |
| **Page** | 라우트와 1:1 대응 | HomePage, ProfilePage |

## Related Terms
- [[State-Management]] — 컴포넌트 간 상태 공유 방법
- [[Virtual-DOM]] — React 컴포넌트가 효율적으로 렌더링되는 방법

## References
- [React — Thinking in React](https://react.dev/learn/thinking-in-react)
