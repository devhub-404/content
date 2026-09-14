# JVM Annotations and API Shaping

Annotations such as `@JvmStatic`, `@JvmOverloads`, `@JvmField`, `@JvmName`, and file-level JVM names adjust how Kotlin declarations appear to Java callers or in bytecode. They are interoperability tools, not everyday syntax requirements.

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

Design the Java-facing API deliberately when publishing JVM libraries. Kotlin defaults, nullability, suspend functions, value classes, properties, and companion members may need adapters or annotations for ergonomic Java consumption.
