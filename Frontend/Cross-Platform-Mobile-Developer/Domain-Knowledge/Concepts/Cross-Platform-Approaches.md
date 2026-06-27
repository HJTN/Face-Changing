# Cross-Platform Mobile Development Approaches

## Overview
크로스 플랫폼 모바일 개발은 하나의 코드베이스로 iOS·Android 두 플랫폼에서 동작하는 앱을 만드는 접근 방식이다. 개발 생산성은 높아지지만 플랫폼 고유 기능 접근이나 성능에서 제약이 있을 수 있다.

## 주요 프레임워크 비교

| 프레임워크 | 언어 | 렌더링 방식 | 특징 |
|---|---|---|---|
| **React Native** | JavaScript/TypeScript | 네이티브 컴포넌트 브리지 | 가장 큰 커뮤니티, Meta 지원 |
| **Flutter** | Dart | 자체 렌더링 엔진(Skia/Impeller) | 일관된 UI, Google 지원 |
| **Ionic** | HTML/CSS/JS | WebView | 웹 기술 그대로 사용 |
| **Xamarin/.NET MAUI** | C# | 네이티브 컴포넌트 | Microsoft 생태계 |
| **KMM (Kotlin Multiplatform)** | Kotlin | 네이티브 | 로직 공유, UI는 네이티브 |

## 아키텍처 스펙트럼

`
네이티브 앱 ←────────────────────────────────────→ 웹앱
(Swift/Kotlin)  KMM   React Native  Flutter  Ionic  PWA
               [공유 로직]  [공유 UI]  [자체 렌더]  [WebView]
`

## React Native 아키텍처 (New Architecture, 2022)

### Old Architecture
- JavaScript ↔ Native 통신: 비동기 JSON 직렬화 (Bridge)
- 성능 병목: 대용량 데이터 통신 시 느림

### New Architecture (JSI)
- JavaScript Interface (JSI) — 동기 직접 호출, 브리지 제거
- Fabric Renderer — UI 렌더링 개선
- TurboModules — 네이티브 모듈 지연 로딩

## Related Terms
- [[Native-vs-Hybrid]] — 성능·비용 트레이드오프 결정 기준
- [[Flutter]] — 자체 렌더링 엔진을 사용하는 크로스플랫폼 프레임워크

## References
- [React Native New Architecture](https://reactnative.dev/docs/the-new-architecture/landing-page)
- [Flutter vs React Native 2024 Comparison](https://flutter.dev/docs/resources/faq)
