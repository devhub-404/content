# Borrowing Mutável

Reference mutável `&mut T` concede acesso temporário exclusivo. Enquanto o borrow está ativo, Rust impede outros borrows sobrepostos incompatíveis.

```rust
fn append_exclamation(text: &mut String) {
    text.push('!');
}

let mut message = String::from("hello");
append_exclamation(&mut message);
```

Essa regra exclusive-or-shared é base da mutation segura. Mantenha borrows mutáveis curtos. O borrow checker normalmente fica mais simples quando a mutation é localizada em vez de manter `&mut` long-lived atravessando trabalho não relacionado.
