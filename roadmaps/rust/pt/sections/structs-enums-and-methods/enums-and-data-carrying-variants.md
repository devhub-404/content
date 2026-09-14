# Enums e Variants com Dados

Enums Rust são algebraic sum types: cada variant pode carregar dados diferentes dentro de um tipo fechado. São muito mais expressivos que enum inteiro C-like e combinam diretamente com pattern matching exaustivo.

```rust
enum Message {
    Quit,
    Move { x: i32, y: i32 },
    Write(String),
    Color(u8, u8, u8),
}
```

Use enums para state machines, protocol messages, outcomes e alternativas mutuamente exclusivas. Um tipo fechado reduz combinações impossíveis e permite tratamento exaustivo pelo compiler.
