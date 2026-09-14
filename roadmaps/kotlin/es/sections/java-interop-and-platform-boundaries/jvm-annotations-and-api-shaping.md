# JVM Annotations y Forma de API

Annotations como `@JvmStatic`, `@JvmOverloads`, `@JvmField` y `@JvmName` ajustan cómo declarations aparecen para Java/bytecode. Son herramientas de interop, no sintaxis obligatoria diaria.

```kotlin
class Api {
    companion object {
        @JvmStatic
        fun create(): Api = Api()
    }

    @JvmOverloads
    fun connect(host: String, port: Int = 443) { }
}
```

Al publicar una JVM library, diseña deliberadamente la API para Java. Defaults, nullability, suspend, value classes, properties y companions pueden necesitar adapters.
