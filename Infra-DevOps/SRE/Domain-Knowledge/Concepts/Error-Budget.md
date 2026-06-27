# Error Budget

## Overview
에러 버짓(Error Budget)은 SLO를 기반으로 허용 가능한 서비스 다운타임·오류의 총량이다. SRE의 핵심 개념으로, 신뢰성과 혁신 속도 사이의 균형을 데이터로 관리한다.

## Error Budget 계산

`
Error Budget = 1 - SLO

예: 가용성 SLO 99.9%이면
Error Budget = 0.1% = 월 43.8분
`

## Error Budget의 2가지 활용

### 1. 혁신 속도 조절자
- **에러 버짓이 충분** → 새 기능 배포, 실험 가능
- **에러 버짓 소진** → 배포 동결, 신뢰성 개선 집중

### 2. 개발·운영 간 협상 도구
- Dev: "빠른 배포를 원한다"
- SRE: "에러 버짓이 허용하는 만큼만 배포한다"
- 주관적 갈등 → 객관적 데이터 기반 협의

## Error Budget Policy 예시

| 에러 버짓 소진 | 대응 |
|---|---|
| 0–50% 소진 | 정상 개발 진행 |
| 50–75% 소진 | 경고, 신뢰성 작업 우선순위 상향 |
| 75–100% 소진 | 신기능 배포 중단, SRE와 공동 스프린트 |
| 100% 초과 | 모든 배포 동결, 포스트모템 필수 |

## Toil vs Engineering
- **Toil (토일)**: 수동적·반복적·자동화 가능한 운영 작업
- SRE 원칙: 토일 50% 이하 유지, 나머지는 엔지니어링 작업
- 토일을 자동화하면 에러 버짓을 더 효율적으로 보호

## Related Terms
- [[Service-Level-Management]] — Error Budget의 기반인 SLO 정의
- [[SRE-Principles]] — Error Budget이 녹아있는 SRE 철학

## References
- [Google SRE Book — Embracing Risk](https://sre.google/sre-book/embracing-risk/)
