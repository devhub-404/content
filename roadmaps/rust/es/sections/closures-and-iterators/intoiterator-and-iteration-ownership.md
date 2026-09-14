# `IntoIterator` y Ownership de Iteración

`IntoIterator` convierte un valor en algo iterable y es lo que usa `for`. Las collections suelen implementarlo para valor owned, shared reference y mutable reference, produciendo item types/ownership distintos.

```rust
let values = vec![1, 2, 3];

for item in &values {
    println!("{item}");
}

for item in values {
    println!("{item}");
}
```

Elige intencionalmente: la iteración consuming mueve elementos, shared los toma prestados y mutable permite mutation in-place. El ownership queda visible incluso en sintaxis ordinaria de collections.
