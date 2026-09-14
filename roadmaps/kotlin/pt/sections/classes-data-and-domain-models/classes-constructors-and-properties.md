# Classes, Constructors e Properties

Primary constructor parameters ficam no header e viram properties com `val`/`var`. Secondary constructors, init blocks, accessors e backing fields cobrem inicialização mais complexa.

```kotlin
class Account(
    val owner: String,
    initialBalance: Long = 0
) {
    var balance: Long = initialBalance
        private set
}
```

Mantenha invariantes no tipo em vez de expor tudo mutável. Properties são abstrações da linguagem, não apenas fields públicos.
