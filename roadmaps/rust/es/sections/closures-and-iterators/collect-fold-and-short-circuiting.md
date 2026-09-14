# `collect`, `fold` y Consumers con Short-circuit

Los consumers transforman un iterator en un resultado final. `collect` construye collections, `sum`/`product` reducen números, `fold` usa un accumulator y `find`/`any`/`all` pueden detenerse temprano.

```rust
let sum: i32 = values.iter().copied().sum();

let parsed: Result<Vec<u32>, _> =
    inputs.iter()
        .map(|text| text.parse::<u32>())
        .collect();
```

El target type influye en `collect`, incluso transformando un iterator de `Result` en `Result<Vec<_>,E>` con short-circuit en el primer error. Prefiere el consumer específico frente a usar `fold` para todo.
