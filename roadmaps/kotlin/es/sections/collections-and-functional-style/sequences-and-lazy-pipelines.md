# Sequences y Pipelines Lazy

`Sequence<T>` ofrece pipelines lazy elemento por elemento. Las intermediate operations aplazan trabajo hasta que una terminal operation o iteration pide valores.

```kotlin
val result = generateSequence(1) { it + 1 }
    .map { it * it }
    .filter { it % 2 == 0 }
    .take(5)
    .toList()
```

Las sequences ayudan cuando los intermedios eager serían costosos o hay early termination. Para collections pequeñas y chains simples, las operaciones normales pueden ser más rápidas y sencillas.
