# Funções e Tipos de Retorno

Tipos de parâmetros são explícitos e `-> T` declara retorno. Funções sem retorno explícito retornam `()`. A expressão final sem semicolon é idiom comum para o valor retornado.

```rust
fn add(a: i32, b: i32) -> i32 {
    a + b
}

fn log(message: &str) {
    println!("{message}");
}
```

Deixe ownership visível na assinatura: `String` pode mover/possuir dados, `&str` faz borrow e `&mut T` borrow mutável. Em Rust, assinaturas descrevem também relações importantes de lifetime e ownership.
