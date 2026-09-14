# Sealed Classes and Interfaces

Sealed classes and interfaces define restricted hierarchies whose direct subclasses are known to the compiler within the permitted scope. They pair naturally with exhaustive `when` expressions and data classes for algebraic domain states.

```kotlin
sealed interface Result {
    data class Success(val value: String) : Result
    data class Failure(val message: String) : Result
}
```

Use sealed hierarchies for closed alternatives such as results, UI states, commands, and protocol messages. Use an ordinary open interface when independent libraries or future third parties should be able to add implementations.
