# Borrowing vs Consuming Collections

Collection iteration can borrow immutably, borrow mutably, or consume ownership depending on the `IntoIterator` implementation selected by the expression. This distinction is visible in `for` loops and iterator chains.

```rust
let values = vec![1, 2, 3];

for value in &values {
    println!("{value}");
}

for value in values {
    println!("{value}");
}

// values moved by the second loop
```

Use `&collection` when the collection remains needed afterward, `&mut collection` for in-place mutation, and ownership-consuming iteration when elements should move out. Understanding this choice prevents unnecessary cloning and clarifies lifetime relationships.
