# Progressive Enhancement

## Overview
점진적 향상(Progressive Enhancement)은 기본 기능을 모든 브라우저·환경에서 보장하고, 고급 기능을 지원하는 환경에서 점차 향상된 경험을 추가하는 개발 철학이다.

## 3개 레이어

`
[Layer 3] JavaScript — 동적 인터랙션, 고급 기능
[Layer 2] CSS        — 시각적 표현, 레이아웃
[Layer 1] HTML       — 콘텐츠, 구조 (항상 작동해야 함)
`

## Graceful Degradation vs Progressive Enhancement

| 접근 | 방향 | 특징 |
|---|---|---|
| **Graceful Degradation** | 위 → 아래 | 최신 기능부터 개발 후 구형 환경 대응 |
| **Progressive Enhancement** | 아래 → 위 | 기본부터 구축 후 고급 기능 추가 |

Progressive Enhancement가 더 견고하고 접근성 친화적이다.

## 실제 적용 예시

`html
<!-- HTML 레이어: 기본 폼 (JS 없어도 작동) -->
<form action="/search" method="GET">
  <input name="q" type="search">
  <button type="submit">검색</button>
</form>

<!-- CSS 레이어: 스타일 추가 -->
<!-- JS 레이어: 자동완성, 실시간 검색 추가 -->
`

## 왜 중요한가
- 접근성(Accessibility) 보장 — 스크린리더·구형 브라우저 사용자도 기본 기능 이용 가능
- SEO 향상 — 크롤러가 HTML 콘텐츠를 읽을 수 있음
- 네트워크 불안정 환경 대응 — JS 로드 실패해도 기본 기능 유지

## Related Terms
- [[Performance-First-Development]] — 성능 최적화와 결합되는 원칙
- [[Accessibility]] — PE의 핵심 수혜자

## References
- [MDN — Progressive Enhancement](https://developer.mozilla.org/en-US/docs/Glossary/Progressive_Enhancement)
