# Conversions and `as` Casts

Rust avoids many implicit numeric conversions. Prefer semantic conversion traits and constructors such as `From`, `Into`, `TryFrom`, and parsing APIs when a conversion can fail or should communicate intent. The `as` operator performs a defined set of casts, including potentially truncating numeric casts.

```rust
let small: u8 = 200;
let wide: u32 = u32::from(small);

let truncated = 300_u16 as u8;
let parsed: u32 = "42".parse()?;
```

Use `as` when the cast semantics are exactly what you want and the range assumptions are obvious. At trust boundaries, prefer checked conversions such as `u8::try_from(value)` so an out-of-range input becomes an error instead of silent truncation.
