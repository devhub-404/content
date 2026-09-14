# Cargo Workspaces

Un workspace agrupa packages relacionados compartiendo target directory, lockfile, dependency config y comandos coordinados. Es útil en monorepos con libraries/binaries separados.

```rust
[workspace]
members = [
    "crates/core",
    "crates/cli",
    "crates/web",
]
resolver = "3"
```

No conviertas cada carpeta en crate sin un boundary real. La estructura debe reflejar la arquitectura: packages se comunican mediante dependencies explícitas, no accediendo a private modules vecinos.
