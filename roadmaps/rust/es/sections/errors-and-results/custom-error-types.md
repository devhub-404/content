# Tipos de Error Personalizados

Un enum de error personalizado conserva categorías estructuradas y contexto. Implementar `Display` y `std::error::Error` integra con error chains/tools, y `source()` puede exponer la causa subyacente.

```rust
#[derive(Debug)]
enum ConfigError {
    Io(std::io::Error),
    InvalidSyntax { line: usize },
}
```

Usa typed errors cuando los callers se beneficien de distinciones programáticas. Capas altas pueden borrar heterogeneidad para reporting, pero libraries lower-level deberían conservar estructura útil.
