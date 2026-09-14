# Crates, Packages e Targets

Package é um projeto Cargo descrito por `Cargo.toml`. Crate é unidade de compilação Rust: binária ou library. Um package pode conter vários binary targets, examples, tests, benches e uma library principal.

```rust
// Cargo.toml
[package]
name = "example"
version = "0.1.0"
edition = "2024"

[dependencies]
serde = "1"
```

A distinção importa porque visibility/dependencies operam em crate level, enquanto versioning/metadata operam em package level. Organize targets em torno de produtos e libraries reais, não apenas por conveniência de pasta.
