# Race Detector e `go vet`

Race detector instrumenta build para encontrar acessos conflitantes sem sincronização durante execução. `go vet` faz checks estáticos de construções legais mas frequentemente erradas.

```go
// Typical checks:
// go test -race ./...
// go vet ./...
```

Ambos são ferramentas normais, não substitutos de tests/review. Race detector só vê caminhos executados e altera timing; vet não tenta provar todo bug. Rode regularmente para manter falhas próximas da mudança causadora.
