# Nullable Types, Safe Calls, and Elvis

Nullability is part of Kotlin types: `String` does not accept null, while `String?` does. Safe calls `?.` propagate null, the Elvis operator `?:` provides a fallback, and nullable-aware library functions help keep absence handling explicit.

```kotlin
val nickname: String? = findNickname()

val display = nickname?.trim()?.takeIf { it.isNotEmpty() }
    ?: "anonymous"
```

Avoid using `!!` as a routine escape hatch because it converts an uncertain value into a possible runtime `NullPointerException`. Prefer modeling absence, checking invariants once, or using APIs that return a non-null value after validation.
