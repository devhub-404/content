# References and Borrowing

A reference borrows a value without taking ownership. An immutable reference `&T` allows read-only access, and the owner remains responsible for the value's lifetime. Borrowing lets functions use data without forcing moves or copies.

```rust
fn length(text: &String) -> usize {
    text.len()
}

let name = String::from("Mina");
let size = length(&name);

println!("{name} {size}");
```

The borrow checker ensures references cannot outlive the data they point to and enforces aliasing rules that make memory access safe. Prefer borrowed parameters such as `&str` or `&[T]` when a function only needs to observe data and should not take ownership.
