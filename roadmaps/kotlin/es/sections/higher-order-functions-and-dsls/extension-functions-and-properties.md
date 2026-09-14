# Extension Functions y Properties

Las extensions permiten llamar functions/properties con sintaxis de receiver sin modificar/subclass el tipo. La resolución es estática según el declared receiver y un member real gana frente a una extension conflictiva.

```kotlin
fun String.isBlankOrDash(): Boolean =
    isBlank() || this == "-"

val String.lastChar: Char
    get() = last()
```

Úsalas para operaciones cohesionadas que parezcan comportamiento natural. Evita volcar helpers no relacionados en extensions amplias.
