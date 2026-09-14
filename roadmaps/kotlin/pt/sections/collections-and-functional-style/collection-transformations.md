# Transformações de Collections

A standard library oferece `map`, `filter`, `associate`, `groupBy`, `partition`, `fold`, `zip` e sorting. Em collections comuns, operações são normalmente eager e criam resultados intermediários.

```kotlin
val activeNames = users
    .filter { it.active }
    .map { it.name }
    .sorted()
```

Chains são claras, mas podem alocar intermediários. Para datasets grandes ou short-circuit, `Sequence` ou loop pode reduzir trabalho quando medições justificarem.
