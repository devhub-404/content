# Associated Types e GATs

Associated types deixam implementação escolher um tipo como parte do trait, reduzindo generic arguments quando existe um associado natural. GATs permitem que associated types sejam parametrizados, frequentemente por lifetimes.

```rust
trait Container {
    type Item;

    fn get(&self) -> Option<&Self::Item>;
}

trait LendingIterator {
    type Item<'a>
    where
        Self: 'a;

    fn next<'a>(&'a mut self) -> Option<Self::Item<'a>>;
}
```

Use associated types quando relação pertence à implementação, não a escolha independente do caller. GATs ajudam abstrações de borrowing, mas podem sofisticar assinaturas rapidamente.
