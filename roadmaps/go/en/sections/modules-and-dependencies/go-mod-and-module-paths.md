# `go.mod` and Module Paths

A module groups versioned packages and is identified by a module path declared in `go.mod`. The file also records the Go language/toolchain expectations and dependency requirements used by the module graph.

```go
module example.com/project

go 1.27

require example.com/dependency v1.4.0
```

Module paths are part of import paths and become public API when a module is published. Choose them deliberately. Keep `go.mod` and `go.sum` under version control, and use standard commands rather than hand-editing dependency checksums.
