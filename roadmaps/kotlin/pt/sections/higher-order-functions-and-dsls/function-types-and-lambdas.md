# Function Types e Lambdas

Function types descrevem callables diretamente e lambdas podem ser passadas, retornadas, armazenadas e capturadas. Kotlin também suporta receiver function types, importantes para DSLs.

```kotlin
val transform: (Int) -> Int = { value -> value * 2 }

fun apply(value: Int, fn: (Int) -> Int): Int = fn(value)
```

Higher-order functions servem a policies, callbacks e transforms pequenos. Se o callback carrega estado mutável long-lived ou muitas operações, interface/class pode dar nome e lifecycle mais claros.
