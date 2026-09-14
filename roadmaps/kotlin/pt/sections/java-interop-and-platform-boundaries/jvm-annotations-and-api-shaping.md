# JVM Annotations e Formato de API

Annotations como `@JvmStatic`, `@JvmOverloads`, `@JvmField` e `@JvmName` ajustam como declarations aparecem para Java/bytecode. São ferramentas de interop, não syntax obrigatória do dia a dia.

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

Ao publicar JVM library, desenhe Java-facing API deliberadamente. Defaults, nullability, suspend, value classes, properties e companions podem precisar adapters.
