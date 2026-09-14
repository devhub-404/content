# Annotations

Las annotations adjuntan metadata a declarations, types, expressions y use-site targets. Los frameworks las usan para serialización, DI, testing, Java interop, code generation y compiler plugins.

```kotlin
@Deprecated("Use newApi instead")
fun oldApi() = Unit

@Target(AnnotationTarget.CLASS)
annotation class Feature(val name: String)
```

Las annotations son pasivas hasta que tooling/runtime las interprete. Usa use-site targets deliberadamente cuando una property Kotlin se mapee a varios elementos JVM.
