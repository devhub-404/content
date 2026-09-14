# Lifetime Parameters in Types and Traits

Types that store references usually carry lifetime parameters describing how long those references may remain valid. Trait bounds can also involve lifetimes, including higher-ranked bounds for behavior that must work for any suitable borrow lifetime.

```rust
struct Excerpt<'a> {
    text: &'a str,
}

impl<'a> Excerpt<'a> {
    fn text(&self) -> &'a str {
        self.text
    }
}
```

Do not add lifetime parameters mechanically. They encode real borrowing relationships and can make a type harder to move through an application. If an object conceptually owns its data, storing `String`, `Arc<T>`, or another owning representation may be simpler than threading borrows through many layers.
