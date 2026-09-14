# Performance, Allocation e Boxing

Abstrações Kotlin podem compilar eficientemente, mas target importa. Na JVM, nullable primitives, generics, lambdas, sequences e interface boundaries podem introduzir boxing/allocations; `IntArray` é especializado.

```kotlin
@JvmInline
value class UserId(val value: Long)

fun sum(values: IntArray): Int = values.sum()
```

Meça workloads reais antes de trocar APIs claras por formas low-level. Profile o runtime target, pois JIT/AOT, coroutines e libraries determinam custo real.
