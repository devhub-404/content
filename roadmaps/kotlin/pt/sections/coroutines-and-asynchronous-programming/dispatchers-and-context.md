# Dispatchers e Coroutine Context

Coroutine context carrega dispatcher, job, name e outros elementos. Dispatchers decidem onde código roda: pools CPU, I/O, main/UI ou custom conforme plataforma.

```kotlin
withContext(Dispatchers.IO) {
    Files.readString(path)
}
```

Troque context deliberadamente para trabalho blocking/platform-specific, não em toda função. Libraries normalmente devem expor suspend sem hard-code de dispatcher salvo implementação bloqueante própria.
