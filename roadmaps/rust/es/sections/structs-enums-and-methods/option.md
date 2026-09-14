# `Option<T>` en vez de Null

`Option<T>` representa `Some(T)` o `None`, haciendo que la ausencia forme parte del tipo. El código no puede usar un valor ausente sin tratar la option primero.

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

Usa combinators como `map`, `and_then`, `unwrap_or` o pattern matching según claridad. Evita `unwrap()` rutinario con datos que legítimamente pueden faltar; resérvalo para invariantes demostradas o tests.
