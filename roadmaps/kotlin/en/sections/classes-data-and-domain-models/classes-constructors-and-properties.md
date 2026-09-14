# Classes, Constructors, and Properties

Primary constructor parameters live in the class header and become properties when declared with `val` or `var`. Secondary constructors, init blocks, custom accessors, visibility modifiers, and backing fields cover more complex initialization and property behavior.

```kotlin
class Account(
    val owner: String,
    initialBalance: Long = 0
) {
    var balance: Long = initialBalance
        private set
}
```

Keep invariants in the type rather than exposing every property as mutable. Kotlin properties are language-level abstractions, not just public fields, and custom getters/setters can preserve a stable API while implementation changes.
