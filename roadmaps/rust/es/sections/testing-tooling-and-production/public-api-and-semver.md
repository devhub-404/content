# APIs Públicas y SemVer

La API pública de un crate incluye types, trait impls, generic bounds, features, panic/error behavior e incluso auto-trait properties que pueden afectar compatibilidad. SemVer en Rust va más allá de los nombres de funciones.

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

Expón la menor API estable que puedas mantener y oculta internals. Revisa cambios semver-sensitive: añadir una enum variant, endurecer un bound o cambiar `Send` puede romper downstream.
