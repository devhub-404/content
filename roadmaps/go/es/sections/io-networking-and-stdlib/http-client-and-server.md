# Clientes y Servidores HTTP

`net/http` ofrece stacks client y server. Los handlers reciben un request y escriben una response, mientras los clients envían mediante `http.Client`. Los patterns modernos de `ServeMux` expresan methods y path variables directamente.

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

HTTP de producción necesita timeouts, context cancellation, cierre de body, size limits, TLS/proxy awareness y error handling. Reutiliza clients. En servers, define shutdown y requests in-flight en vez de terminar abruptamente.
