# Llamando Java desde Kotlin

Kotlin/JVM llama directamente a classes, methods, fields, annotations, SAM interfaces y libraries Java. El compiler adapta getters/setters a property syntax y no exige catch-or-declare para checked exceptions.

```kotlin
val list = java.util.ArrayList<String>()
list.add("Mina")

val instant = java.time.Instant.now()
```

La conveniencia no cambia el contrato Java. Presta atención a mutability, raw types, failures, overloads y null retornado sin annotations.
