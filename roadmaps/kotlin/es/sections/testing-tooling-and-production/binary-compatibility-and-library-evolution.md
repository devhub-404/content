# Compatibilidad Binaria y Evolución de Libraries

Las libraries Kotlin publicadas tienen compatibilidad source, binary, metadata y platform-specific. Cambios pequeños en defaults, inline, sealed hierarchies, interfaces o JVM signatures pueden afectar consumers.

```kotlin
public interface Clock {
    fun now(): Instant
}
```

Mantén la API pública pequeña, versionado deliberado y prueba consumers cuando importe compatibilidad. Multiplatform también implica target availability y metadata.
