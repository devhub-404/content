# `if let`, `while let` y `let...else`

Los patterns refutables pueden usarse de forma compacta cuando solo importa una forma. `if let` maneja un caso, `while let` repite mientras el pattern coincida y `let...else` exige match o una salida divergente.

```rust
let Some(user) = find_user(id) else {
    return Err(Error::NotFound);
};

if let Some(email) = user.email.as_deref() {
    println!("{email}");
}
```

Usa estas formas cuando dejan el happy path más claro que un `match`. Vuelve a `match` cuando importen varias alternativas o la exhaustividad sea documentación útil.
