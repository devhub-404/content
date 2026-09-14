# Sequences e Pipelines Lazy

`Sequence<T>` fornece pipelines lazy element-by-element. Intermediate operations adiam trabalho até terminal operation ou iteration pedir valores.

```kotlin
val result = generateSequence(1) { it + 1 }
    .map { it * it }
    .filter { it % 2 == 0 }
    .take(5)
    .toList()
```

Sequences ajudam quando intermediários eager seriam caros ou há early termination. Para collections pequenas e chains simples, operações comuns podem ser mais rápidas e simples.
