# Unit Tests y Table-driven Tests

Los tests viven en `_test.go` y usan el package `testing`. Los table-driven tests ejecutan el mismo comportamiento sobre varios inputs con nombre y `t.Run` crea subtests útiles.

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

Prueba comportamiento y contratos públicos, no dupliques la implementación. Mantén los datos legibles, usa helpers con `t.Helper()` y ejecuta `go test ./...` como check normal. Los fallos deben mostrar claramente valores obtenidos y esperados.
