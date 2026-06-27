# Embedded Systems Design Principles

## Overview
임베디드 시스템은 제한된 자원(메모리·CPU·전력)에서 신뢰성 있게 동작해야 한다. 일반 소프트웨어와 다른 설계 원칙이 적용된다.

## 핵심 원칙

### 1. Resource Constraint First (자원 제약 우선)
- Flash: 수십 KB ~ 수 MB. 코드 크기 최적화 필수
- RAM: 수 KB ~ 수백 KB. 동적 할당(malloc) 최소화
- static, 스택 사이의 트레이드오프 항상 고려

### 2. Determinism (결정론적 동작)
- 동일 입력 → 항상 동일 출력, 동일 타이밍
- 가비지 컬렉터·런타임 예외 지양 (C/C++ 선호)
- WCET(Worst-Case Execution Time) 분석 필수

### 3. Defensive Programming (방어적 프로그래밍)
- Watchdog Timer — 프로그램이 멈추면 자동 재시작
- Null 체크, 경계값 검사 철저히
- Fail-Safe Default — 오류 시 안전한 기본 상태로

### 4. Hardware Abstraction (하드웨어 추상화)
- HAL(Hardware Abstraction Layer)로 하드웨어 의존 코드 분리
- MCU 교체 시 HAL만 수정, 비즈니스 로직 재사용

### 5. Low Power Design (저전력 설계)
- Sleep Mode 활용 (유휴 시 CPU 클럭 감소)
- 필요할 때만 주변장치 활성화
- DMA(Direct Memory Access)로 CPU 개입 없는 데이터 전송

## Safety-Critical 기준
- **IEC 61508** — 기능 안전 국제 표준
- **MISRA C** — 자동차 임베디드 C 코딩 규칙 (동적 할당 금지 등)
- **DO-178C** — 항공 소프트웨어 인증 기준

## Related Terms
- [[Real-Time-Systems]] — 결정론적 동작을 RTOS로 구현
- [[MCU-Architecture]] — 자원 제약의 실제 하드웨어 기반

## References
- [MISRA C Guidelines](https://www.misra.org.uk/)
