# `Vec<T>`

`Vec<T>` es una secuencia contigua growable que posee los elementos y la backing allocation, manteniendo length/capacity. La indexación `[]` hace panic si el índice es inválido; `get()` retorna `Option`.

```rust
let mut values = Vec::with_capacity(4);
values.push(10);
values.push(20);

for value in &values {
    println!("{value}");
}
```

Haz borrow como `&[T]` cuando la API solo necesite secuencia. Preasigna capacity con una buena estimación, pero optimiza por medición. Una reallocation puede invalidar raw pointers/unsafe references al buffer.
