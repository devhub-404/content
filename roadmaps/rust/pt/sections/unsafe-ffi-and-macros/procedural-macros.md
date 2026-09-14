# Procedural Macros e Derives

Procedural macros rodam em compile time e transformam token streams. Sustentam custom derives, attribute-like e function-like macros usadas em serialization, web, databases e async.

```rust
#[derive(Debug, Clone)]
struct User {
    id: u64,
    name: String,
}
```

Proc macro é crate separado com muito poder e pode esconder comportamento gerado. Prefira APIs transparentes/docs, inspecione expansions ao depurar e evite macro magic quando trait/função comum for mais claro.
