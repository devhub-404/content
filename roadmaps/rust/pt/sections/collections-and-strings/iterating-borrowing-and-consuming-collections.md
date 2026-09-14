# Borrowing vs Consuming em Coleções

Iteração pode fazer borrow imutável, mutável ou consumir ownership conforme `IntoIterator` selecionado. Isso aparece em `for` e iterator chains.

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

Use `&collection` quando ainda precisa dela depois, `&mut` para mutation in-place e consumo quando elementos devem sair por move. Essa escolha evita clones desnecessários e clarifica lifetimes.
