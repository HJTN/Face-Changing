# API Security

## Overview
API 보안은 인증(Authentication)·인가(Authorization)·데이터 보호를 통해 API 엔드포인트를 무단 접근·악용으로부터 보호하는 방법론이다.

## 인증 방법 비교

| 방법 | 원리 | 장점 | 단점 |
|---|---|---|---|
| **API Key** | 발급된 키를 헤더에 전달 | 단순 | 키 노출 위험 |
| **Basic Auth** | Base64(user:pass) | 단순 | HTTPS 필수, Stateful |
| **JWT (Bearer Token)** | 서명된 토큰, 자기 검증 | Stateless, 표준화 | 토큰 탈취 시 무효화 어려움 |
| **OAuth 2.0** | 위임 인증 프레임워크 | 제3자 인증, 세분화된 권한 | 복잡도 높음 |

## JWT 구조
`
Header.Payload.Signature
eyJhbGciOiJIUzI1NiJ9.eyJ1c2VySWQiOiIxMjMifQ.SflKxwRJSMeKKF...
`
- **Header**: 알고리즘 (HS256, RS256)
- **Payload**: Claims (userId, exp, iss) — 민감 정보 절대 금지
- **Signature**: 비밀키로 서명 — 위변조 방지

## OAuth 2.0 플로우

`
사용자 → 클라이언트 앱 → Authorization Server
                      ← Authorization Code
클라이언트 → Auth Server (code + client_secret)
           ← Access Token + Refresh Token
클라이언트 → Resource Server (Access Token)
           ← Protected Resource
`

## API 보안 체크리스트
- [ ] HTTPS 강제 (HTTP 차단)
- [ ] Rate Limiting (429 Too Many Requests)
- [ ] Input Validation & Sanitization
- [ ] CORS 정책 설정
- [ ] 토큰 만료 시간 설정 (Access: 15분, Refresh: 7일)
- [ ] 민감 정보 응답에서 제외 (password, SSN)

## Related Terms
- [[RESTful-Design]] — REST API에 보안 적용
- [[OAuth2]] — 가장 널리 사용되는 API 인가 프레임워크

## References
- [OWASP API Security Top 10](https://owasp.org/www-project-api-security/)
