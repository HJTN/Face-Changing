# Responsive Design Principles

## Overview
반응형 디자인(Responsive Design)은 하나의 HTML/CSS 코드베이스로 다양한 화면 크기(모바일·태블릿·데스크탑)에서 최적의 경험을 제공하는 웹 설계 방식이다.

## 3대 핵심 원칙 (Ethan Marcotte, 2010)

1. **Fluid Grids** — 고정 픽셀 대신 % 단위 유연한 그리드
2. **Flexible Images** — 컨테이너에 맞게 이미지 크기 조절 (max-width: 100%)
3. **Media Queries** — CSS에서 뷰포트 크기에 따라 스타일 분기

## Breakpoint 기준 (일반적)
`css
/* Mobile first approach */
/* default  : 0–767px   (모바일) */
@media (min-width: 768px)  { /* 태블릿 */ }
@media (min-width: 1024px) { /* 데스크탑 */ }
@media (min-width: 1440px) { /* 와이드 데스크탑 */ }
`

## Mobile First 원칙
- 가장 작은 화면부터 설계 시작
- 이유: 모바일 트래픽이 전 세계 60%+ 차지
- 콘텐츠 우선순위 강제: 작은 화면에 뭘 보여줄지 먼저 결정

## 반응형 레이아웃 패턴
- **Mostly Fluid** — 열이 줄어들다가 모바일에서 단일 열
- **Column Drop** — 순차적으로 열이 아래로 쌓임
- **Layout Shifter** — 레이아웃 구조가 완전히 바뀜

## Related Terms
- [[Visual-Hierarchy]] — 화면 크기별로 시각 위계 재조정
- [[Color-and-Typography]] — 모바일에서 폰트 크기 최소 16px 유지

## References
- [MDN — Responsive Design](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design)
