# MCP Context Template (English Version)

## Introduction
MCP Context Template is a repository designed to centrally manage AI tools (MCP - Model Centralized Prompting) to reduce context sharing costs and improve development productivity.

It serves as a central context repository that helps modern AI tools like Claude Code and Cursor AI consistently understand your company's codebase and development practices.

## Purpose
* Common context repository managed independently from individual projects
* Providing reference document structure to improve collaboration efficiency with AI tools
* Containing examples and guides that can be used by different teams and organizational layers
* Providing consistent AI usage experience across projects
* Reducing the burden of duplicate context management

## Directory Structure

```
ai-context/
├── README.md
├── context/
│   ├── backend/
│   │   ├── domain-overview.md
│   │   ├── service-patterns.md
│   │   └── test-guidelines.md
│   ├── frontend/
│   │   ├── component-structure.md
│   │   └── naming-convention.md
│   ├── mobile/
│   │   └── network-layer.md
│   └── shared/
│       ├── business-terms.md
│       └── naming-style.md
├── prompts/
│   ├── refactoring.md
│   ├── test-generation.md
│   └── code-review.md
└── examples/
├── cursor-snippets.md
└── claude-usage.md
```

## How to Use

### 1. Project Integration
* Set `ai-context/` as a context path in your project's `.cloderc` or Cursor settings
* Explicitly reference guides in Claude Code prompts with "Please refer to the following guide: [path]"
* Example: Request refactoring based on `context/backend/service-patterns.md`

```
Refactoring request:
Please refactor the following code according to the service patterns defined in context/backend/service-patterns.md.

[INSERT CODE]
```

### 2. Contribution Guidelines
* Contribute via Pull Request
* Write all convention documents in Markdown
* Propose significant context structure changes as issues first for discussion
* Write context concisely and clearly for easy AI understanding

### 3. Prompt Writing Examples

Example from `prompts/test-generation.md`:
```markdown
## Purpose
Claude prompt example for automating service unit test generation

## Prompt
Please write unit test code for the following service class method:
- Test framework: JUnit5
- Mocking: MockK
- Use Given-When-Then format
- Target method:
```kotlin
fun getUserById(id: Long): User
```

## Use Cases
* New developer onboarding - quickly understand code styles and patterns
* Automation of repetitive coding tasks - generating test code, boilerplate
* Code review automation - generate review comments with consistent standards
* Documentation support - assist in codebase documentation tasks

---

# MCP Context Template(Korean)

## 소개
MCP Context Template은 AI 도구(MCP - Model Centralized Prompting)를 "중앙 집중식"으로 관리하여 컨텍스트 공유 비용을 줄이고 개발 생산성을 높이기 위한 레포지토리입니다.

Claude Code, Cursor AI 등 최신 AI 도구들이 일관된 방식으로 회사의 코드베이스와 개발 관행을 이해할 수 있도록 돕는 중앙 컨텍스트 저장소로 기능합니다.

## 목적
* 프로젝트와 독립적으로 관리되는 공통 컨텍스트 저장소
* AI 도구와의 협업 효율을 높이기 위한 참고 문서 구조 제공
* 팀별, 계층별로 활용 가능한 예시와 가이드 수록
* 프로젝트 간 일관된 AI 사용 경험 제공
* 중복 컨텍스트 관리 부담 감소

## 디렉토리 구조

```
ai-context/
├── README.md
├── context/
│   ├── backend/
│   │   ├── domain-overview.md
│   │   ├── service-patterns.md
│   │   └── test-guidelines.md
│   ├── frontend/
│   │   ├── component-structure.md
│   │   └── naming-convention.md
│   ├── mobile/
│   │   └── network-layer.md
│   └── shared/
│       ├── business-terms.md
│       └── naming-style.md
├── prompts/
│   ├── refactoring.md
│   ├── test-generation.md
│   └── code-review.md
└── examples/
    ├── cursor-snippets.md
    └── claude-usage.md
```

## 활용 방법

### 1. 프로젝트에서의 활용
* 프로젝트 내 `.cloderc` 또는 Cursor 설정에서 `ai-context/`를 context path로 지정
* Claude Code 프롬프트 작성 시 "다음 가이드를 참고해주세요: [경로]"와 같이 명시적으로 언급
* 예시: `context/backend/service-patterns.md`에 기반한 리팩토링 요청

```
리팩토링 요청:
context/backend/service-patterns.md에 정의된 서비스 패턴에 따라 다음 코드를 리팩토링해 주세요.

[코드 삽입]
```

### 2. 문서 기여 가이드
* Pull Request를 통해 기여
* 모든 컨벤션 문서는 Markdown으로 작성
* 큰 컨텍스트 구조 변경은 이슈로 먼저 제안 후 논의
* 컨텍스트는 간결하고 명확하게 작성하여 AI가 이해하기 쉽게 구성

### 3. 프롬프트 작성 예시

`prompts/test-generation.md` 예시:

```markdown
## 목적
서비스 단위 테스트 자동화를 위한 Claude용 프롬프트 예시

## 프롬프트
서비스 클래스의 메서드에 대해 단위 테스트 코드를 작성해주세요.
- 테스트 프레임워크: JUnit5
- 모킹: MockK
- Given-When-Then 형식 사용
- 테스트 대상 메서드:

```kotlin
fun getUserById(id: Long): User
```

## 활용 사례
* 새로운 개발자 온보딩 - 코드 스타일과 패턴을 빠르게 이해
* 반복적인 코드 작업 자동화 - 테스트 코드, 보일러플레이트 생성
* 코드 리뷰 자동화 - 일관된 기준으로 리뷰 코멘트 생성
* 문서화 지원 - 코드베이스 문서화 작업 보조

---
