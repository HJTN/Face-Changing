# Real-Time Systems (RTOS)

## Overview
실시간 시스템(Real-Time System)은 특정 시간 제약(Deadline) 내에 반드시 응답해야 하는 시스템이다. 단순히 '빠른' 것이 아니라 '예측 가능하고 결정론적'인 것이 핵심이다.

## 실시간 시스템 분류

| 유형 | 데드라인 초과 결과 | 예시 |
|---|---|---|
| **Hard Real-Time** | 시스템 실패 (생명 위험) | 에어백, 항공 제어 |
| **Firm Real-Time** | 데이터 쓸모없음 | 금융 거래, 비디오 코덱 |
| **Soft Real-Time** | 성능 저하만 발생 | 스트리밍, 게임 |

## RTOS 핵심 개념

### 태스크 스케줄링
- **Priority-based Preemptive** — 높은 우선순위 태스크가 낮은 우선순위 선점
- **Round-Robin** — 동일 우선순위 태스크를 시간 분할
- **Rate Monotonic** — 주기 짧을수록 우선순위 높음 (이론적 최적)

### 주요 RTOS 개념
- **Task/Thread** — 독립적으로 스케줄링되는 실행 단위
- **Semaphore** — 자원 접근 동기화
- **Mutex** — 상호 배제 (Priority Inheritance로 Priority Inversion 해결)
- **Message Queue** — 태스크 간 통신

## 주요 RTOS

| RTOS | 특징 | 주요 사용처 |
|---|---|---|
| **FreeRTOS** | 오픈소스, 가장 대중적 | IoT, 소비자 기기 |
| **Zephyr** | Linux Foundation, 모듈식 | Nordic, STM32 |
| **AUTOSAR** | 자동차 산업 표준 | 차량 ECU |
| **VxWorks** | 고신뢰성 상용 RTOS | 항공우주, 국방 |

## Related Terms
- [[MCU-Architecture]] — RTOS가 실행되는 하드웨어
- [[Embedded-Design-Principles]] — 임베디드 시스템 설계 원칙

## References
- [FreeRTOS Documentation](https://www.freertos.org/Documentation/RTOS_book.html)
