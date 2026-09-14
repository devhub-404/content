# Clientes e Servidores HTTP

`net/http` fornece stacks client e server. Handlers recebem request e escrevem response, enquanto clients enviam por `http.Client`. Patterns modernos de `ServeMux` expressam methods e path variables diretamente.

```go
mux := http.NewServeMux()

mux.HandleFunc("GET /health", func(
    w http.ResponseWriter,
    r *http.Request,
) {
    w.WriteHeader(http.StatusNoContent)
})

server := &http.Server{
    Addr:    ":8080",
    Handler: mux,
}
```

HTTP de produção precisa timeouts, context cancellation, fechamento de body, size limits, TLS/proxy awareness e error handling. Reuse clients. Em servers, defina shutdown e requests in-flight em vez de término abrupto.
