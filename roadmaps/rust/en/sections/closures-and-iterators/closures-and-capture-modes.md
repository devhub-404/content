# Closures and Capture Modes

Closures can capture variables from their environment by shared borrow, mutable borrow, or move depending on how the closure body uses them. The compiler infers the least powerful capture mode that satisfies the code unless `move` forces ownership capture.

```rust
let prefix = String::from("user:");

let label = |id: u64| {
    format!("{prefix}{id}")
};

println!("{}", label(42));
```

Capture mode affects which call traits—`Fn`, `FnMut`, or `FnOnce`—the closure implements. Long-lived or cross-thread closures often use `move`, but moving a reference still moves only the reference, not magically the referenced data's ownership.
