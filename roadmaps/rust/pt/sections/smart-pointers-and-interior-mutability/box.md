# `Box<T>`

`Box<T>` possui valor alocado no heap e representação pointer-sized. É comum em tipos recursivos, valores que devem mover por pointer e trait objects owning.

```rust
enum List {
    Cons(i32, Box<List>),
    Nil,
}
```

Não use `Box` apenas porque objeto parece grande sem medir. Use quando indirection ou heap ownership estável faz parte do requisito estrutural.
