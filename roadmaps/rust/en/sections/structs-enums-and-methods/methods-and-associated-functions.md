# Methods and Associated Functions

An `impl` block defines methods and associated functions for a type. Methods use a receiver such as `&self`, `&mut self`, or `self`, making borrowing or ownership of the receiver explicit. Associated functions such as `new` do not receive `self`.

```rust
impl User {
    fn new(id: u64, name: impl Into<String>) -> Self {
        Self {
            id,
            name: name.into(),
        }
    }

    fn name(&self) -> &str {
        &self.name
    }
}
```

Choose the receiver from the operation: `&self` observes, `&mut self` mutates in place, and `self` consumes the value. Constructors are only conventions—Rust has no special constructor syntax—so use names such as `new`, `with_capacity`, or domain-specific factories that communicate what is built.
