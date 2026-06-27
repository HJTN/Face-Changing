# Golden Path Principle

## Overview
골든 패스(Golden Path)는 Spotify가 처음 도입한 개념으로, 플랫폼 팀이 개발자에게 제공하는 '표준화된 권장 경로'다. 빠르고 안전하게 아이디어를 프로덕션으로 가져가는 검증된 방법이다.

## 핵심 개념

### What is Golden Path?
- 개발자가 새 서비스를 만들 때 따를 수 있는 미리 정의된 경로
- 기술 선택, 파이프라인 설정, 모니터링 연결까지 모두 포함
- "당신이 고민해야 할 것들을 우리가 미리 결정했습니다"

### Golden Path vs Paved Road
- **Paved Road**: 추천 경로를 제공하되 이탈도 허용
- **Golden Path**: 더 강하게 표준화, 이탈 시 팀의 지원 감소

## Golden Path 구성요소

`
[Golden Path 예시: 새 마이크로서비스 시작]
1. GitHub에서 서비스 템플릿 선택 (Backstage)
   → Spring Boot / FastAPI / Node.js 중 선택
2. 자동으로 생성되는 것들:
   - Git 저장소
   - CI/CD 파이프라인 (GitHub Actions)
   - Kubernetes Namespace + RBAC
   - 모니터링 대시보드 (Grafana)
   - 문서 페이지 (Backstage)
   - Vault 비밀 경로
3. 개발자는 비즈니스 로직 코드만 작성
`

## 왜 Golden Path인가
- 빈 들판(Blank Slate): 완전한 자유 → 모든 팀이 다른 방식 → 혼돈
- 고속도로(Highway): 강제된 표준 → 유연성 없음 → 개발자 불만
- 골든 패스: 검증된 경로 + 이탈 자유 → 빠름 + 유연성

## Related Terms
- [[Internal-Developer-Platform]] — Golden Path를 실현하는 인프라
- [[Platform-Engineering]] — Golden Path를 설계·제공하는 팀

## References
- [Spotify Engineering — Golden Path](https://engineering.atspotify.com/2020/08/how-we-use-golden-paths-to-solve-fragmentation-in-our-software-ecosystem/)
