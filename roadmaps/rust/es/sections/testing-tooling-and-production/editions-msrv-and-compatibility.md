# Editions, MSRV y Compatibilidad

Una edition selecciona un conjunto coherente de defaults/migrations y crates de editions distintas interoperan. Un crate también puede declarar MSRV con `rust-version`, distinto de la edition.

```rust
[package]
name = "example"
version = "0.1.0"
edition = "2024"
rust-version = "1.90"
```

Usar una API nueva de std, Cargo o lenguaje puede elevar el MSRV real sin cambiar edition. Las libraries que prometen MSRV deberían probarlo en CI; las aplicaciones pueden fijar toolchain/lockfile según sus necesidades de reproducibilidad.
