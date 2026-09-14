# Memory Model e Data Races

Memory model define quando writes de uma goroutine são garantidos a outra. Acessos conflitantes sem sincronização são data races e tornam o programa inválido mesmo se parecer funcionar.

```go
var value int
var ready atomic.Bool

go func() {
    value = 42
    ready.Store(true)
}()

if ready.Load() {
    fmt.Println(value)
}
```

Use channels, mutexes ou atomics para estabelecer happens-before. Race detector (`-race`) é ferramenta importante, mas só encontra races em caminhos executados.
