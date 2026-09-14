# Alocação e Escape Analysis

Go decide placement de storage por escape analysis. Retornar endereço de local é seguro porque compiler/runtime garante lifetime adequado; o objeto pode ir para heap quando necessário.

```go
func build() *int {
    value := 42
    return &value
}
```

Não deforme source por guesses de stack/heap. Use diagnostics e profiles quando allocations importam. Ganhos maiores costumam vir de estruturas, APIs, evitar cópias/conversions e reuse de buffers em hot paths medidos.
