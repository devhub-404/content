# Scope Functions

`let`, `run`, `with`, `apply` y `also` ejecutan un block con un objeto como receiver/argument y difieren en el retorno. Sirven para configuración, null-safe transforms y scopes temporales.

```kotlin
val user = User().apply {
    name = "Mina"
    active = true
}

val label = user.let { "${it.name}:${it.active}" }
```

Elige según semántica. Chains anidadas con `it`/`this` pueden ocultar qué objeto está activo; las variables nombradas son mejores cuando interactúan varios valores.
