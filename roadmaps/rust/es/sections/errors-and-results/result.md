# `Result<T, E>`

El fallo recuperable suele representarse con `Result<T,E>`, que es `Ok(T)` o `Err(E)`. Los errores forman parte del tipo y los callers deben propagarlos o tratarlos.

```rust
fn read_config(path: &str) -> Result<String, std::io::Error> {
    std::fs::read_to_string(path)
}

match read_config("config.toml") {
    Ok(text) => println!("{text}"),
    Err(err) => eprintln!("{err}"),
}
```

Usa `map`, `map_err`, `and_then` y `unwrap_or_else` cuando aclaren el flujo. Evita `unwrap()`/`expect()` indiscriminados en rutas donde input externo o I/O puedan fallar legítimamente.
