# Race Detector and `go vet`

The race detector instruments a build to find unsynchronized conflicting memory accesses during execution. `go vet` performs static checks for suspicious constructs that are legal Go but commonly erroneous.

```go
// Typical checks:
// go test -race ./...
// go vet ./...
```

Both are normal quality tools, not substitutes for tests or review. The race detector sees only executed paths and changes timing; `go vet` intentionally does not try to prove every possible bug. Run them regularly enough that failures remain close to the change that introduced them.
