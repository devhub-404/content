# `IntoIterator` e Ownership da Iteração

`IntoIterator` converte valor em algo iterável e é usado pelo `for`. Collections frequentemente implementam para valor owned, shared reference e mutable reference, produzindo item types/ownership diferentes.

```rust
let values = vec![1, 2, 3];

for item in &values {
    println!("{item}");
}

for item in values {
    println!("{item}");
}
```

Escolha intencionalmente: iteração consuming move elementos, shared borrows e mutable permite mutation in-place. Ownership fica visível até na sintaxe comum de collections.
