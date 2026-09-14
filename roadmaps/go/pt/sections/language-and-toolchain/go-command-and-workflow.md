# Comando `go` e Workflow Diário

O comando `go` é o centro do toolchain padrão. Ele compila packages, executa programas e testes, gerencia dependencies, instala binaries e consulta metadata de packages/modules. Um projeto Go normalmente precisa de muito menos configuração customizada de build que outros ecossistemas compilados.

```go
// Typical commands:
// go run .
// go test ./...
// go fmt ./...
// go vet ./...
// go build ./...
```

Use as ferramentas padrão como workflow default antes de adicionar wrappers. `gofmt` define formatação, `go test` é o runner normal, `go vet` encontra construções suspeitas e `go build` segue o grafo de modules/packages. Convenções facilitam manutenção e CI.
