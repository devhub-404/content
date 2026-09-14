# Annotations

Annotations anexam metadata a declarations, types, expressions e use-site targets. Frameworks usam em serialization, DI, testing, Java interop, code generation e compiler plugins.

```kotlin
@Deprecated("Use newApi instead")
fun oldApi() = Unit

@Target(AnnotationTarget.CLASS)
annotation class Feature(val name: String)
```

Annotations são passivas até tooling/runtime interpretá-las. Use use-site targets conscientemente quando uma property Kotlin mapeia a vários elementos JVM. Use o recurso quando ele expressa um contrato real; evitar abstrações desnecessárias mantém a API mais simples de ler.
