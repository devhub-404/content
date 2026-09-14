# `context` para Cancellation e Deadlines

`context.Context` carrega cancellation, deadlines e valores request-scoped por fronteiras de API. I/O e trabalho long-running devem aceitar context quando callers precisam cancelar ou limitar deadline.

```go
func load(ctx context.Context) error {
    req, err := http.NewRequestWithContext(
        ctx,
        http.MethodGet,
        endpoint,
        nil,
    )
    if err != nil {
        return err
    }

    _, err = http.DefaultClient.Do(req)
    return err
}
```

Passe context explicitamente como primeiro parâmetro em vez de guardá-lo em structs para uso genérico. Não coloque options comuns em context; values servem a metadata request-scoped. Chame cancel functions quando exigido.
