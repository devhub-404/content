# APIs Públicas e SemVer

API pública de crate inclui types, trait impls, generic bounds, features, panic/error behavior e até auto-trait properties que podem afetar compatibilidade. SemVer em Rust vai além de nomes de functions.

```rust
pub struct Client {
    inner: Inner,
}

impl Client {
    pub fn new() -> Self {
        // ...
        todo!()
    }
}
```

Exponha a menor API estável sustentável e esconda internals. Revise mudanças semver-sensitive: adicionar enum variant, apertar bound ou mudar `Send` pode quebrar downstream.
