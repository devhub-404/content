# Basic Types and Numbers

Kotlin exposes numeric, Boolean, character, string, array, and other standard types with a uniform object-like syntax. Numeric types do not perform broad implicit widening conversions: converting an `Int` to `Long` is explicit.

```kotlin
val age: Int = 42
val total: Long = 8_000_000_000L
val ratio: Double = 0.75
val enabled: Boolean = true
val letter: Char = 'K' 
```

Choose a numeric type from range and API needs. On the JVM, primitives can often compile to primitive representations where possible even though source syntax is uniform. Exact decimal money still needs a decimal type such as Java `BigDecimal` on JVM targets.
