# MCU Architecture (Microcontroller Unit)

## Overview
마이크로컨트롤러(MCU)는 CPU·메모리·주변장치(GPIO, UART, SPI, I2C)를 단일 칩에 통합한 소형 컴퓨터다. 임베디드 시스템 개발자는 MCU 아키텍처를 이해하고 하드웨어를 직접 제어하는 코드를 작성한다.

## MCU 주요 구성요소

| 구성요소 | 설명 |
|---|---|
| **CPU Core** | ARM Cortex-M (M0/M3/M4/M7/M33) — 가장 광범위 |
| **Flash Memory** | 프로그램 코드 저장 (비휘발성) |
| **SRAM** | 런타임 데이터, 스택, 힙 저장 (휘발성) |
| **GPIO** | 디지털 입출력 핀 (LED, 버튼) |
| **ADC/DAC** | 아날로그↔디지털 변환 (센서 읽기) |
| **타이머/PWM** | 정밀 시간 측정, 모터·LED 제어 |
| **통신 인터페이스** | UART, SPI, I2C, CAN, USB |

## 주요 MCU 플랫폼

| 플랫폼 | 코어 | 주요 사용처 |
|---|---|---|
| **STM32** (ST) | ARM Cortex-M | 산업용, 로봇공학 |
| **ESP32** (Espressif) | Xtensa LX6, RISC-V | IoT, Wi-Fi/BT 내장 |
| **nRF52840** (Nordic) | ARM Cortex-M4 | BLE 무선 통신 |
| **ATmega328P** (Microchip) | AVR 8-bit | Arduino, 교육용 |
| **RP2040** (Raspberry Pi) | ARM Cortex-M0+ | 취미, 교육 |

## 메모리 맵 (Memory Map)
`
0xFFFFFFFF ─ System/Peripheral Registers
             (GPIO, UART, SPI 레지스터 직접 접근)
0x20000000 ─ SRAM (스택, 힙, 전역변수)
0x08000000 ─ Flash (코드, 상수)
0x00000000 ─ Interrupt Vector Table
`

## Related Terms
- [[Real-Time-Systems]] — MCU 위에서 실행되는 RTOS
- [[HAL]] — 하드웨어 추상화 레이어

## References
- [ARM Cortex-M Datasheet](https://developer.arm.com/Processors/Cortex-M)
