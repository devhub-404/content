# `rustc`, Cargo y Rustup

`rustc` es el compilador, Cargo es package manager/build tool y Rustup gestiona toolchains y components. La mayor parte del desarrollo usa Cargo en vez de invocar `rustc` directamente.

```rust
// Typical workflow:
// rustup update stable
// cargo new app
// cargo check
// cargo test
// cargo run
// cargo build --release
```

Usa `cargo check` para feedback rápido de tipos/lifetimes, `cargo test` para tests, `cargo run` durante desarrollo y release builds para performance realista. Rustup permite fijar o cambiar toolchains cuando la reproducibilidad o experimentos nightly lo exijan.
