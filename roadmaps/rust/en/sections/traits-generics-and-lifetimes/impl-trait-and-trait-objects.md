# `impl Trait` and Trait Objects

`impl Trait` expresses an opaque concrete type that satisfies a trait, commonly in function arguments or returns. Trait objects such as `&dyn Trait` or `Box<dyn Trait>` use dynamic dispatch through a runtime vtable when heterogeneous implementations need one interface.

```rust
fn make_iter(values: &[i32])
    -> impl Iterator<Item = &i32>
{
    values.iter()
}

fn render(item: &dyn Summary) {
    println!("{}", item.summary());
}
```

Static generic dispatch and dynamic trait-object dispatch solve different problems. Prefer generics or `impl Trait` when the concrete type can remain compile-time known; use trait objects when runtime heterogeneity or plugin-like abstraction is genuinely required.
