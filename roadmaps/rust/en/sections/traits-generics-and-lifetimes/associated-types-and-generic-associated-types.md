# Associated Types and GATs

Associated types let a trait choose a type as part of an implementation, reducing repeated generic arguments when one implementation has one natural associated type. Generic associated types (GATs) allow those associated types to themselves be parameterized, commonly by lifetimes.

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

Use associated types when the relationship belongs to the implementation rather than being independently chosen by every caller. GATs are powerful for lending/borrowing abstractions but can make signatures sophisticated quickly, so keep the public contract as simple as the domain permits.
