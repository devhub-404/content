# Traits e Implementaciones

Un trait define comportamiento compartido que los tipos pueden implementar. Los traits sustentan constraints genéricos, operators, formatting, conversions, iteration, concurrency markers y extensibilidad de la std.

```rust
trait Summary {
    fn summary(&self) -> String;
}

struct Article {
    title: String,
}

impl Summary for Article {
    fn summary(&self) -> String {
        self.title.clone()
    }
}
```

Implementa traits cuando expresen un contrato significativo, no solo methods con nombres parecidos. Las coherence/orphan rules limitan combinaciones implementables y mantienen la resolución predecible.
