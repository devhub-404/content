# `collect`, `fold` e Consumers com Short-circuit

Consumers transformam iterator em resultado final. `collect` constrói collections, `sum`/`product` reduzem números, `fold` usa accumulator e `find`/`any`/`all` podem parar cedo.

```rust
let sum: i32 = values.iter().copied().sum();

let parsed: Result<Vec<u32>, _> =
    inputs.iter()
        .map(|text| text.parse::<u32>())
        .collect();
```

Target type influencia `collect`, inclusive transformando iterator de `Result` em `Result<Vec<_>,E>` com short-circuit no primeiro erro. Prefira consumer específico a usar `fold` para tudo.
