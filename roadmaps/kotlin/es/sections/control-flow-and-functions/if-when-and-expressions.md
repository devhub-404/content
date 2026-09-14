# `if` y `when` como Expressions

Kotlin es expression-oriented: `if`, `when` y blocks pueden producir valores. `when` cubre values, ranges, type tests, condiciones y sealed hierarchies.

```kotlin
val label = if (ready) "ready" else "waiting"

val result = when (status) {
    Status.READY -> "ready"
    Status.FAILED -> "failed"
    Status.PENDING -> "pending"
}
```

Usa branching como expression cuando una entrada se mapee a un resultado. Un `when` exhaustivo sobre enum/sealed hierarchy hace que nuevos casos aparezcan como errores de compilación.
