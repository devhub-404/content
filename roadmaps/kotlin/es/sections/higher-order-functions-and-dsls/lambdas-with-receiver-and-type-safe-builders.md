# Lambdas con Receiver y Type-safe Builders

Una lambda con receiver como `HtmlBuilder.() -> Unit` se ejecuta con un receiver disponible como `this`, permitiendo builder APIs parecidas a un lenguaje. Las DSLs combinan esto con extensions, builders y DSL markers.

```kotlin
class HtmlBuilder {
    fun h1(text: String) { /* ... */ }
}

fun html(block: HtmlBuilder.() -> Unit) =
    HtmlBuilder().apply(block)

html {
    h1("Hello")
}
```

Una DSL debe guiar hacia estructuras válidas, no solo esconder calls. Mantén nesting/receivers claros; los DSL markers evitan acceso accidental a receivers externos.
