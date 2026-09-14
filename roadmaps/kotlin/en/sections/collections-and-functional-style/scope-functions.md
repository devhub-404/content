# Scope Functions

`let`, `run`, `with`, `apply`, and `also` execute a block with an object as receiver or argument and differ in what they return. They are useful for configuration, null-safe transformations, side observations, and limiting a temporary name to a small scope.

```kotlin
val user = User().apply {
    name = "Mina"
    active = true
}

val label = user.let { "${it.name}:${it.active}" }
```

Choose a scope function by semantics rather than novelty. Deeply nested `let`/`apply` chains with implicit `it` and `this` can hide which object is active; ordinary named variables are clearer when multiple values interact.
