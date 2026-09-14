# Operador `?`

El operador `?` propaga un error/residual de tipos compatibles como `Result`/`Option`, retornando temprano cuando corresponde. Mantiene lineal el happy path sin ocultar la posibilidad de fallo en la firma.

```rust
fn load(path: &str) -> Result<String, std::io::Error> {
    let text = std::fs::read_to_string(path)?;
    Ok(text)
}
```

`?` también puede convertir errores mediante `From` cuando esté soportado. Usa conversiones deliberadamente para no borrar distinciones útiles demasiado pronto en libraries lower-level.
