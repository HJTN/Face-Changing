# Android Lifecycle

## Overview
안드로이드 액티비티·프래그먼트의 생명주기는 시스템이 앱 구성요소를 생성·중지·소멸시키는 과정이다. 생명주기를 잘못 다루면 메모리 누수·데이터 손실·크래시가 발생한다.

## Activity 생명주기

`
onCreate() → onStart() → onResume()
                              ↓ (앱 동작 중)
              onPause() ← onResume()
                ↓
             onStop()
                ↓
            onDestroy()
`

| 콜백 | 트리거 | 할 일 |
|---|---|---|
| onCreate() | 액티비티 최초 생성 | UI 초기화, ViewModel 연결 |
| onStart() | 화면 표시 시작 | 센서·카메라 시작 |
| onResume() | 포커스 획득 (상호작용 가능) | 애니메이션 재개 |
| onPause() | 포커스 잃음 (다른 앱 위에 덮임) | 애니메이션 중지, 데이터 저장 |
| onStop() | 화면에서 완전히 사라짐 | 리소스 해제 |
| onDestroy() | 액티비티 소멸 | 최종 정리 |

## 생명주기 관련 문제

### Configuration Change (화면 회전)
- 기본: onDestroy → onCreate 재실행 → 데이터 손실
- 해결: **ViewModel** — onDestroy에도 살아남아 데이터 보존

### 메모리 누수 방지
`kotlin
// onStop에서 리스너 해제
override fun onStop() {
    super.onStop()
    locationManager.removeUpdates(locationListener)
}
`

## Lifecycle-aware Components
- LiveData — 활성 생명주기에서만 Observer 호출
- lifecycleScope — ViewModel의 생명주기와 연동된 코루틴 스코프

## Related Terms
- [[Android-App-Architecture]] — ViewModel로 생명주기 문제 해결
- [[Kotlin-Coroutines]] — lifecycleScope와 함께 사용

## References
- [Android Lifecycle Documentation](https://developer.android.com/guide/components/activities/activity-lifecycle)
