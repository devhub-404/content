# Goroutines

Goroutine é função executando concorrentemente gerenciada pelo runtime. Começar com `go` é barato comparado a thread OS, mas toda goroutine precisa de lifetime, forma de terminar e ownership claro dos dados acessados.

```go
go func() {
    result := doWork()
    results <- result
}()
```

Não lance goroutines sem saber como param. Goroutines vazadas retêm stacks, referências, timers, sockets e recursos. Código estruturado liga lifetime a request, context, worker group ou componente owner.
