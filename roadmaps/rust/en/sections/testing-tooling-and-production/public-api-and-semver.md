# Public APIs and SemVer

A published crate's public types, trait implementations, generic bounds, feature flags, panic/error behavior, and sometimes auto-trait properties can all affect compatibility. Cargo follows semantic-version conventions, but Rust's rich type system means compatibility is more than function names.

```rust
pub struct Client {
    inner: Inner,
}

impl Client {
    pub fn new() -> Self {
        // ...
        todo!()
    }
}
```

Expose the smallest stable API you can support, hide implementation details behind private fields/modules, and review semver-sensitive changes before release. Adding a public enum variant, tightening a generic bound, or changing whether a type is `Send` can affect downstream code even if runtime behavior seems similar.
