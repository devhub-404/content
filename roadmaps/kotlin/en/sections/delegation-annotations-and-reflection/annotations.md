# Annotations

Annotations attach metadata to declarations, types, expressions, use-site targets, and other language elements. Kotlin frameworks use them for serialization, dependency injection, testing, Java interop, code generation, and compiler plugins.

```kotlin
@Deprecated("Use newApi instead")
fun oldApi() = Unit

@Target(AnnotationTarget.CLASS)
annotation class Feature(val name: String)
```

Annotations are passive metadata unless tooling or runtime code interprets them. Use use-site targets deliberately when one Kotlin declaration maps to several JVM elements such as a property, field, getter, constructor parameter, or method parameter.
