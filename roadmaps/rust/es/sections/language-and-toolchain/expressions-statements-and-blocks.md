# Expresiones, Statements y Bloques

Rust es expression-oriented. Literals, llamadas, `if`, `match` y bloques pueden producir valores. La expresión final de un bloque sin semicolon se convierte en su resultado; añadir semicolon la vuelve un statement cuyo resultado es `()`.

```rust
fn square(x: i32) -> i32 {
    let result = {
        let y = x * x;
        y
    };

    result
}
```

Esto explica el idiom de retornar la expresión final sin `return`. Usa control flow orientado a expresiones cuando aclare el flujo de datos, sin comprimir demasiados side effects en una expresión difícil de leer.
