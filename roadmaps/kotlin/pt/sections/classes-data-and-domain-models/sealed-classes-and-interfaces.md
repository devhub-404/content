# Sealed Classes e Interfaces

Sealed classes/interfaces definem hierarquias restritas conhecidas pelo compiler e combinam naturalmente com `when` exaustivo e data classes.

```kotlin
sealed interface Result {
    data class Success(val value: String) : Result
    data class Failure(val message: String) : Result
}
```

Use para alternatives fechadas como results, UI states e messages. Use interface aberta quando terceiros devem poder implementar. Esse modelo também ajuda o compiler a verificar casos conhecidos quando a hierarquia é consumida com `when`.
