# Funciones y Tipos de Retorno

Los tipos de parámetros son explícitos y `-> T` declara el retorno. Las funciones sin retorno explícito retornan `()`. La expresión final sin semicolon es un idiom común para el valor retornado.

```rust
fn add(a: i32, b: i32) -> i32 {
    a + b
}

fn log(message: &str) {
    println!("{message}");
}
```

Haz visible el ownership en la firma: `String` puede mover/poseer datos, `&str` hace borrow y `&mut T` un borrow mutable. En Rust, las firmas describen también relaciones importantes de lifetime y ownership.
