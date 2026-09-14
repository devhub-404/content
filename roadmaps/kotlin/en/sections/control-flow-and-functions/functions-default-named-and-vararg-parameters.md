# Functions, Default, Named, and Vararg Parameters

Kotlin functions can have default parameter values, named arguments, expression bodies, generic parameters, and one `vararg` parameter. These features let APIs avoid many overloads that Java would otherwise require.

```kotlin
fun connect(
    host: String,
    port: Int = 443,
    secure: Boolean = true
) { /* ... */ }

connect(host = "example.com", secure = false)
```

Use named arguments to clarify Boolean or same-typed parameters, but remember Java callers may not see the same source-level conveniences. For public libraries with Java consumers, design overloads and JVM annotations deliberately.
