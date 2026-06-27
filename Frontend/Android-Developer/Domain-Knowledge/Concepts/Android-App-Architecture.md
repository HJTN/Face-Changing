# Android App Architecture

## Overview
Google이 권장하는 안드로이드 앱 아키텍처는 관심사 분리(Separation of Concerns)와 단방향 데이터 흐름(Unidirectional Data Flow, UDF)을 핵심 원칙으로 한다.

## Android Architecture Components (AAC)

`
┌─────────────────────────────────────────┐
│  UI Layer  (Activity / Fragment / Composable)  │
│       ↓ observes                               │
│  ViewModel (상태 보유, 비즈니스 로직 중재)      │
│       ↓ 요청 / ↑ 데이터                        │
│  Domain Layer (UseCase) — 선택사항             │
│       ↓ 요청 / ↑ 데이터                        │
│  Data Layer (Repository → DataSource)          │
└─────────────────────────────────────────┘
`

### ViewModel
- UI 회전·재생성 시 데이터 유지 (Configuration Change 대응)
- StateFlow / LiveData로 UI에 상태 발행
- Repository에 요청 위임

### Repository
- 단일 데이터 소스 역할 (Network vs Cache 선택)
- ViewModel이 데이터 출처를 알 필요 없게 추상화

## Jetpack Compose vs XML View

| 항목 | Jetpack Compose | XML View |
|---|---|---|
| 선언 방식 | Kotlin 코드로 선언형 | XML 레이아웃 |
| 상태 관리 | emember, State | 수동 View 업데이트 |
| 재사용 | Composable 함수 | Custom View |
| 성능 | 스마트 리컴포지션 | View hierarchy |
| 트렌드 | Google 공식 권장 (2021+) | 기존 코드베이스 |

## Related Terms
- [[Kotlin-Coroutines]] — 비동기 데이터 패칭을 ViewModel에서 처리
- [[Hilt]] — 의존성 주입으로 Repository·UseCase 연결

## References
- [Android Architecture Guide](https://developer.android.com/topic/architecture)
