# End-to-End Development

## Overview
End-to-End(E2E) 개발은 기능 요구사항을 사용자 인터페이스부터 데이터베이스까지 전체 스택에 걸쳐 혼자 구현하는 방식이다. 풀스택 개발자의 핵심 역량이자 스타트업에서 특히 요구되는 능력이다.

## E2E 개발 흐름 예시 (로그인 기능)

`
1. [UI]       React 로그인 폼 컴포넌트 작성
2. [API]      POST /auth/login 엔드포인트 정의
3. [Auth]     JWT 토큰 생성 및 검증 로직
4. [DB]       users 테이블 비밀번호 해시 조회
5. [Security] bcrypt 비교, Rate Limiting 적용
6. [UI]       토큰 저장 (httpOnly Cookie) 및 리다이렉트
`

## 풀스택 개발자의 균형감각

### 언제 각 레이어에 더 집중하는가
- **UX 병목**: 프론트엔드 컴포넌트·상태 최적화
- **성능 병목**: 백엔드 쿼리·캐싱 최적화
- **데이터 모델 변경**: DB 마이그레이션·API 계약 수정

### T자형 vs π자형 인재
- **T자형**: 한 레이어 전문성 + 다른 레이어 폭넓은 이해
- **π자형**: 두 레이어 전문성 (ex: 프론트엔드 + 백엔드 모두 심층)

## Related Terms
- [[Full-Stack-Architecture]] — E2E 개발을 위한 구조적 기반
- [[Separation-of-Concerns]] — E2E 개발에서도 레이어 분리는 필수

## References
- [The Pragmatic Fullstack Developer](https://www.freecodecamp.org/news/what-is-a-full-stack-developer/)
