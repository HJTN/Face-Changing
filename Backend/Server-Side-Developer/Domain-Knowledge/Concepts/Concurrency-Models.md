# Concurrency Models

## Overview
서버는 동시에 수천~수백만 요청을 처리해야 한다. 동시성 모델은 이 병렬 처리를 어떻게 구현할지 결정하며, 선택에 따라 성능·복잡도·리소스 사용량이 크게 달라진다.

## 주요 동시성 모델

### 1. Thread-per-Request (전통적 모델)
- 요청마다 OS 스레드 할당
- 장점: 단순, 블로킹 코드 그대로 사용 가능
- 단점: 스레드 스위칭 비용, 메모리 사용량 큼 (스레드당 1MB+)
- 사례: 전통적 Spring MVC, Apache

### 2. Event Loop (비동기 모델)
- 단일 스레드 이벤트 루프 + 논블로킹 I/O
- 장점: 높은 동시성, 낮은 메모리 사용
- 단점: CPU 집약적 작업에 부적합, 콜백 지옥
- 사례: Node.js, Nginx

### 3. Reactive / Async (비동기 프레임워크)
- 비동기 논블로킹 + 함수형 파이프라인
- 장점: 높은 처리량, 배압(Backpressure) 지원
- 단점: 디버깅 어려움, 학습 곡선
- 사례: Spring WebFlux (Project Reactor), RxJava

### 4. Actor Model
- 독립 Actor가 메시지로만 통신 → 공유 상태 없음
- 사례: Akka (Scala/Java), Erlang

## Java 21의 Virtual Thread (Project Loom)
`java
// 기존: OS Thread (무거움)
var thread = new Thread(task);

// Virtual Thread (경량, 수백만 개 생성 가능)
var vThread = Thread.ofVirtual().start(task);
`
- OS 스레드 위에 JVM이 가상 스레드를 스케줄링
- Thread-per-Request 모델의 편의성 + Event Loop의 확장성

## Related Terms
- [[Caching-Strategies]] — 동시 요청에서 DB 부하를 줄이는 방법
- [[Message-Queue]] — 비동기 처리로 동시성 문제를 완화

## References
- [Project Loom — Virtual Threads](https://openjdk.org/projects/loom/)
- [The C10K Problem](http://www.kegel.com/c10k.html)
