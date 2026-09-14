# `let`, `mut`, and Shadowing

Bindings are immutable by default. Add `mut` when a binding's value will be changed through that binding. Shadowing with a new `let` creates a new binding and can change the type, unlike mutation, which keeps the same binding and type.

```rust
let count = 10;
let mut total = 0;

total += count;

let count = count.to_string();
```

Default immutability makes state changes visible and helps the borrow checker reason about aliasing. Use mutation when it is part of the algorithm; use shadowing for staged transformations where the old binding is conceptually replaced by a new value.
