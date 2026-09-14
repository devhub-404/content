# Borrowing vs Consuming en Colecciones

La iteración puede hacer borrow inmutable, mutable o consumir ownership según el `IntoIterator` seleccionado. Esto aparece en `for` e iterator chains.

```rust
let values = vec![1, 2, 3];

for value in &values {
    println!("{value}");
}

for value in values {
    println!("{value}");
}

// values moved by the second loop
```

Usa `&collection` cuando aún la necesites después, `&mut` para mutation in-place y consumo cuando los elementos deban salir por move. Esta elección evita clones innecesarios y aclara lifetimes.
