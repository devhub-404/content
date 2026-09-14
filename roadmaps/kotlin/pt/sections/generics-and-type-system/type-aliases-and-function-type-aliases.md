# Type Aliases

Type alias cria outro nome source-level para tipo existente, inclusive function/generic types. Melhora leitura, mas não cria identidade distinta de tipo.

```kotlin
typealias UserId = String
typealias Handler = (Request) -> Response
```

Use value class/wrapper quando valores com mesma representação não podem se misturar. Use alias quando identidade deve permanecer igual e o objetivo é apenas nomear tipo verboso.
