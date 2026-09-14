# Conversiones y Casts con `as`

Rust evita muchas conversiones numéricas implícitas. Prefiere `From`, `Into`, `TryFrom` y parsing cuando una conversión puede fallar o debe comunicar intención. `as` realiza un conjunto definido de casts, incluidos truncamientos numéricos.

```rust
let small: u8 = 200;
let wide: u32 = u32::from(small);

let truncated = 300_u16 as u8;
let parsed: u32 = "42".parse()?;
```

Usa `as` cuando su semántica sea exactamente la deseada y las range assumptions estén claras. En fronteras, prefiere conversiones checked para convertir out-of-range en error en vez de truncamiento silencioso.
