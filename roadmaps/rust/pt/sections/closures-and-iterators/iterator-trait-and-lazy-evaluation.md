# Trait `Iterator` e Avaliação Lazy

Iterator produz sequência por `next()` repetido e é lazy: adapters constroem pipeline mas só executam quando consumer dirige o iterator.

```rust
let values = vec![1, 2, 3, 4];

let doubled: Vec<_> = values
    .iter()
    .map(|value| value * 2)
    .collect();
```

Chains costumam compilar para loops eficientes sem collections intermediárias. Use adapters quando expressam intenção; prefira `for` quando control flow/side effects dominam.
