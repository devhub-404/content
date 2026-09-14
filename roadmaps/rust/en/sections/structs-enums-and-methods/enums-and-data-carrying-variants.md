# Enums and Data-carrying Variants

Rust enums are algebraic sum types: every variant can carry different data while remaining one closed type. This is substantially more expressive than a C-style integer enum and works directly with exhaustive pattern matching.

```rust
enum Message {
    Quit,
    Move { x: i32, y: i32 },
    Write(String),
    Color(u8, u8, u8),
}
```

Use enums to model state machines, protocol messages, outcomes, and alternatives that are mutually exclusive. Keeping the alternatives in one type makes impossible combinations harder to construct and gives the compiler enough information to enforce exhaustive handling.
