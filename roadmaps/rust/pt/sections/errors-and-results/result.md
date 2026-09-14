# `Result<T, E>`

Falha recuperável normalmente usa `Result<T,E>`, que é `Ok(T)` ou `Err(E)`. Erros fazem parte do tipo e callers precisam propagar ou tratar.

```rust
fn read_config(path: &str) -> Result<String, std::io::Error> {
    std::fs::read_to_string(path)
}

match read_config("config.toml") {
    Ok(text) => println!("{text}"),
    Err(err) => eprintln!("{err}"),
}
```

Use `map`, `map_err`, `and_then` e `unwrap_or_else` quando deixam fluxo mais claro. Evite `unwrap()`/`expect()` indiscriminados em caminhos onde input externo ou I/O pode falhar legitimamente.
