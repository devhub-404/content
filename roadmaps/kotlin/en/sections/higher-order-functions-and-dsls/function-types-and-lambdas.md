# Function Types and Lambdas

Function types describe callable values directly, and lambdas can be passed, returned, stored, and captured. Kotlin has syntax for receivers in function types too, enabling blocks that behave as if methods of another object were in scope.

```kotlin
val transform: (Int) -> Int = { value -> value * 2 }

fun apply(value: Int, fn: (Int) -> Int): Int = fn(value)
```

Higher-order functions are natural for small policies, callbacks, transformations, and DSLs. If a callback carries long-lived mutable state or many operations, an interface or class can give the behavior a clearer name and lifecycle.
