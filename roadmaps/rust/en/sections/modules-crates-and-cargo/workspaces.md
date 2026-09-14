# Cargo Workspaces

A Cargo workspace groups related packages so they can share a target directory, lockfile, dependency configuration, and coordinated commands. It is useful for monorepos with multiple libraries and binaries that remain separate packages.

```rust
[workspace]
members = [
    "crates/core",
    "crates/cli",
    "crates/web",
]
resolver = "3"
```

Do not turn every folder into its own crate without a real dependency or release boundary. Workspace structure should reflect architecture: packages communicate through explicit dependencies rather than reaching into each other's private module trees.
