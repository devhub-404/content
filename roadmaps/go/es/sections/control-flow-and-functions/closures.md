# Function Values y Closures

Las funciones son valores de primera clase y pueden almacenarse, pasarse y retornarse. Una closure captura variables del entorno léxico y estas permanecen vivas mientras sean necesarias.

```go
func makeCounter() func() int {
    count := 0

    return func() int {
        count++
        return count
    }
}
```

Las closures aparecen en handlers, callbacks, predicates, middleware y goroutines. Sé deliberado con estado mutable capturado, especialmente en concurrencia. Capturar un objeto grande también puede prolongar su lifetime.
