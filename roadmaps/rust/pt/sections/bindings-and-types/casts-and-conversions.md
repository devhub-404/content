# Conversões e Casts com `as`

Rust evita muitas conversões numéricas implícitas. Prefira `From`, `Into`, `TryFrom` e parsing quando conversão pode falhar ou precisa comunicar intenção. `as` executa conjunto definido de casts, inclusive truncamentos numéricos.

```rust
let small: u8 = 200;
let wide: u32 = u32::from(small);

let truncated = 300_u16 as u8;
let parsed: u32 = "42".parse()?;
```

Use `as` quando sua semântica é exatamente a desejada e range assumptions são claras. Em fronteiras, prefira conversões checked para transformar out-of-range em erro em vez de truncamento silencioso.
