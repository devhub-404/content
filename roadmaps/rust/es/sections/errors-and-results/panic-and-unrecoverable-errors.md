# `panic!` y Errores Irrecuperables

`panic!` representa un fallo irrecuperable en la ruta actual. El panic puede hacer unwind o abortar según configuración, y el unwinding ejecuta destructors de valores vivos.

```rust
fn positive(value: i32) -> i32 {
    assert!(value > 0, "value must be positive");
    value
}
```

Usa panic para invariantes internas violadas, estados imposibles o tests, no para input inválido, archivos ausentes o fallos de red recuperables. Las APIs no deberían sorprender a callers con panics rutinarios cuando `Result` serviría.
