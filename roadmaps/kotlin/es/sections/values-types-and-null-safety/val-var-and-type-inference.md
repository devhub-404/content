# `val`, `var` e Inferencia de Tipo

`val` declara un binding read-only y `var` uno reasignable. Kotlin infiere tipos locales cuando puede, pero el valor sigue teniendo un tipo estático. Un binding read-only no vuelve profundamente inmutable al objeto.

```kotlin
val name = "Mina"
var count = 0

count += 1
```

Prefiere `val` por defecto y `var` cuando el estado cambie de verdad. Las type annotations ayudan en boundaries públicos, collections vacías o cuando la inferencia queda demasiado específica.
