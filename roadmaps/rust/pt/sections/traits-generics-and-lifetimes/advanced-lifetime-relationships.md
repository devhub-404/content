# Parâmetros de Lifetime em Tipos e Traits

Tipos que armazenam references normalmente carregam lifetime parameters descrevendo validade. Trait bounds também podem envolver lifetimes, inclusive higher-ranked bounds para comportamento válido em qualquer borrow apropriado.

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

Não adicione lifetime parameters mecanicamente. Eles codificam relações reais de borrow e podem dificultar uso do tipo. Se objeto conceitualmente possui os dados, representação owning pode ser mais simples que borrows atravessando muitas layers.
