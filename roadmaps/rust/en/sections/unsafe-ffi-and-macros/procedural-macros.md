# Procedural Macros and Derives

Procedural macros run at compile time and transform Rust token streams. They power custom derives, attribute-like macros, and function-like macros used heavily by serialization, web, database, and async ecosystems.

```rust
#[derive(Debug, Clone)]
struct User {
    id: u64,
    name: String,
}
```

A proc macro is a separate crate with significant power and can make generated behavior less visible to readers. Prefer transparent APIs and generated documentation, inspect expansions when debugging, and avoid macro-driven magic when a normal trait/function abstraction would be easier to understand.
