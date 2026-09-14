# Smart Casts y Type Checks

El operador `is` prueba runtime type y Kotlin puede smart-cast cuando demuestra que el valor es estable en ese control-flow path, eliminando muchos casts explícitos.

```kotlin
fun length(value: Any): Int = when (value) {
    is String -> value.length
    is Collection<*> -> value.size
    else -> 0
}
```

Los smart casts dependen de estabilidad; una property mutable que podría cambiar entre check/use puede no servir. Guarda en un local `val` o rediseña el estado en vez de forzar un cast.
