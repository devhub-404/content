# `impl Trait` y Trait Objects

`impl Trait` expresa un tipo concreto opaco que satisface un trait, común en argumentos/retornos. Los trait objects como `&dyn Trait`/`Box<dyn Trait>` usan dynamic dispatch mediante vtable para implementaciones heterogéneas.

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

Static dispatch y dynamic dispatch resuelven problemas distintos. Prefiere generics/`impl Trait` cuando el tipo concreto puede permanecer conocido en compile time; usa trait objects para heterogeneidad runtime real.
