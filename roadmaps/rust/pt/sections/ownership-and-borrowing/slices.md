# Slices

Slice é view borrowed sobre sequência contígua. `&[T]` vê elementos e `&str` é string slice UTF-8. Slice carrega pointer e length, evitando pointer-plus-count manual.

```rust
fn first_word(text: &str) -> &str {
    text.split_whitespace()
        .next()
        .unwrap_or("")
}

let values = [10, 20, 30, 40];
let middle: &[i32] = &values[1..3];
```

Slices não possuem os dados e dependem do lifetime da origem. Prefira `&[T]` a `&Vec<T>` e `&str` a `&String` quando a função só precisa de acesso genérico.
