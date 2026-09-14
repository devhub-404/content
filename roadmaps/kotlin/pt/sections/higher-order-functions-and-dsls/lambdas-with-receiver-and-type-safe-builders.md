# Lambdas com Receiver e Type-safe Builders

Lambda com receiver como `HtmlBuilder.() -> Unit` executa com receiver como `this`, permitindo builder APIs parecidas com linguagem. DSLs combinam isso com extensions, builders e DSL markers.

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

DSL deve guiar para estruturas válidas, não apenas esconder calls. Mantenha nesting/receivers claros; DSL markers evitam acesso acidental a receivers externos.
