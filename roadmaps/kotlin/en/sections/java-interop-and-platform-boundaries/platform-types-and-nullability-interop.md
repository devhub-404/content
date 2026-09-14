# Platform Types and Java Nullability

When Java nullability information is incomplete, Kotlin uses platform types internally, allowing either nullable or non-null use with reduced compiler guarantees. Modern Java annotations can improve that boundary, but legacy APIs often remain uncertain.

```kotlin
val value = javaApi.findName() // may be String! internally

val safe: String? = value
val required: String = requireNotNull(value)
```

Treat platform values as trust-boundary data. Assign them to an explicit nullable or non-null Kotlin type and validate once rather than letting uncertain nullability flow through many layers.
