# iOS App Architecture Patterns

## Overview
iOS 앱 아키텍처 패턴은 코드를 역할별로 분리해 유지보수성·테스트 가능성을 높이는 설계 방식이다. 선택은 앱 규모·팀 경험·테스트 전략에 따라 달라진다.

## 주요 패턴 비교

### MVC (Model-View-Controller)
- Apple 공식 권장 패턴 (UIKit 기반)
- **Model** — 데이터·비즈니스 로직
- **View** — UI 표시
- **Controller** — Model·View 중재자
- 문제점: Massive View Controller (ViewController가 비대해짐)

### MVVM (Model-View-ViewModel)
- SwiftUI와 잘 어울림
- **ViewModel** — View의 상태를 관리, 비즈니스 로직 포함
- **Binding** — ViewModel 변경이 View에 자동 반영 (Combine, @Published)
- 테스트: ViewModel은 UIKit 의존성 없이 단위 테스트 가능

### Clean Architecture
- Uncle Bob의 아키텍처를 iOS에 적용
- 레이어: Presentation → Domain (UseCase) → Data
- 의존성은 항상 안쪽(Domain)을 향함

## SwiftUI vs UIKit
| 항목 | SwiftUI | UIKit |
|---|---|---|
| 선언 방식 | 선언형 | 명령형 |
| 상태 관리 | @State, @ObservedObject | 수동 업데이트 |
| iOS 지원 | iOS 13+ | iOS 2+ |
| 성숙도 | 빠르게 발전 중 | 매우 성숙 |

## Related Terms
- [[Swift-Memory-Management]] — ARC는 아키텍처와 무관하게 모든 패턴에 적용
- [[Combine]] — MVVM의 바인딩을 구현하는 Apple 리액티브 프레임워크

## References
- [The iOS App Architecture Patterns](https://medium.com/ios-os-x-development/ios-architecture-patterns-ecba4c38de52)
