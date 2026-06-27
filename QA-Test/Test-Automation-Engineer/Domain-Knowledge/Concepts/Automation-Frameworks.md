# Test Automation Frameworks

## Overview
테스트 자동화 프레임워크는 테스트 스크립트 작성·실행·보고를 위한 구조와 도구 집합이다. 올바른 프레임워크 선택이 자동화 효율성과 유지보수성을 결정한다.

## 테스트 자동화 계층별 프레임워크

### 단위 테스트
| 언어 | 프레임워크 |
|---|---|
| Java | JUnit 5, TestNG |
| Python | pytest, unittest |
| JavaScript | Jest, Mocha, Vitest |
| Go | testing (내장) |
| Kotlin | JUnit 5, Kotest |

### E2E / UI 테스트
| 도구 | 특징 |
|---|---|
| **Playwright** | 현대적, 멀티 브라우저, 빠름. 2024년 표준 |
| **Cypress** | 개발자 친화적, JavaScript, 단일 브라우저 |
| **Selenium** | 레거시 표준, 모든 브라우저, 느림 |
| **Appium** | 모바일 앱 자동화 (iOS + Android) |

### API 테스트
- **Postman / Newman** — GUI + CLI 자동화
- **REST Assured** — Java API 테스트
- **pytest + requests** — Python API 테스트

### 성능 테스트
- **k6** — JavaScript, 개발자 친화적, CI 통합 쉬움
- **JMeter** — GUI 기반, 오래된 표준
- **Gatling** — Scala, 고성능 시뮬레이션

## 프레임워크 설계 패턴

### Page Object Model (POM)
`python
# 나쁜 예: 테스트에 직접 셀렉터
def test_login():
    driver.find_element(By.ID, "username").send_keys("admin")

# 좋은 예: Page Object로 추상화
class LoginPage:
    def enter_username(self, username): ...
    def click_login(self): ...

def test_login():
    LoginPage().enter_username("admin").click_login()
`

## Related Terms
- [[Test-Architecture]] — 프레임워크를 조합한 전체 자동화 아키텍처
- [[Automation-Best-Practices]] — 프레임워크를 효과적으로 활용하는 원칙

## References
- [Playwright Documentation](https://playwright.dev/)
- [k6 Load Testing](https://k6.io/docs/)
