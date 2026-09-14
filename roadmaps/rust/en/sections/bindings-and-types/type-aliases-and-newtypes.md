# Type Aliases and Newtypes

A type alias creates another name for an existing type and does not create a new type identity. The newtype pattern wraps one value in a tuple struct, producing a distinct type that can enforce domain separation and define its own traits and methods.

```rust
type UserIdText = String;

struct UserId(String);

fn load_user(id: UserId) {
    // ...
}
```

Use aliases to improve readability or shorten complex types without changing compatibility. Use newtypes when two values share a representation but should not be mixed, or when you need to implement traits around a foreign/external type under Rust's coherence rules.
