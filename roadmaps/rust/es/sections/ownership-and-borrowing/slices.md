# Slices

Un slice es una view borrowed sobre una secuencia contigua. `&[T]` ve elementos y `&str` es un string slice UTF-8. El slice lleva pointer y length, evitando pointer-plus-count manual.

```rust
fn first_word(text: &str) -> &str {
    text.split_whitespace()
        .next()
        .unwrap_or("")
}

let values = [10, 20, 30, 40];
let middle: &[i32] = &values[1..3];
```

Los slices no poseen los datos y dependen del lifetime de la fuente. Prefiere `&[T]` frente a `&Vec<T>` y `&str` frente a `&String` cuando la función solo necesita acceso genérico.
