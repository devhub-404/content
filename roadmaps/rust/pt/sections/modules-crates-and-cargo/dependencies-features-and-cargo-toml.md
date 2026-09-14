# Dependencies, Features e `Cargo.toml`

Cargo resolve dependencies por manifests/lockfiles e features habilitam capacidades condicionais aditivas. Feature unification significa que dependência pode receber union de features pedidas por vários dependents.

```rust
[dependencies]
serde = { version = "1", features = ["derive"] }

[features]
default = []
json = ["dep:serde_json"]
```

Features normalmente devem ser aditivas, não switches mutuamente exclusivos. Revise upgrades, version lockfiles conforme tipo de projeto e entenda política de reproducibility.
