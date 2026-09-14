# Macros Declarativas

Las macros declarativas `macro_rules!` combinan syntax patterns y expanden a sintaxis Rust antes de etapas posteriores de compilación. Pueden expresar repetition y formas que las funciones no pueden, con hygiene importante de nombres.

```rust
macro_rules! vec_of_strings {
    ($($value:expr),* $(,)?) => {
        vec![$($value.to_string()),*]
    };
}

let names = vec_of_strings!("Ada", "Mina");
```

Usa función/generic cuando una abstracción tipada sea suficiente; las macros sirven cuando la sintaxis debe variar o repetirse. Mantén patterns/expansions simples para que los diagnostics sigan siendo comprensibles.
