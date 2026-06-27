# Apple Human Interface Guidelines (HIG)

## Overview
Apple HIG는 iOS·macOS·watchOS·tvOS 플랫폼에서 사용자에게 일관되고 직관적인 경험을 제공하기 위한 설계 지침이다. Apple이 앱 심사 시 참고하며, 이를 준수하는 앱이 앱 스토어에서 유리하다.

## 핵심 4대 원칙

### 1. Clarity (명확성)
- 텍스트는 모든 크기에서 읽기 쉬워야 함
- 아이콘은 정밀하고 의미가 명확해야 함
- 장식보다 기능이 앞서야 함

### 2. Deference (존중)
- UI가 콘텐츠를 돋보이게 해야지, UI 자체가 주인공이 되어선 안 됨
- 투명도·흐림 효과로 콘텐츠 맥락 유지

### 3. Depth (깊이)
- 레이어와 움직임으로 계층 구조와 공간감 전달
- 터치 제스처로 콘텐츠 탐색의 즐거움 제공

### 4. Accessibility (접근성)
- Dynamic Type — 사용자 지정 폰트 크기 지원
- VoiceOver — 시각 장애인을 위한 스크린리더 지원
- Reduce Motion — 전정기관 장애 사용자를 위한 모션 감소

## iOS 주요 UI 패턴
- **Navigation Controller** — 계층적 콘텐츠 탐색
- **Tab Bar** — 앱의 주요 섹션 전환 (5개 이하 권장)
- **Action Sheet vs Alert** — 파괴적 행동은 Action Sheet, 즉각 주의 필요시 Alert

## Related Terms
- [[SwiftUI]] — HIG를 코드로 구현하는 Apple 프레임워크
- [[Accessibility]] — HIG의 핵심 접근성 요구사항

## References
- [Apple Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/)
