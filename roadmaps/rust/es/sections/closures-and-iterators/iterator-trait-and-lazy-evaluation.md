# Trait `Iterator` y Evaluación Lazy

Un iterator produce una secuencia mediante llamadas repetidas a `next()` y es lazy: los adapters construyen un pipeline pero no trabajan hasta que una operación consumidora lo ejecuta.

```rust
let values = vec![1, 2, 3, 4];

let doubled: Vec<_> = values
    .iter()
    .map(|value| value * 2)
    .collect();
```

Las chains suelen compilar a loops eficientes sin colecciones intermedias. Usa adapters cuando expresen intención; prefiere `for` cuando dominen el control flow o los side effects.
