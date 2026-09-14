# `Result<T, E>`

Recoverable failure is usually represented with `Result<T, E>`, which is either `Ok(T)` or `Err(E)`. This makes error possibilities part of the type and forces callers to propagate or handle them.

```rust
fn read_config(path: &str) -> Result<String, std::io::Error> {
    std::fs::read_to_string(path)
}

match read_config("config.toml") {
    Ok(text) => println!("{text}"),
    Err(err) => eprintln!("{err}"),
}
```

Use methods such as `map`, `map_err`, `and_then`, and `unwrap_or_else` when they clarify data flow. Avoid indiscriminate `unwrap()` and `expect()` in production paths where external input or I/O can legitimately fail.
