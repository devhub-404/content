# Smart Casts e Type Checks

`is` testa runtime type e Kotlin pode smart-cast quando prova que o valor é estável naquele control-flow path, eliminando muitos casts explícitos.

```kotlin
fun length(value: Any): Int = when (value) {
    is String -> value.length
    is Collection<*> -> value.size
    else -> 0
}
```

Smart casts dependem de estabilidade; property mutável que pode mudar entre check/use pode não servir. Guarde em local `val` ou redesenhe estado em vez de forçar cast.
