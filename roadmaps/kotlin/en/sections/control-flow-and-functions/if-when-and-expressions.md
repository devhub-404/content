# `if` and `when` as Expressions

Kotlin is expression-oriented: `if`, `when`, and blocks can produce values. `when` replaces many switch-style patterns and can branch on values, ranges, type tests, arbitrary Boolean conditions, or sealed hierarchies.

```kotlin
val label = if (ready) "ready" else "waiting"

val result = when (status) {
    Status.READY -> "ready"
    Status.FAILED -> "failed"
    Status.PENDING -> "pending"
}
```

Use expression-style branching when one input naturally maps to one result. An exhaustive `when` over an enum or sealed hierarchy is valuable because adding a new case can produce compiler errors where handling must be updated.
