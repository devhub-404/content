# Macros Declarativas

Macros declarativas `macro_rules!` combinam syntax patterns e expandem para sintaxe Rust antes de compilação posterior. Conseguem repetition e formas que funções não conseguem, com hygiene importante de nomes.

```rust
macro_rules! vec_of_strings {
    ($($value:expr),* $(,)?) => {
        vec![$($value.to_string()),*]
    };
}

let names = vec_of_strings!("Ada", "Mina");
```

Use função/generic quando abstração tipada basta; macros servem quando sintaxe precisa variar/repetir. Mantenha patterns/expansions simples para diagnostics continuarem compreensíveis.
