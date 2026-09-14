# Tipos Nullable, Safe Calls e Elvis

Nullability faz parte do tipo: `String` não aceita null e `String?` aceita. Safe call `?.` propaga null e Elvis `?:` fornece fallback.

```kotlin
val nickname: String? = findNickname()

val display = nickname?.trim()?.takeIf { it.isNotEmpty() }
    ?: "anonymous"
```

Evite `!!` como escape rotineiro porque transforma incerteza em possível `NullPointerException`. Prefira modelar ausência, validar invariantes ou usar APIs que retornem non-null após check.
