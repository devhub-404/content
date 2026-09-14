# `IntoIterator` and Iteration Ownership

`IntoIterator` converts a value into something iterable and is what `for` uses under the hood. Collections often implement it for owned values, shared references, and mutable references, producing different item types and ownership behavior.

```rust
let values = vec![1, 2, 3];

for item in &values {
    println!("{item}");
}

for item in values {
    println!("{item}");
}
```

Choose the form intentionally: consuming iteration moves elements, shared-reference iteration borrows immutably, and mutable-reference iteration allows in-place changes. This is one of the places where Rust makes data ownership visible in ordinary collection syntax.
