# Scope Functions

`let`, `run`, `with`, `apply` e `also` executam block com objeto como receiver/argument e diferem no retorno. Servem a configuração, null-safe transforms e scopes temporários.

```kotlin
val user = User().apply {
    name = "Mina"
    active = true
}

val label = user.let { "${it.name}:${it.active}" }
```

Escolha pela semântica. Chains aninhadas com `it`/`this` podem esconder qual objeto está ativo; variáveis nomeadas são melhores quando vários valores interagem.
