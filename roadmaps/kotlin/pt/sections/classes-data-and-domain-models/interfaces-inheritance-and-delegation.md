# Interfaces, Herança e Delegation

Classes são final por default; `open` é necessário para herança/override. Interfaces suportam comportamento default e delegation com `by` encaminha implementação a outro objeto sem boilerplate.

```kotlin
interface Repository {
    fun save(value: String)
}

class LoggingRepository(
    private val delegate: Repository
) : Repository by delegate
```

Prefira composição/delegation para reuso salvo relação de subtype real. Final-by-default reduz contratos de herança acidentais.
