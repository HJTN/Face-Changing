# Docs as Code

## Overview
Docs as Code는 소프트웨어 코드를 다루듯이 문서를 작성·버전 관리·검토·배포하는 방법론이다. 코드와 문서를 같은 워크플로우로 관리함으로써 문서가 코드와 항상 동기화되게 한다.

## 핵심 원칙

### 1. 버전 관리 (Version Control)
- 문서를 Git으로 관리 (코드와 같은 저장소 또는 별도)
- 변경 이력 추적, 이전 버전 복원 가능

### 2. Plain Text 형식
- Markdown, reStructuredText, AsciiDoc
- WYSIWYG 도구가 아닌 텍스트 에디터로 작성
- 코드 리뷰 도구(GitHub PR)로 문서 리뷰 가능

### 3. CI/CD 파이프라인
`
문서 Markdown → 빌드 (MkDocs, Sphinx, Docusaurus) → 정적 사이트 → 자동 배포
`
- 문서 PR 병합 시 자동 빌드·배포
- 링크 유효성·철자 오류 자동 검사

### 4. 이슈 트래킹
- 문서 오류·개선 요청을 GitHub Issues로 관리
- 독자가 직접 PR 기여 가능 ("Edit this page" 버튼)

## 주요 문서 빌드 도구

| 도구 | 언어 | 특징 |
|---|---|---|
| **Docusaurus** | React/MDX | Meta 오픈소스, 버전 관리 기능 |
| **MkDocs Material** | Python/Markdown | 깔끔한 디자인, 간단한 설정 |
| **Sphinx** | Python/RST | 파이썬 생태계 표준 |
| **Gitbook** | SaaS | 협업·편집 UX 우수 |

## API 문서 자동화
- **OpenAPI → Swagger UI / Redoc**: 코드 주석에서 API 문서 자동 생성
- **Javadoc / JSDoc**: 코드 주석에서 라이브러리 문서 생성

## Related Terms
- [[Documentation-Types]] — Docs as Code로 관리되는 문서 유형들
- [[Information-Architecture]] — 문서 저장소의 폴더 구조

## References
- [Docs as Code — Anne Gentle](https://www.docslikecode.com/)
- [Docusaurus](https://docusaurus.io/)
