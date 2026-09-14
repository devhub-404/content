# `rustfmt`, Clippy y Compiler Lints

Rustfmt proporciona el formatter convencional y Clippy añade muchos lints semánticos además de los warnings del compiler. Juntos reducen debates de estilo y detectan patrones sospechosos/ineficientes.

```rust
// Typical checks:
// cargo fmt --check
// cargo clippy --all-targets --all-features -- -D warnings
// cargo test
```

No aceptes cada lint mecánicamente sin contexto, pero mantén políticas de CI consistentes. Los `allow`/`warn`/`deny` específicos deben documentar excepciones, especialmente en unsafe/API compatibility.
