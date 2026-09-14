# Unit Tests e Table-driven Tests

Tests ficam em `_test.go` e usam package `testing`. Table-driven tests executam o mesmo comportamento em vários inputs nomeados, e `t.Run` cria subtests úteis.

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

Teste comportamento e contratos públicos, não copie a implementação. Mantenha dados legíveis, use helpers com `t.Helper()` e rode `go test ./...` como check normal. Falhas devem mostrar valores obtidos/esperados claramente.
