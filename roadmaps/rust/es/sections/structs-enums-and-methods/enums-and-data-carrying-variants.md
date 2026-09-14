# Enums y Variants con Datos

Los enums de Rust son algebraic sum types: cada variant puede transportar datos distintos dentro de un tipo cerrado. Son mucho más expresivos que un enum entero C-like y se integran directamente con pattern matching exhaustivo.

```rust
enum Message {
    Quit,
    Move { x: i32, y: i32 },
    Write(String),
    Color(u8, u8, u8),
}
```

Usa enums para state machines, protocol messages, outcomes y alternativas mutuamente exclusivas. Un tipo cerrado reduce combinaciones imposibles y permite tratamiento exhaustivo por el compiler.
