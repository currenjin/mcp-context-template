# 코드 리뷰 프롬프트 예시

"다음 코드를 리뷰해줘. 성능, 가독성, 유지보수성, 명명 규칙 위반 여부를 중심으로 평가해줘."

```kotlin
fun calculateDiscount(amount: Int): Int {
    return if (amount > 10000) 1000 else 0
}