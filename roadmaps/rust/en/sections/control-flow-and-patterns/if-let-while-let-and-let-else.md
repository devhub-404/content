# `if let`, `while let`, and `let...else`

Refutable patterns can be used more compactly when only one shape matters. `if let` handles one matching case, `while let` repeats while a pattern keeps matching, and `let...else` requires a pattern or diverges through `return`, `break`, `continue`, or panic-like control.

```rust
let Some(user) = find_user(id) else {
    return Err(Error::NotFound);
};

if let Some(email) = user.email.as_deref() {
    println!("{email}");
}
```

Use these forms when they make the happy path clearer than a full `match`. Switch back to `match` when multiple alternatives are meaningful or exhaustiveness itself is valuable documentation.
