# Atomic Design Methodology

## Overview
Atomic Design은 Brad Frost가 2013년 제안한 디자인 시스템 구축 방법론이다. 자연계의 원소 개념을 차용해 UI를 계층적으로 분해하고 조합하는 원칙을 제시한다.

## 5단계 계층 구조

| 단계 | 화학 비유 | UI 예시 | 특징 |
|---|---|---|---|
| **Atoms** | 원자 | 버튼, 인풋, 레이블 | 더 작게 분해 불가 |
| **Molecules** | 분자 | 검색폼(인풋+버튼) | 원자 조합, 단일 기능 |
| **Organisms** | 유기체 | 헤더, 제품 카드 리스트 | 분자 조합, 독립 기능 |
| **Templates** | 레이아웃 | 블로그 포스트 템플릿 | 실제 데이터 없는 구조 |
| **Pages** | 실제 페이지 | 블로그 포스트 페이지 | 실제 데이터가 채워진 상태 |

## 핵심 원칙

1. **재사용성**: 한 번 정의한 컴포넌트를 전 제품에 재사용
2. **일관성**: 동일한 컴포넌트 = 동일한 경험
3. **유지보수성**: 한 곳 수정이 전 제품에 반영
4. **협업 효율**: 디자이너·개발자가 동일한 언어로 소통

## 도구 생태계
- **Figma Components** — 디자인 원자 정의
- **Storybook** — 개발 컴포넌트 문서화
- **Design Tokens** — 원자 레벨 값(색상·크기) 중앙 관리

## Related Terms
- [[Design-Systems]] — Atomic Design의 구현 결과물
- [[Component-Library]] — Organisms/Molecules의 코드 구현체

## References
- [Atomic Design Book — Brad Frost](https://atomicdesign.bradfrost.com/table-of-contents/)
