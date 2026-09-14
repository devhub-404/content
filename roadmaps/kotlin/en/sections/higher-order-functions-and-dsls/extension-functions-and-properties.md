# Extension Functions and Properties

Extensions let functions and properties be called with receiver syntax without modifying or subclassing the target type. They are resolved statically from the declared receiver type, and a real member wins over an extension with the same applicable signature.

```kotlin
fun String.isBlankOrDash(): Boolean =
    isBlank() || this == "-"

val String.lastChar: Char
    get() = last()
```

Use extensions for cohesive operations that naturally read as behavior of a type or domain. Avoid dumping unrelated helpers into broad extensions that make APIs hard to discover and name conflicts more likely.
