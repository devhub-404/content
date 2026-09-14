# Type Parameters Reified

Type erasure normalmente impede testar generic parameter em runtime. Inline function com `reified` permite `is T`, class literals e helpers reflection com informação concreta inserida pelo compiler.

```kotlin
inline fun <reified T> Any?.isType(): Boolean = this is T

println(value.isType<String>())
```

Reified exige inline e funciona bem em wrappers pequenos. Para metadata runtime long-lived, `KClass`, `Class`, serializer ou descriptor explícito pode ser melhor.
