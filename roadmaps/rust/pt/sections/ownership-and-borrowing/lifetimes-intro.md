# Relações de Lifetime

Lifetimes descrevem relações entre references para o compilador provar validade. A maioria é inferida por elision; annotations explícitas aparecem quando vários inputs/outputs possuem relação que a inferência não consegue determinar.

```rust
fn longer<'a>(a: &'a str, b: &'a str) -> &'a str {
    if a.len() >= b.len() { a } else { b }
}
```

Annotation não prolonga lifetime de valor; apenas declara relação que caller deve satisfazer. Se lifetimes ficam muito complexos, considere retornar owned value ou reorganizar storage em vez de forçar long borrowing chains.
