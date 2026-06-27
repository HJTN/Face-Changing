# Performance-First Development

## Overview
성능 우선 개발은 사용자 경험에 직결되는 로딩 속도·반응성을 개발 초기부터 고려하는 원칙이다. 구글 연구에 따르면 로딩 시간이 1초 늘어날 때마다 전환율이 최대 20% 감소한다.

## Core Web Vitals (Google 기준)

| 지표 | 측정 항목 | Good 기준 |
|---|---|---|
| **LCP** (Largest Contentful Paint) | 가장 큰 콘텐츠 로드 시간 | 2.5초 이하 |
| **FID** (First Input Delay) | 첫 입력 응답 지연 | 100ms 이하 |
| **CLS** (Cumulative Layout Shift) | 레이아웃 누적 이동 | 0.1 이하 |
| **INP** (Interaction to Next Paint) | FID 대체, 모든 인터랙션 응답 | 200ms 이하 |

## 주요 최적화 기법

### JavaScript 최적화
- **Code Splitting** — 라우트별 JS 청크 분리 (React.lazy)
- **Tree Shaking** — 사용하지 않는 코드 제거 (Webpack, Rollup)
- **Bundle 분석** — webpack-bundle-analyzer로 크기 시각화

### 이미지 최적화
- WebP/AVIF 형식 사용 (JPEG 대비 30% 작음)
- loading="lazy" 지연 로딩
- srcset으로 반응형 이미지

### 캐싱 전략
- CDN 배포로 지리적 거리 최소화
- Service Worker로 오프라인 캐싱

## Related Terms
- [[Browser-Rendering-Pipeline]] — 성능의 기술적 기반
- [[Web-Vitals]] — 성능 측정 표준 지표

## References
- [web.dev — Core Web Vitals](https://web.dev/vitals/)
