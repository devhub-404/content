# `impl Trait` e Trait Objects

`impl Trait` expressa tipo concreto opaco que satisfaz trait, comum em argumentos/retornos. Trait objects como `&dyn Trait`/`Box<dyn Trait>` usam dynamic dispatch via vtable para implementações heterogêneas.

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

Static dispatch e dynamic dispatch resolvem problemas distintos. Prefira generics/`impl Trait` quando o tipo concreto pode permanecer conhecido em compile time; use trait object para heterogeneidade runtime real.
