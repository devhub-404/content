# `rustfmt`, Clippy e Compiler Lints

Rustfmt fornece formatter convencional e Clippy adiciona muitos lints semânticos além dos warnings do compiler. Juntos reduzem debates de estilo e encontram padrões suspeitos/ineficientes.

```rust
// Typical checks:
// cargo fmt --check
// cargo clippy --all-targets --all-features -- -D warnings
// cargo test
```

Não aceite lint mecanicamente sem contexto, mas mantenha políticas de CI consistentes. `allow`/`warn`/`deny` específicos devem documentar exceções, principalmente em unsafe/API compatibility.
