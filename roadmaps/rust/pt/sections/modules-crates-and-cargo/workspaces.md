# Cargo Workspaces

Workspace agrupa packages relacionados compartilhando target directory, lockfile, dependency config e comandos coordenados. É útil em monorepos com libraries/binaries separados.

```rust
[workspace]
members = [
    "crates/core",
    "crates/cli",
    "crates/web",
]
resolver = "3"
```

Não transforme toda pasta em crate sem boundary real. Estrutura deve refletir arquitetura: packages comunicam por dependencies explícitas, não acessando private modules de vizinhos.
