# Performance, Allocation, and Boxing

Kotlin abstractions can compile efficiently, but target details matter. On JVM, nullable primitives, generic type parameters, lambdas, sequences, and interface boundaries can introduce boxing or allocations, while specialized arrays such as `IntArray` store primitives directly.

```kotlin
@JvmInline
value class UserId(val value: Long)

fun sum(values: IntArray): Int = values.sum()
```

Measure real optimized workloads before replacing clear APIs with low-level forms. Profile the target runtime, not Kotlin source in isolation, because JIT/AOT behavior, coroutine machinery, and platform libraries determine actual cost.
