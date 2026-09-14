# Dangling References y Borrow Checker

Las reglas de references impiden retornar/almacenar una reference a datos que se destruirán demasiado pronto, eliminando clases enteras de use-after-free en safe Rust.

```rust
fn valid() -> String {
    let text = String::from("owned");
    text
}

// Returning &text here would be rejected.
```

Cuando el compiler rechaza un borrow, identifica el ownership/lifetime real en vez de clonar todo. A menudo mover ownership, acortar el borrow, separar estructuras o retornar un owned value expresa mejor el diseño.
