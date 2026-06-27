# Native vs Hybrid Development

## Overview
모바일 앱 개발 방식을 선택할 때 네이티브(Native)와 크로스플랫폼(Hybrid/Cross-Platform) 사이의 트레이드오프를 이해해야 한다.

## 비교 분석

| 기준 | Native | Cross-Platform | Web App (PWA) |
|---|---|---|---|
| **성능** | 최고 | 매우 좋음 | 보통 |
| **개발 비용** | 2배 (iOS+Android) | 1배 | 0.8배 |
| **플랫폼 기능 접근** | 100% | 90%+ | 제한적 |
| **UI 일관성** | 플랫폼별 최적화 | 통일 or 플랫폼별 | 브라우저 의존 |
| **출시 속도** | 느림 | 빠름 | 빠름 |
| **유지보수** | 2개 코드베이스 | 1개 코드베이스 | 1개 코드베이스 |

## 언제 네이티브를 선택하는가
- 최고 수준의 성능이 필요한 앱 (게임, 카메라, AR)
- 플랫폼 최신 API를 즉시 활용해야 할 때
- 플랫폼별 UX 정체성이 중요할 때
- 큰 개발팀과 충분한 예산이 있을 때

## 언제 크로스플랫폼을 선택하는가
- 스타트업·MVP 단계 — 빠른 출시 우선
- 비즈니스 앱·내부 도구 — 화려한 애니메이션 불필요
- 작은 팀 — 한 팀이 두 플랫폼 모두 담당
- 코드 공유가 비용 절감에 직결될 때

## Related Terms
- [[Cross-Platform-Approaches]] — 크로스플랫폼 방식의 세부 프레임워크
- [[React-Native]] — 가장 많이 쓰이는 크로스플랫폼 솔루션

## References
- [State of React Native 2024](https://reactnative.dev/blog)
