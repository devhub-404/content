# Type Aliases

Un type alias crea otro nombre source-level para un tipo existente, incluidos function/generic types. Mejora lectura, pero no crea identidad distinta de tipo.

```kotlin
typealias UserId = String
typealias Handler = (Request) -> Response
```

Usa value class/wrapper cuando valores con la misma representación no deban mezclarse. Usa alias cuando la identidad deba seguir igual y el objetivo sea solo nombrar un tipo verboso.
