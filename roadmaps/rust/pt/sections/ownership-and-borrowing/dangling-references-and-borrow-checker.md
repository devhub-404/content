# Dangling References e Borrow Checker

As regras de references impedem retornar/armazenar reference para dados que serão destruídos cedo demais, eliminando classes inteiras de use-after-free em safe Rust.

```rust
fn valid() -> String {
    let text = String::from("owned");
    text
}

// Returning &text here would be rejected.
```

Quando o compiler rejeita borrow, identifique ownership/lifetime real em vez de clonar tudo. Muitas vezes mover ownership, encurtar borrow, separar estruturas ou retornar owned value expressa melhor o design.
