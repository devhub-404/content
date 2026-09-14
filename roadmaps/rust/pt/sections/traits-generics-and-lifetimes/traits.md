# Traits e Implementações

Trait define comportamento compartilhado que tipos podem implementar. Traits sustentam constraints genéricos, operators, formatting, conversions, iteration, concurrency markers e extensibilidade da std.

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

Implemente traits quando expressam contrato significativo, não apenas methods com nomes parecidos. Coherence/orphan rules limitam combinações implementáveis e mantêm resolução previsível.
