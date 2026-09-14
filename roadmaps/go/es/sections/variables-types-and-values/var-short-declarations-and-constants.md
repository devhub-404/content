# `var`, Declaración Corta y Constants

`var` declara variables explícitamente y puede inferir el tipo desde el initializer. Dentro de funciones, `:=` es la forma corta y debe declarar al menos una variable nueva en el scope actual. Las constants son valores de compile time con reglas propias de representabilidad y untyped constants.

```go
var host string = "example.com"
port := 443

const timeoutSeconds = 30
const Pi = 3.141592653589793
```

Usa short declarations para locals cuando el tipo sea obvio, pero presta atención al shadowing en scopes anidados. Las constants pueden permanecer untyped hasta que el contexto les dé un tipo concreto, haciendo flexibles las constantes numéricas.
