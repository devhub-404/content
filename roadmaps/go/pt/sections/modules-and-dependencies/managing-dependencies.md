# Gerenciando Dependências

Go modules usam semantic versions e module graph para resolver dependencies. `go get` altera requirements, `go mod tidy` adiciona o necessário e remove o não usado, e `go list` inspeciona o grafo.

```go
// Typical workflow:
// go get example.com/lib@v1.2.3
// go mod tidy
// go list -m all
```

Revise upgrades como mudanças de source, principalmente majors e transitivas. Checksum database/proxy ajudam integridade, mas segurança também exige saber que código e versões entram na aplicação.
