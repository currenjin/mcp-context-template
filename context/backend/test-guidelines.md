# 테스트 가이드

이 문서는 백엔드 시스템 테스트 작성 시의 원칙 및 도구 사용 방법을 안내합니다.

## 1. 테스트 프레임워크

- 기본: JUnit5
- Mock 라이브러리: MockK
- Controller 테스트: MockMvc

## 2. 테스트 종류 및 우선순위

| 테스트 종류 | 목적 | 사용 도구 |
|--------------|------|------------|
| 단위 테스트 | 개별 메서드 검증 | JUnit5, MockK |
| 통합 테스트 | 모듈 간 상호작용 | SpringBootTest |
| 문서화 테스트 | API 문서 생성 | RestDocs, MockMvc |

## 3. 작성 예시

```kotlin
@WebMvcTest(UserController::class)
class UserControllerTest {

    @MockBean
    private lateinit var userFacade: UserFacade

    @Autowired
    private lateinit var mockMvc: MockMvc

    @Test
    fun `사용자 조회 API는 200을 반환한다`() {
        // given
        val response = UserResponse.Detail(...)
        every { userFacade.getUser(any()) } returns response

        // when, then
        mockMvc.perform(get("/users/1"))
            .andExpect(status().isOk)
            .andDo(document("user-get"))
    }
}
```