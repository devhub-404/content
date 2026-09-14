# `Option<T>` em vez de Null

`Option<T>` representa `Some(T)` ou `None`, tornando ausência parte do tipo. Código não consegue usar valor ausente sem tratar a option primeiro.

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

Use combinators como `map`, `and_then`, `unwrap_or` ou pattern matching conforme clareza. Evite `unwrap()` rotineiro em dados que legitimamente podem faltar; reserve para invariantes provadas ou testes.
