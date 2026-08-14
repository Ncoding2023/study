
## 44. Mermaid 다이어그램 !!
```mermaid
flowchart TD
    Client --> Controller
    Controller --> Service
    Service --> Repository
    Repository --> Database
```

## 45. Mermaid Sequence Diagram !!

API 흐름을 표현하기 좋다.

```mermaid
sequenceDiagram
    Client->>Controller: POST /login
    Controller->>Service: login()
    Service->>Repository: findUser()
    Repository-->>Service: User
    Service-->>Controller: Token
    Controller-->>Client: Response
```

## 46. Mermaid ERD

데이터베이스 관계를 표현할 수도 있다.

```mermaid
erDiagram
    USER ||--o{ POST : writes
    POST ||--o{ COMMENT : has

    USER {
        bigint id
        varchar email
    }

    POST {
        bigint id
        bigint user_id
        varchar title
    }

    COMMENT {
        bigint id
        bigint post_id
        text content
    }
```

47. Mermaid State Diagram

상태 흐름을 표현할 때:

```mermaid
stateDiagram-v2
    [*] --> CREATED
    CREATED --> ACTIVE
    ACTIVE --> COMPLETED
    ACTIVE --> CANCELLED
```

48. Mermaid Class Diagram

클래스 관계를 표현할 수 있다.

```mermaid
classDiagram
    User --> Post
    Post --> Comment

    class User {
        +Long id
        +String name
    }

    class Post {
        +Long id
        +String title
    }
```
49. Mermaid Git Graph

Git 흐름을 표현할 수도 있다.

```mermaid
gitGraph
    commit
    branch develop
    checkout develop
    commit
    checkout main
    merge develop
```