# Tipos de Erro Customizados

Enum de erro customizado preserva categorias estruturadas e contexto. Implementar `Display` e `std::error::Error` integra com error chains/tools, e `source()` pode expor causa subjacente.

```rust
#[derive(Debug)]
enum ConfigError {
    Io(std::io::Error),
    InvalidSyntax { line: usize },
}
```

Use typed errors quando callers se beneficiam de distinções programáticas. Camadas altas podem erasure erros para reporting, mas libraries lower-level devem preservar estrutura útil.
