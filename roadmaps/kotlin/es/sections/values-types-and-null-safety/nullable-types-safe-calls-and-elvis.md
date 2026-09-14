# Tipos Nullable, Safe Calls y Elvis

La nullability forma parte del tipo: `String` no acepta null y `String?` sí. Safe call `?.` propaga null y Elvis `?:` ofrece fallback.

```kotlin
val nickname: String? = findNickname()

val display = nickname?.trim()?.takeIf { it.isNotEmpty() }
    ?: "anonymous"
```

Evita `!!` como escape rutinario porque convierte incertidumbre en posible `NullPointerException`. Prefiere modelar ausencia, validar invariantes o usar APIs que retornen non-null tras comprobar.
