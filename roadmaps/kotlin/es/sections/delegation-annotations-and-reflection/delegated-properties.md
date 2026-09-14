# Delegated Properties

Property delegation permite que otro objeto proporcione getter/setter. Los standard delegates incluyen `lazy`, observable/vetoable, map-backed y delegates de frameworks.

```kotlin
val config by lazy {
    loadConfiguration()
}

var name: String by Delegates.observable("") { _, old, new ->
    println("$old -> $new")
}
```

Delegation centraliza comportamiento repetido, pero también esconde trabajo tras property syntax. Evita side effects costosos o sorprendentes sin un contrato claro. Usa el recurso cuando exprese un contrato real; evitar abstracciones innecesarias mantiene la API más fácil de leer.
