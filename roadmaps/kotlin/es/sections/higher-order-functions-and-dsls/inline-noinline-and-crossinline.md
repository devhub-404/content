# `inline`, `noinline` y `crossinline`

Inlinear una higher-order function puede eliminar overhead de function object/call y habilita non-local returns y reified types. `noinline`/`crossinline` restringen lambdas cuando se almacenan o llaman en otro contexto.

```kotlin
inline fun measure(block: () -> Unit): Long {
    val start = System.nanoTime()
    block()
    return System.nanoTime() - start
}
```

No marques todo inline. Aumenta generated code y tiene sentido cuando overhead, reified types o control flow aportan un beneficio real.
