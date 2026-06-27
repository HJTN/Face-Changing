# Testing Types

## Overview
소프트웨어 테스팅 유형은 무엇을, 어느 시점에, 어떤 방식으로 테스트하는지에 따라 분류된다. 각 유형은 서로 다른 결함을 발견하며 조합이 중요하다.

## 테스트 피라미드 (Test Pyramid)

`
        /\
       /  \
      / E2E\        ← UI/통합 테스트 (느림, 비용 큼, 적게)
     /──────\
    / API   /\     ← API/통합 테스트 (중간)
   /──────────\
  / Unit Tests \   ← 단위 테스트 (빠름, 비용 낮음, 많이)
 /──────────────\
`

## 주요 테스트 유형

| 유형 | 범위 | 목적 |
|---|---|---|
| **Unit Test** | 함수·클래스 단위 | 로직 검증, 빠른 피드백 |
| **Integration Test** | 모듈 간 연동 | 인터페이스·계약 검증 |
| **API Test** | HTTP 엔드포인트 | 계약·데이터 형식 검증 |
| **E2E Test** | 사용자 시나리오 전체 | 비즈니스 흐름 검증 |
| **Performance Test** | 부하·응답시간 | 성능 병목 발견 |
| **Security Test** | 취약점 | OWASP Top 10 검증 |
| **Usability Test** | 사용자 경험 | UX 문제 발견 |
| **Regression Test** | 기존 기능 | 변경 후 기존 기능 유지 확인 |
| **Smoke Test** | 핵심 기능 | 배포 후 기본 동작 확인 |
| **Exploratory Test** | 자유 탐색 | 스크립트 없는 창의적 결함 발견 |

## V-Model (전통적 테스트 모델)

`
요구사항 분석 ──────────────── 인수 테스트
시스템 설계 ──────────────── 시스템 테스트
아키텍처 설계 ────────────── 통합 테스트
모듈 설계 ──────────────── 단위 테스트
            개발
`

## Related Terms
- [[Test-Design-Techniques]] — 각 테스트 유형에서 테스트 케이스를 설계하는 기법
- [[Shift-Left-Testing]] — 테스트를 개발 초기로 이동하는 원칙

## References
- [ISTQB Foundation Level Syllabus](https://www.istqb.org/certifications/certified-tester-foundation-level)
