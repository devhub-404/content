# `if let`, `while let` e `let...else`

Patterns refutáveis podem ser usados de forma compacta quando apenas uma forma importa. `if let` trata um caso, `while let` repete enquanto pattern combina e `let...else` exige match ou saída divergente.

```rust
let Some(user) = find_user(id) else {
    return Err(Error::NotFound);
};

if let Some(email) = user.email.as_deref() {
    println!("{email}");
}
```

Use essas formas quando deixam happy path mais claro que `match`. Volte a `match` quando várias alternativas importam ou exaustividade é documentação útil.
