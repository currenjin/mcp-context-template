# 리팩토링 프롬프트 예시

"다음 코드를 더 읽기 좋고 테스트하기 쉬운 형태로 리팩토링해줘. 가능한 경우 함수 분리, 변수 명확화, guard clause를 사용해줘."

```kotlin
fun getDiscount(user: User): Int {
    if (user.age > 60) {
        return 30
    } else {
        if (user.age > 30) {
            return 10
        } else {
            return 0
        }
    }
}
```