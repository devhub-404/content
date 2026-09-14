# `inline`, `noinline`, and `crossinline`

Inlining a higher-order function can remove function-object and call overhead and also enables non-local returns and reified type parameters in suitable cases. `noinline` and `crossinline` restrict selected lambda parameters when the implementation stores them or invokes them in another context.

```kotlin
inline fun measure(block: () -> Unit): Long {
    val start = System.nanoTime()
    block()
    return System.nanoTime() - start
}
```

Do not mark every function inline. Inlining increases generated code and only makes sense when higher-order overhead, reified types, or control-flow behavior provides a real benefit.
