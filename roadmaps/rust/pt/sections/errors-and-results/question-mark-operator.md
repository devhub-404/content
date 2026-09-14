# Operador `?`

Operador `?` propaga erro/residual de tipos compatíveis como `Result`/`Option`, retornando cedo quando necessário. Mantém happy path linear sem esconder possibilidade de falha da assinatura.

```rust
fn load(path: &str) -> Result<String, std::io::Error> {
    let text = std::fs::read_to_string(path)?;
    Ok(text)
}
```

`?` também pode converter erro via `From` quando suportado. Use conversões conscientemente para não apagar distinções úteis cedo demais em libraries lower-level.
