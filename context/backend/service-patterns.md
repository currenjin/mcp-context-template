# Backend Service 패턴 가이드

이 문서는 백엔드 개발 시 사용하는 서비스 계층 패턴에 대한 가이드입니다.

## 기본 구조

- 단일 책임 원칙을 지키기 위해 역할 별 클래스를 분리
- 각 서비스는 명확한 역할을 갖고 작동

| 접미사 | 역할 설명 |
|--------|----------|
| `Saver` | 생성 및 저장 담당 |
| `Reader` | 조회 담당 |
| `Updater` | 수정 담당 |
| `Deleter` | 삭제 담당 |
| `Processor` | 여러 서비스를 조합하여 비즈니스 로직 처리 |

## 예시 구조

```kotlin
@Service
class UserReader(private val userRepository: UserRepository) {
    fun findById(id: Long): User = userRepository.getById(id)
}

@Service
class UserProfileProcessor(
    private val userReader: UserReader,
    private val profileUpdater: ProfileUpdater
) {
    fun updateUserProfile(id: Long, profile: Profile): UserProfile {
        val user = userReader.findById(id)
        val updatedProfile = profileUpdater.update(user.profileId, profile)
        return UserProfile(user, updatedProfile)
    }
}

@Component
class UserFacade(
    private val userProfileProcessor: UserProfileProcessor
) {
    fun updateProfile(request: ProfileUpdateRequest): ProfileResponse {
        val result = userProfileProcessor.updateUserProfile(
            request.userId,
            request.toProfile()
        )
        return ProfileResponse.from(result)
    }
}
```
