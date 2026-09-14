# Delegated Properties

Property delegation permite que outro objeto forneça getter/setter. Standard delegates incluem `lazy`, observable/vetoable, map-backed e delegates de frameworks.

```kotlin
val config by lazy {
    loadConfiguration()
}

var name: String by Delegates.observable("") { _, old, new ->
    println("$old -> $new")
}
```

Delegation centraliza comportamento repetido, mas também esconde trabalho atrás de property syntax. Evite side effects caros ou surpreendentes sem contrato claro. Use o recurso quando ele expressa um contrato real; evitar abstrações desnecessárias mantém a API mais simples de ler.
