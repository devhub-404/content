# Associated Types y GATs

Los associated types permiten que una implementación elija un tipo como parte del trait, reduciendo generic arguments cuando existe un asociado natural. Los GATs permiten que esos associated types estén parametrizados, frecuentemente por lifetimes.

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

Usa associated types cuando la relación pertenezca a la implementación, no a una elección independiente del caller. Los GATs ayudan a abstracciones de borrowing, pero pueden sofisticar las firmas rápidamente.
