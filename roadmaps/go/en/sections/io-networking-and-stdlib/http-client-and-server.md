# HTTP Clients and Servers

`net/http` provides both client and server HTTP stacks. Handlers receive a request and write a response, while clients send requests through an `http.Client`. Modern `ServeMux` patterns can express methods and path variables directly.

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

Production HTTP needs timeouts, context cancellation, body closing, size limits, TLS/proxy awareness, and careful error handling. Reuse clients rather than creating one per request. On servers, define shutdown and in-flight request behavior instead of relying on abrupt process termination.
