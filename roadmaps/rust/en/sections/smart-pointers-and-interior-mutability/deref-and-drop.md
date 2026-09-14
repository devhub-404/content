# `Deref` and `Drop`

`Drop` runs deterministic cleanup when a value leaves scope, making RAII-style resource management fundamental in Rust. `Deref` and `DerefMut` let smart-pointer-like types expose access to a target and participate in deref coercions.

```rust
struct Guard {
    name: String,
}

impl Drop for Guard {
    fn drop(&mut self) {
        println!("releasing {}", self.name);
    }
}
```

Implement `Deref` when your type truly behaves like a smart pointer, not simply to forward arbitrary methods. `Drop` should release resources reliably and must not depend on being called at process termination in every situation. Avoid cycles that prevent owners from being dropped.
