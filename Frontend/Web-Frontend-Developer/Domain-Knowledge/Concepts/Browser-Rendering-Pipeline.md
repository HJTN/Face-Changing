# Browser Rendering Pipeline

## Overview
브라우저가 HTML/CSS/JS를 받아 화면에 픽셀을 그리는 과정이다. 이 과정을 이해하면 성능 병목을 정확히 진단하고 최적화할 수 있다.

## Critical Rendering Path

`
HTML → DOM
             → Render Tree → Layout → Paint → Composite
CSS  → CSSOM
`

1. **HTML 파싱 → DOM 생성** — HTML을 파싱해 DOM 트리 생성
2. **CSS 파싱 → CSSOM 생성** — CSS 규칙을 파싱해 CSSOM 트리 생성
3. **Render Tree 생성** — DOM + CSSOM 결합, 화면에 표시될 요소만 포함
4. **Layout (Reflow)** — 각 요소의 크기·위치 계산
5. **Paint (Repaint)** — 픽셀 그리기 (색상, 텍스트, 이미지)
6. **Composite** — 레이어를 합성해 최종 화면 출력

## 성능 최적화 관점

| 단계 | 병목 원인 | 해결책 |
|---|---|---|
| DOM 크기 | DOM 노드 수 과다 | 가상화(Virtual Scroll), 불필요 노드 제거 |
| CSS | 복잡한 셀렉터, 블로킹 CSS | Critical CSS 인라인, 미디어 쿼리 분리 |
| Reflow | 레이아웃 변경 빈번 | 	ransform 사용, 배치 DOM 업데이트 |
| Repaint | 잦은 색상·배경 변경 | will-change, GPU 레이어 활용 |

## 렌더링 방식
- **CSR (Client-Side Rendering)** — JS로 클라이언트에서 렌더링. 초기 로드 느림
- **SSR (Server-Side Rendering)** — 서버에서 HTML 완성 후 전송. 초기 로드 빠름
- **SSG (Static Site Generation)** — 빌드 타임에 HTML 생성. CDN 캐시 활용

## Related Terms
- [[Web-Vitals]] — 렌더링 성능의 사용자 중심 측정 지표
- [[Virtual-DOM]] — React가 Reflow를 최소화하는 방법

## References
- [Google Web Fundamentals — Critical Rendering Path](https://web.dev/critical-rendering-path/)
