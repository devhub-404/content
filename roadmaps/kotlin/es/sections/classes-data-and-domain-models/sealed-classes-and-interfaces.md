# Sealed Classes e Interfaces

Las sealed classes/interfaces definen jerarquías restringidas conocidas por el compiler y combinan naturalmente con `when` exhaustivo y data classes.

```kotlin
sealed interface Result {
    data class Success(val value: String) : Result
    data class Failure(val message: String) : Result
}
```

Úsalas para alternativas cerradas como results, UI states y messages. Usa una interface abierta cuando terceros deban poder implementar. Este modelo también ayuda al compiler a comprobar los casos conocidos cuando la jerarquía se consume con `when`.
