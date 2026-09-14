# Borrowing Mutable

Una reference mutable `&mut T` concede acceso temporal exclusivo. Mientras el borrow está activo, Rust impide otros borrows solapados incompatibles.

```rust
fn append_exclamation(text: &mut String) {
    text.push('!');
}

let mut message = String::from("hello");
append_exclamation(&mut message);
```

Esta regla exclusive-or-shared es la base de la mutation segura. Mantén los borrows mutables cortos. El borrow checker suele ser más simple si localizas la mutation en vez de mantener un `&mut` long-lived atravesando trabajo no relacionado.
