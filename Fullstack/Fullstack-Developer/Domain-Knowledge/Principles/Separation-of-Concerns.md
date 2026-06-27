# Separation of Concerns (SoC)

## Overview
관심사 분리(Separation of Concerns)는 프로그램을 서로 다른 기능이나 역할(관심사)로 분리해 각 부분이 독립적으로 개발·테스트·유지보수 가능하게 하는 설계 원칙이다.

## 풀스택에서의 적용

### 레이어 분리
`
UI 컴포넌트:   "어떻게 보여줄까?"
API 레이어:    "어떻게 데이터를 주고받을까?"
비즈니스 로직: "어떤 규칙으로 처리할까?"
데이터 접근:   "어떻게 DB에서 읽고 쓸까?"
`

### 위반 사례와 개선

`javascript
// 나쁜 예: UI 컴포넌트가 SQL 직접 실행
function UserList() {
  const users = db.query("SELECT * FROM users WHERE active=1");
  return <ul>{users.map(u => <li>{u.name}</li>)}</ul>;
}

// 좋은 예: 역할 분리
// 1. Repository: DB 쿼리 담당
// 2. Service: 비즈니스 로직 담당  
// 3. Controller: HTTP 요청 처리
// 4. Component: UI 렌더링 담당
function UserList({ users }) { // Props로 데이터 주입
  return <ul>{users.map(u => <li>{u.name}</li>)}</ul>;
}
`

## 주요 이점
- **독립 개발**: 백엔드·프론트엔드 팀이 병렬 작업 가능
- **독립 테스트**: 레이어별 단위 테스트 가능
- **교체 용이**: DB를 바꿔도 UI는 영향 없음

## Related Terms
- [[Full-Stack-Architecture]] — SoC를 레이어로 구현한 구조
- [[Clean-Architecture]] — SoC를 극단적으로 적용한 아키텍처

## References
- [SoC — Wikipedia](https://en.wikipedia.org/wiki/Separation_of_concerns)
