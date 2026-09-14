# `context` para Cancellation y Deadlines

`context.Context` transporta cancellation, deadlines y valores request-scoped a través de fronteras de API. I/O y trabajo long-running deben aceptar context cuando los callers necesiten cancelar o fijar deadline.

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

Pasa context explícitamente como primer parámetro en vez de guardarlo en structs para uso genérico. No pongas options normales en context; los values son para metadata request-scoped. Llama a las cancel functions cuando corresponda.
