# `rustc`, Cargo e Rustup

`rustc` é o compilador, Cargo é package manager/build tool e Rustup gerencia toolchains e components. A maior parte do desenvolvimento usa Cargo em vez de invocar `rustc` diretamente.

```rust
// Typical workflow:
// rustup update stable
// cargo new app
// cargo check
// cargo test
// cargo run
// cargo build --release
```

Use `cargo check` para feedback rápido de tipos/lifetimes, `cargo test` para testes, `cargo run` em desenvolvimento e release builds para performance realista. Rustup permite fixar ou trocar toolchains quando reprodução ou experimentos nightly exigirem.
