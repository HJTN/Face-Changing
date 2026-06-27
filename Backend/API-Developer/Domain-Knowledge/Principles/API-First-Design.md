# API-First Design

## Overview
API First는 제품 개발 시 UI나 백엔드 구현보다 API 설계를 먼저 하는 접근 방식이다. API가 제품의 핵심 인터페이스가 되는 현대 MSA·모바일 환경에서 더욱 중요해졌다.

## API First vs Code First

| 접근 | 순서 | 장점 | 단점 |
|---|---|---|---|
| **API First** | 명세 설계 → 구현 | 팀 간 병렬 개발 가능, 계약 명확 | 초기 설계 시간 필요 |
| **Code First** | 구현 → 명세 생성 | 빠른 시작 | 명세가 구현에 종속됨 |

## API First 프로세스

1. **API 계약 설계** — OpenAPI 3.0 (YAML/JSON) 명세 작성
2. **Mock 서버 생성** — Prism, Stoplight으로 명세에서 Mock 자동 생성
3. **병렬 개발** — 프론트엔드는 Mock 서버로, 백엔드는 구현 시작
4. **계약 테스트** — Dredd, Pact로 명세 vs 구현 일치 검증
5. **문서 자동화** — Swagger UI, Redoc으로 명세에서 문서 생성

## DX (Developer Experience) 원칙
- **일관성**: 모든 엔드포인트가 같은 패턴 (에러 형식, 페이지네이션)
- **예측 가능성**: 이름만 보고 동작을 예상 가능
- **명확한 에러**: 에러 메시지가 문제 해결에 도움이 되어야 함

`json
// 나쁜 에러
{ "error": "400" }

// 좋은 에러
{
  "error": {
    "code": "INVALID_EMAIL",
    "message": "이메일 형식이 올바르지 않습니다.",
    "field": "email"
  }
}
`

## Related Terms
- [[RESTful-Design]] — API First로 설계되는 가장 일반적인 API 스타일
- [[OpenAPI-Swagger]] — API First 명세의 표준 도구

## References
- [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [API Design Guide — Google](https://cloud.google.com/apis/design)
