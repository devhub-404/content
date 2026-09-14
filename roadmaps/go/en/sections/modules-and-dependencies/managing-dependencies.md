# Managing Dependencies

Go modules use semantic versions and a module graph to resolve dependencies. `go get` changes requirements, `go mod tidy` adds dependencies required by imports/tests and removes unused ones, and `go list` can inspect the graph.

```go
// Typical workflow:
// go get example.com/lib@v1.2.3
// go mod tidy
// go list -m all
```

Review dependency upgrades like source changes, especially major versions and transitive additions. Go's checksum database and proxy ecosystem improve reproducibility and integrity, but dependency security also requires understanding what code and versions your application includes.
