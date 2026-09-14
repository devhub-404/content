# Editions, MSRV e Compatibilidade

Edition seleciona conjunto coerente de defaults/migrations e crates de editions diferentes interoperam. Crate também pode declarar MSRV com `rust-version`, distinto da edition.

```rust
[package]
name = "example"
version = "0.1.0"
edition = "2024"
rust-version = "1.90"
```

Usar API nova de std, Cargo ou linguagem pode elevar MSRV real sem mudar edition. Libraries que prometem MSRV devem testá-lo em CI; aplicações podem pin toolchain/lockfile conforme necessidade de reprodução.
