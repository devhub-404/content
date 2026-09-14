# `Cell` and `RefCell`

Interior-mutability types allow mutation through a shared reference by moving some borrowing checks from compile time to a controlled runtime mechanism. `Cell<T>` supports value replacement/copy-like operations, while `RefCell<T>` dynamically tracks shared and mutable borrows.

```rust
use std::cell::RefCell;

let value = RefCell::new(vec![1, 2, 3]);

value.borrow_mut().push(4);

println!("{:?}", value.borrow());
```

A violated `RefCell` borrow rule panics at runtime, so interior mutability is not a way to ignore ownership design. It is useful for patterns the static borrow checker cannot express conveniently, especially behind single-threaded abstractions. For shared concurrent mutation, use synchronization types instead.
