# `inline`, `noinline` e `crossinline`

Inline de higher-order function pode remover overhead de function object/call e habilita non-local returns e reified types. `noinline`/`crossinline` restringem lambdas quando são armazenadas ou chamadas em outro contexto.

```kotlin
inline fun measure(block: () -> Unit): Long {
    val start = System.nanoTime()
    block()
    return System.nanoTime() - start
}
```

Não marque tudo inline. Isso aumenta generated code e faz sentido quando overhead, reified types ou control flow realmente trazem benefício.
