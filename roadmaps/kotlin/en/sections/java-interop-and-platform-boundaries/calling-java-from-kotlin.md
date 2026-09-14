# Calling Java from Kotlin

Kotlin/JVM calls Java classes, methods, fields, annotations, SAM interfaces, and libraries directly. The compiler adapts common Java idioms such as getters/setters into Kotlin property syntax and handles checked exceptions without requiring catch-or-declare syntax.

```kotlin
val list = java.util.ArrayList<String>()
list.add("Mina")

val instant = java.time.Instant.now()
```

Interop convenience does not change the underlying Java contract. Pay attention to mutability, raw types, checked failures, overloads, and whether Java APIs may return null without Kotlin annotations.
