# Pattern Matching con `match`

`match` compara un valor con patterns y exige tratamiento exhaustivo. Los patterns pueden destructure enums, tuples, structs, references, ranges, literals y datos anidados; los guards añaden condiciones booleanas.

```rust
match status {
    Status::Ready => start(),
    Status::Failed(code) if code >= 500 => retry(),
    Status::Failed(code) => log_error(code),
    Status::Pending => wait(),
}
```

La exhaustividad convierte cambios del dominio en trabajo de compile time: añadir una variant revela matches que deben actualizarse. Prefiere enum variants frente a sentinels y booleans sueltos cuando el state space es conocido.
