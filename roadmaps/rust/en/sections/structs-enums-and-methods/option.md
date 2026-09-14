# `Option<T>` Instead of Null

`Option<T>` represents either `Some(T)` or `None`. It makes absence part of the type, so code cannot accidentally dereference or use a missing value without handling the option first.

```rust
fn find_user(id: u64) -> Option<User> {
    users()
        .into_iter()
        .find(|user| user.id == id)
}

if let Some(user) = find_user(42) {
    println!("{}", user.name);
}
```

Use combinators such as `map`, `and_then`, `unwrap_or`, or pattern matching when they make the flow clearer. Avoid routine `unwrap()` on data that can legitimately be absent; reserve it for states that are provably impossible or tests where panic is the intended failure mode.
