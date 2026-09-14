# Delegated Properties

Property delegation lets another object provide getter/setter behavior. Standard delegates include `lazy`, observable/vetoable helpers, map-backed properties, and delegates supplied by frameworks such as UI and dependency-injection systems.

```kotlin
val config by lazy {
    loadConfiguration()
}

var name: String by Delegates.observable("") { _, old, new ->
    println("$old -> $new")
}
```

Delegation can centralize repeated property behavior, but it also hides work behind normal property syntax. Avoid expensive or surprising side effects in a property access unless the contract makes them obvious.
