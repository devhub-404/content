# `if` e `when` como Expressions

Kotlin é expression-oriented: `if`, `when` e blocks podem produzir valores. `when` cobre values, ranges, type tests, condições e sealed hierarchies.

```kotlin
val label = if (ready) "ready" else "waiting"

val result = when (status) {
    Status.READY -> "ready"
    Status.FAILED -> "failed"
    Status.PENDING -> "pending"
}
```

Use branching como expression quando uma entrada mapeia para um resultado. `when` exaustivo sobre enum/sealed hierarchy faz novos casos aparecerem como erros de compilação.
