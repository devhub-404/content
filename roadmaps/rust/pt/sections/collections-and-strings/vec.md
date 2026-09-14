# `Vec<T>`

`Vec<T>` é sequência contígua growable que possui elementos e backing allocation, mantendo length/capacity. Indexação `[]` panica em índice inválido; `get()` retorna `Option`.

```rust
let mut values = Vec::with_capacity(4);
values.push(10);
values.push(20);

for value in &values {
    println!("{value}");
}
```

Faça borrow como `&[T]` quando API só precisa de sequência. Pré-aloque capacity com boa estimativa, mas otimize por medição. Reallocation pode invalidar raw pointers/unsafe references para o buffer.
