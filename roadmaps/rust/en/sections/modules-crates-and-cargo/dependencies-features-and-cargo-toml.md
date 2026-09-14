# Dependencies, Features, and `Cargo.toml`

Cargo resolves dependencies from manifests and lockfiles, while features enable additive conditional capabilities within a package. Feature unification means dependencies in one build may receive the union of requested features from several dependents.

```rust
[dependencies]
serde = { version = "1", features = ["derive"] }

[features]
default = []
json = ["dep:serde_json"]
```

Features should normally be additive rather than mutually exclusive switches because downstream packages can activate them independently. Review dependency updates, commit `Cargo.lock` for applications/binaries, and understand your project's policy for libraries and reproducible builds.
