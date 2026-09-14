# `val`, `var`, and Type Inference

`val` declares a read-only binding and `var` a reassignable binding. Kotlin infers local types from initializers when possible, but the value still has one static compile-time type. Read-only binding does not mean the referenced object is deeply immutable.

```kotlin
val name = "Mina"
var count = 0

count += 1
```

Prefer `val` by default and use `var` where state genuinely changes. Explicit type annotations are useful at public boundaries, for empty collections, or when the inferred type is more specific than the intended abstraction.
