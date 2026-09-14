# Variância: `in`, `out` e Star Projections

Declaration-site variance permite dizer que tipo só produz (`out`) ou consome (`in`) T, habilitando subtype relationships seguros. Projections tratam casos onde variance não pode ficar na declaration.

```kotlin
interface Producer<out T> {
    fun produce(): T
}

interface Consumer<in T> {
    fun consume(value: T)
}
```

Variance deve refletir a API real. Tipo que consome e produz T normalmente é invariant. Não adicione apenas para fazer assignment compilar.
