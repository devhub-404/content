# The `?` Operator

The `?` operator propagates an error-like residual from compatible types such as `Result` and `Option`, returning early from the current function when propagation is required. It makes the happy path linear without hiding the possibility of failure from the return type.

```rust
fn load(path: &str) -> Result<String, std::io::Error> {
    let text = std::fs::read_to_string(path)?;
    Ok(text)
}
```

`?` can also perform error conversion through `From` when the surrounding error type supports it. Use conversions deliberately so important distinctions are not erased into an unstructured error too early in lower-level libraries.
