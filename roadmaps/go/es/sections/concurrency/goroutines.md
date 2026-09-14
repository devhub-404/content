# Goroutines

Una goroutine es una función que se ejecuta concurrentemente gestionada por el runtime. Empezarla con `go` es barato frente a crear un thread del sistema, pero toda goroutine necesita un lifetime, una forma de terminar y un ownership claro de los datos que toca.

```go
go func() {
    result := doWork()
    results <- result
}()
```

No lances goroutines sin saber cómo terminan. Las goroutines filtradas retienen stacks, referencias, timers, sockets y otros recursos. El código estructurado vincula su lifetime a un request, context, worker group o componente owner.
