# Sequences and Lazy Pipelines

`Sequence<T>` provides lazy element-by-element pipelines. Intermediate sequence operations defer work until a terminal operation such as `toList`, `first`, `count`, or iteration requests values.

```kotlin
val result = generateSequence(1) { it + 1 }
    .map { it * it }
    .filter { it % 2 == 0 }
    .take(5)
    .toList()
```

Sequences help when many eager intermediate collections would be wasteful or when the pipeline can terminate early. For small collections and simple chains, ordinary collection operations can be faster and simpler because sequence iteration has its own overhead.
