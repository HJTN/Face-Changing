# Design Systems

## Overview
디자인 시스템은 재사용 가능한 컴포넌트, 패턴, 가이드라인의 집합으로 팀이 일관된 제품을 효율적으로 만들 수 있게 하는 단일 소스(Single Source of Truth)다.

## 구성 요소

| 레이어 | 내용 | 예시 |
|---|---|---|
| **Foundations** | 기본 원소 | 색상, 타이포그래피, 간격, 아이콘 |
| **Components** | 재사용 UI 단위 | 버튼, 인풋, 카드, 모달 |
| **Patterns** | 컴포넌트 조합 규칙 | 폼 레이아웃, 네비게이션 패턴 |
| **Guidelines** | 사용 지침 | 언제 어떤 컴포넌트를 쓰는가 |
| **Documentation** | 개발자용 명세 | Storybook, Zeroheight |

## Atomic Design 방법론 (Brad Frost)
`
Atoms → Molecules → Organisms → Templates → Pages
`
- **Atoms**: 버튼·인풋·레이블 (더 이상 분해 불가한 기본 단위)
- **Molecules**: 검색 폼 = 인풋 + 버튼
- **Organisms**: 헤더 = 로고 + 네비게이션 + 검색 폼
- **Templates**: 페이지 레이아웃 (콘텐츠 없는 와이어프레임)
- **Pages**: 실제 콘텐츠가 들어간 최종 화면

## 주요 Design System 사례
- **Google Material Design** — 구글 생태계 전반
- **Apple Human Interface Guidelines** — iOS/macOS
- **Airbnb DLS** — Airbnb 제품군
- **Salesforce Lightning** — 엔터프라이즈 B2B

## Related Terms
- [[Component-Library]] — 디자인 시스템의 코드 구현체
- [[Design-Token]] — 색상·간격 값을 토큰으로 중앙 관리
- [[Storybook]] — 컴포넌트 문서화·테스트 도구

## References
- [Atomic Design — Brad Frost](https://atomicdesign.bradfrost.com/)
