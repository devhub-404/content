# `String` y `str`

`String` posee un buffer UTF-8 growable y `str` es un string slice unsized usado normalmente como `&str`. Ninguno soporta indexación entera arbitraria porque un offset puede caer dentro de un code point multibyte.

```rust
let mut owned = String::from("Olá");
owned.push_str(", Rust");

let borrowed: &str = &owned;
println!("{borrowed}");
```

Decide si el dominio trabaja con bytes, Unicode scalar values (`chars()`) o grapheme clusters. Prefiere `&str` para texto borrowed y `String` cuando necesites ownership/mutation.
