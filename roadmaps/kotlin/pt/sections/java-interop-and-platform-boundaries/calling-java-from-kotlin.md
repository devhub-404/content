# Chamando Java a partir de Kotlin

Kotlin/JVM chama classes, methods, fields, annotations, SAM interfaces e libraries Java diretamente. O compiler adapta getters/setters para property syntax e não exige catch-or-declare para checked exceptions.

```kotlin
val list = java.util.ArrayList<String>()
list.add("Mina")

val instant = java.time.Instant.now()
```

Conveniência não muda o contrato Java. Observe mutability, raw types, failures, overloads e null retornado sem annotations.
