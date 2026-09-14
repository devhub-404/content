# Dangling References and the Borrow Checker

Rust's safe reference rules prevent returning or storing a reference to data that will be destroyed before the reference is used. This makes entire classes of use-after-free and dangling-pointer bugs impossible in safe Rust.

```rust
fn valid() -> String {
    let text = String::from("owned");
    text
}

// Returning &text here would be rejected.
```

When the compiler rejects a borrow, identify the true ownership and lifetime relationship instead of immediately cloning everything. Sometimes moving ownership, shortening a borrow, splitting data structures, or returning an owned result expresses the design more accurately.
