# Performance, Allocation y Boxing

Las abstracciones Kotlin pueden compilar eficientemente, pero el target importa. En JVM, nullable primitives, generics, lambdas, sequences e interface boundaries pueden introducir boxing/allocations; `IntArray` es especializado.

```kotlin
@JvmInline
value class UserId(val value: Long)

fun sum(values: IntArray): Int = values.sum()
```

Mide workloads reales antes de sustituir APIs claras por formas low-level. Perfila el runtime target, porque JIT/AOT, coroutines y libraries determinan el coste real.
