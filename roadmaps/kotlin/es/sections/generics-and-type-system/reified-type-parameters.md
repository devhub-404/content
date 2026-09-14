# Type Parameters Reified

El type erasure normalmente impide probar un generic parameter en runtime. Una inline function con `reified` permite `is T`, class literals y helpers de reflection con información concreta insertada por el compiler.

```kotlin
inline fun <reified T> Any?.isType(): Boolean = this is T

println(value.isType<String>())
```

Reified exige inline y funciona bien en wrappers pequeños. Para metadata runtime long-lived, `KClass`, `Class`, serializer o descriptor explícito puede ser mejor.
