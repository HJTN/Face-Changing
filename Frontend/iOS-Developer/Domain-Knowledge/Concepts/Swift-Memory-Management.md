# Swift Memory Management

## Overview
Swift는 ARC(Automatic Reference Counting)를 사용해 메모리를 자동 관리한다. GC(Garbage Collector)와 달리 런타임 부하 없이 컴파일 타임에 메모리 해제 시점을 결정한다.

## ARC 동작 원리

`swift
class Person {
    let name: String
    init(name: String) { self.name = name }
    deinit { print("(name) 해제됨") }
}

var p1: Person? = Person(name: "Alice")  // RC: 1
var p2 = p1                              // RC: 2
p1 = nil                                 // RC: 1
p2 = nil                                 // RC: 0 → 메모리 해제
`

## 강한 참조 순환 (Retain Cycle)

`swift
class A { var b: B? }    // A → B 강한 참조
class B { var a: A? }    // B → A 강한 참조 → Retain Cycle!
`

- 두 객체의 RC가 서로를 유지해 0이 되지 않음 → 메모리 누수

### 해결책
| 참조 유형 | 키워드 | 사용 시점 |
|---|---|---|
| **Strong** | (기본값) | 소유권 필요할 때 |
| **Weak** | weak | 옵션 참조, 대등한 관계 |
| **Unowned** | unowned | 비옵션 참조, 피참조 객체가 더 오래 삶 |

## Value vs Reference Types
- **Value Types** (struct, enum, String, Array): 복사본 사용, 스택 할당, ARC 불필요
- **Reference Types** (class): 참조 공유, 힙 할당, ARC 관리 대상

## Related Terms
- [[Swift]] — ARC를 구현하는 언어
- [[Instruments]] — Allocations·Leaks 도구로 메모리 누수 탐지

## References
- [Swift Documentation — ARC](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/automaticreferencecounting/)
