# The `go` Command and Daily Workflow

The `go` command is the center of the standard toolchain. It builds packages, runs programs, executes tests, formats modules through related tooling, manages dependencies, installs binaries, and queries package/module metadata. A Go project usually needs much less custom build configuration than many compiled-language ecosystems.

```go
// Typical commands:
// go run .
// go test ./...
// go fmt ./...
// go vet ./...
// go build ./...
```

Use the standard tools as the default workflow before adding wrappers. `gofmt` defines formatting, `go test` is the normal test runner, `go vet` catches suspicious constructs, and `go build` follows the module/package graph. Keeping the conventional workflow makes projects easier for other Go developers and CI systems to understand.
