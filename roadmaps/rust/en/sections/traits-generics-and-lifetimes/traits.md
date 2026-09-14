# Traits and Implementations

A trait defines shared behavior that types can implement. Traits power generic constraints, operator behavior, formatting, conversions, iteration, concurrency markers, and much of the standard library's extensibility.

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

Implement traits when they express a meaningful contract, not merely because two types happen to have similarly named methods. Rust's coherence/orphan rules limit which trait/type combinations a crate may implement, keeping global trait resolution predictable.
