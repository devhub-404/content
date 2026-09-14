# Smart Casts and Type Checks

The `is` operator tests a runtime type, and Kotlin can smart-cast a value after proving that its type is stable on that control-flow path. This removes many explicit casts that would be required in Java.

```kotlin
fun length(value: Any): Int = when (value) {
    is String -> value.length
    is Collection<*> -> value.size
    else -> 0
}
```

Smart casts depend on stability: a mutable property or value that could change between the check and use may not be eligible. When the compiler refuses a smart cast, preserve the value in a local `val` or redesign the state relationship instead of forcing casts blindly.
