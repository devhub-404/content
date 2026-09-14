# Dependencies, Features y `Cargo.toml`

Cargo resuelve dependencies mediante manifests/lockfiles y las features habilitan capacidades condicionales aditivas. Feature unification significa que una dependencia puede recibir la unión de features solicitadas por varios dependents.

```rust
[dependencies]
serde = { version = "1", features = ["derive"] }

[features]
default = []
json = ["dep:serde_json"]
```

Las features normalmente deben ser aditivas, no switches mutuamente exclusivos. Revisa upgrades, versiona lockfiles según el tipo de proyecto y entiende la política de reproducibility.
