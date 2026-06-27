# Information Architecture for Technical Writing

## Overview
기술 문서에서의 정보 아키텍처(IA)는 사용자가 필요한 정보를 빠르게 찾고 이해할 수 있도록 정보를 구조화·분류·표현하는 방법이다.

## 기술 문서의 IA 원칙

### 1. 독자 중심 구조 (User-Centered Structure)
- 독자의 목표·역할·경험 수준에 따라 구조 결정
- 초보자 → 튜토리얼, 숙련자 → 레퍼런스

### 2. 점진적 공개 (Progressive Disclosure)
- 핵심 내용 먼저, 세부사항은 나중에
- 깊이 읽고 싶은 독자를 위한 링크 제공

### 3. 검색 가능성 (Findability)
- 명확한 제목·부제목 계층 (H1 → H2 → H3)
- 검색 최적화: 독자가 검색할 키워드가 제목에 포함되어야 함
- 사이드바 내비게이션, 태그, 색인

## 문서 사이트 구조 예시

`
docs/
├── getting-started/
│   ├── installation.md
│   ├── quick-start.md
│   └── first-project.md
├── tutorials/
│   ├── build-a-todo-app.md
│   └── connect-to-database.md
├── how-to/
│   ├── configure-authentication.md
│   └── set-up-ci-cd.md
├── reference/
│   ├── api-endpoints.md
│   └── configuration-options.md
└── explanation/
    ├── architecture-overview.md
    └── design-decisions.md
`

## 문서 품질 지표
- **Completeness**: 필요한 모든 정보 포함
- **Accuracy**: 코드·명령어가 실제 동작
- **Currency**: 최신 제품 버전 반영
- **Clarity**: 모호함 없이 이해 가능

## Related Terms
- [[Documentation-Types]] — 정보 아키텍처가 정의하는 문서 유형
- [[Docs-as-Code]] — IA를 Git 저장소 구조로 구현

## References
- [Google Developer Documentation Style Guide](https://developers.google.com/style)
