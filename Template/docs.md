## 52. 체크리스트 + 작업 관리

프로젝트 관리에도 활용 가능하다.

## 개발 진행 상황

### Backend

- [x] Entity
- [x] DTO
- [x] Repository
- [x] Service
- [ ] Controller
- [ ] Test

### Frontend

- [x] 화면 설계
- [ ] API 연결
- [ ] Error 처리
- [ ] Loading 처리

## 53. 변경 전/후 비교

Trouble Shooting에서 유용하다.

### Before

```java
User user = repository.findById(id).get();
```

### After

```java
User user = repository.findById(id)
    .orElseThrow(() -> new UserNotFoundException(id));
```
## 54. 문제 → 원인 → 해결 → 결과

네 프로젝트 문서에서 적극적으로 사용할 만한 형식이다.

# N+1 문제 해결 !!

## 문제

게시글 목록 조회 시 예상보다 많은 SQL이 실행되었다.

## 원인

Post와 User의 연관관계에서 Lazy Loading으로 인한
추가 조회가 발생했다.

## 해결

Fetch Join을 적용했다.

## 결과

게시글 목록 조회 시 발생하는 불필요한 쿼리를 줄였다.

## 55. 경고/주의사항 표현 !!

GitHub에서는 일반적으로 인용문 + 강조를 조합한다.

> **주의**
>
> `@Transactional`은 같은 클래스 내부에서 직접 호출할 경우
> Spring AOP 프록시가 적용되지 않을 수 있다.

## 56. 용어 정의 !!

학습 문서에 좋다.

## 용어

| 용어 | 의미 |
|---|---|
| Entity | DB 테이블과 매핑되는 객체 |
| DTO | 계층 간 데이터 전달 객체 |
| Repository | 데이터 접근 계층 |
57. 참고 자료

문서 마지막에:

## 참고 자료

- [Spring 공식 문서](https://spring.io/)
- [PostgreSQL 공식 문서](https://www.postgresql.org/docs/)
- [MDN](https://developer.mozilla.org/)
58. 문서 버전

필요하다면:

## 문서 정보

| 항목 | 내용 |
|---|---|
| 작성일 | 2026-08-14 |
| 수정일 | 2026-08-14 |
| 버전 | 1.0 |

하지만 모든 학습 문서에 넣을 필요는 없다.

Git 기록으로 변경 이력을 관리할 수 있기 때문이다.

59. 작성자 정보

프로젝트 README에서는:

## Author

**홍길동**

- GitHub: [github.com/example](https://github.com/example)
- Email: example@email.com

65. 접기 + API 목록

이건 프로젝트 README에서 상당히 추천한다.

<details>
<summary>API 목록</summary>

| Method | Endpoint | 설명 |
|---|---|---|
| GET | `/users` | 사용자 조회 |
| POST | `/users` | 사용자 생성 |
| PATCH | `/users/{id}` | 사용자 수정 |
| DELETE | `/users/{id}` | 사용자 삭제 |

</details>

## 66. 학습 문서에 추천하는 구조 !!

네가 앞으로 공부할 때는 모든 Markdown 문서를 복잡하게 만들 필요가 없어.

예를 들어 transaction.md:

# Spring Transaction

## 1. 개념

## 2. 동작 원리

## 3. 사용 방법

## 4. 예제

## 5. 주의사항

## 6. 내가 헷갈렸던 부분

## 7. 프로젝트 적용

## 8. 참고 자료

이 정도면 충분하다.

## 67. Trouble Shooting 문서 구조 !!
# 문제 제목

## 문제

무슨 문제가 발생했는가?

## 환경

- Java 17
- Spring Boot 3.x
- PostgreSQL

## 원인

왜 발생했는가?

## 해결

어떻게 해결했는가?

## 결과

무엇이 개선되었는가?

## 재발 방지

앞으로 어떻게 방지할 것인가?

## 68. 코드 리뷰 문서 구조 !!
# UserService 코드 리뷰

## 기존 코드

```java
```



---

# 69. 프로젝트 README 구조 !!!

네 프로젝트라면 이런 구조가 가장 활용도가 높아.

```md
# Project Name

프로젝트 한 줄 설명

## 목차

- [프로젝트 소개](#프로젝트-소개)
- [기술 스택](#기술-스택)
- [주요 기능](#주요-기능)
- [아키텍처](#아키텍처)
- [ERD](#erd)
- [API](#api)
- [Trouble Shooting](#trouble-shooting)
- [프로젝트 회고](#프로젝트-회고)

## 프로젝트 소개

## 기술 스택

## 주요 기능

## 아키텍처

## ERD

## API

## Trouble Shooting

## 프로젝트 회고

## 실행 방법

## 참고 자료

---
70. 가장 중요한 작성 원칙

Markdown 문법을 전부 사용할 필요는 없어.

네가 실제 개발 문서를 작성할 때 가장 많이 사용할 건 사실 이 정도다.

# 제목
## 소제목

**강조**
`코드`

```java
코드