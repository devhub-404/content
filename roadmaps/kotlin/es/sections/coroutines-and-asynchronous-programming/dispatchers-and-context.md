# Dispatchers y Coroutine Context

El coroutine context transporta dispatcher, job, name y otros elementos. Los dispatchers deciden dónde corre el código: pools CPU, I/O, main/UI o custom según plataforma.

```kotlin
withContext(Dispatchers.IO) {
    Files.readString(path)
}
```

Cambia context deliberadamente para trabajo blocking/platform-specific, no en cada función. Las libraries normalmente deberían exponer suspend sin hard-codear dispatcher salvo implementación bloqueante propia.
