# `Vec<T>`

`Vec<T>` is Rust's growable contiguous sequence. It owns its elements and backing allocation, tracks length and capacity, and grows when needed. Indexing with `[]` panics on an invalid index, while `get()` returns an `Option`.

```rust
let mut values = Vec::with_capacity(4);
values.push(10);
values.push(20);

for value in &values {
    println!("{value}");
}
```

Borrow the vector as a slice `&[T]` when an API only needs sequence access. Preallocate with `with_capacity` when a useful estimate is known, but optimize capacity based on measurements rather than habit. Mutations that reallocate can invalidate raw pointers or unsafe references into the buffer.
