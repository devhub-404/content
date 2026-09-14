# Mutable Borrowing

A mutable reference `&mut T` grants temporary exclusive access to a value. While that mutable borrow is active, Rust prevents other overlapping borrows that could observe or mutate the same data in incompatible ways.

```rust
fn append_exclamation(text: &mut String) {
    text.push('!');
}

let mut message = String::from("hello");
append_exclamation(&mut message);
```

This exclusive-or-shared rule is the core aliasing discipline behind safe mutation. Keep mutable borrows as short as practical. Often the borrow checker becomes easier to satisfy when code performs one localized mutation rather than holding a long-lived `&mut` across unrelated work.
