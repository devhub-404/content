# Compatibilidade Binária e Evolução de Libraries

Libraries Kotlin publicadas têm compatibilidade source, binary, metadata e platform-specific. Mudanças pequenas em defaults, inline, sealed hierarchies, interfaces ou JVM signatures podem afetar consumers.

```kotlin
public interface Clock {
    fun now(): Instant
}
```

Mantenha API pública pequena, versionamento deliberado e teste consumers quando compatibilidade importa. Multiplatform também envolve target availability e metadata.
