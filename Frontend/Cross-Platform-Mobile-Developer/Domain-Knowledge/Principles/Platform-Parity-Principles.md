# Platform Parity Principles

## Overview
플랫폼 패리티(Platform Parity)는 크로스플랫폼 앱에서 iOS와 Android 사용자 모두에게 동등한 기능·품질의 경험을 제공하는 원칙이다.

## 핵심 원칙

### 1. Functional Parity (기능 동등성)
- iOS 출시 후 Android는 2개월 뒤 출시하는 방식은 사용자 불평등을 만든다
- 크로스플랫폼 프레임워크의 핵심 가치: 동시 출시(Simultaneous Launch)

### 2. Platform-Idiomatic UI (플랫폼 관용 UI)
- iOS: Cupertino 스타일 (Sheet, NavigationBar 위치)
- Android: Material Design (Bottom Navigation, FAB)
- 공유된 비즈니스 로직, 플랫폼별 UI 패턴 존중

### 3. Performance Parity (성능 동등성)
- 구형 Android 기기에서도 60fps 유지
- iOS 최신 기기에서만 최적화된 앱은 안드로이드 사용자 이탈 유발

### 4. Accessibility Parity
- 두 플랫폼 모두 스크린리더(VoiceOver/TalkBack) 지원
- 폰트 크기 설정 연동

## 공유 전략 (KMM 방식)

`
┌─────────────────────┐
│  iOS UI (SwiftUI)   │
└─────────┬───────────┘
          │ (공유 로직)
┌─────────▼───────────┐
│  Kotlin Multiplatform│
│  - Domain Logic      │
│  - Repository        │
│  - Network           │
└─────────┬───────────┘
          │ (공유 로직)
┌─────────▼───────────┐
│  Android UI (Compose)│
└─────────────────────┘
`

## Related Terms
- [[Cross-Platform-Approaches]] — 플랫폼 패리티를 달성하는 도구들
- [[Native-vs-Hybrid]] — 패리티와 성능 간의 트레이드오프

## References
- [Kotlin Multiplatform Mobile](https://kotlinlang.org/docs/multiplatform-mobile-getting-started.html)
