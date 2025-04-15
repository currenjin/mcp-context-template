# 테스트 자동 생성 프롬프트 예시

"다음 Kotlin 코드에 대한 단위 테스트 코드를 작성해줘. 테스트는 MockK와 JUnit5를 기반으로 해줘."

```kotlin
class OrderService(private val repository: OrderRepository) {
    fun getById(id: Long): Order {
        return repository.getById(id)
    }
}
```