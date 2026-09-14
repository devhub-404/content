# Language Versions and Compatibility

Go modules declare a Go language version that controls which language semantics are expected for the module. Toolchains also evolve independently, and newer toolchains can build modules targeting older compatible language versions.

```go
// go.mod
module example.com/project

go 1.27
```

When using a new feature, confirm whether it is a language feature, standard-library API, or toolchain feature and what minimum version it requires. Keep the module's declared version honest so downstream users and tooling receive the correct compatibility signal.
