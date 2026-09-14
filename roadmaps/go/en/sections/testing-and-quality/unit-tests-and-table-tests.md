# Unit Tests and Table-driven Tests

Tests live in `_test.go` files and use the standard `testing` package. Table-driven tests make it easy to run the same behavior over many named inputs, and `t.Run` creates useful subtests for targeted execution and reporting.

```go
func TestAdd(t *testing.T) {
    tests := []struct {
        name string
        a, b int
        want int
    }{
        {"positive", 2, 3, 5},
        {"zero", 0, 4, 4},
    }

    for _, tt := range tests {
        t.Run(tt.name, func(t *testing.T) {
            if got := Add(tt.a, tt.b); got != tt.want {
                t.Fatalf("got %d, want %d", got, tt.want)
            }
        })
    }
}
```

Test behavior and public contracts rather than mirroring internal implementation. Keep test data readable, use helpers with `t.Helper()`, and run `go test ./...` as the normal project-wide check. Test failures should explain the observed and expected values clearly.
