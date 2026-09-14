# Lambdas with Receiver and Type-safe Builders

A lambda with receiver such as `HtmlBuilder.() -> Unit` executes with a receiver available as `this`, making nested builder APIs read like a small language. Kotlin DSLs combine these lambdas with extensions, builders, and optional DSL-marker annotations.

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

A DSL should constrain users toward valid structures, not merely hide arbitrary function calls behind custom syntax. Keep nesting and implicit receivers understandable; DSL markers can prevent accidental access to receivers from outer levels.
