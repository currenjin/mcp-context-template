# 네이밍 컨벤션

## 컴포넌트
- PascalCase 사용 (e.g., `UserProfileCard.tsx`)

## 파일
- 기능 단위 kebab-case 사용 (e.g., `user-profile.tsx`)

## 클래스 이름 (Tailwind 기준)
- BEM 방식 대신 역할 위주의 명명 사용
- 조건부 클래스는 명확히 구분 (`is-active`, `has-error`)

## 훅
- `use` 접두어 필수 (e.g., `useUserFetch`)