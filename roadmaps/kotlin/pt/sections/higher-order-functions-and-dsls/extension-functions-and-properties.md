# Extension Functions e Properties

Extensions permitem chamar functions/properties com syntax de receiver sem modificar/subclass o tipo. Resolução é estática pelo declared receiver e member real ganha de extension conflitante.

```kotlin
fun String.isBlankOrDash(): Boolean =
    isBlank() || this == "-"

val String.lastChar: Char
    get() = last()
```

Use para operações coesas que parecem comportamento natural. Evite despejar helpers sem relação em extensions amplas.
