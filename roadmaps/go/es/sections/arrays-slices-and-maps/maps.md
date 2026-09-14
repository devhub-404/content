# Maps

Map es un tipo reference built-in de claves comparable a valores. Buscar una clave ausente devuelve el zero value; la forma de dos resultados indica además si la clave estaba presente.

```go
counts := map[string]int{
    "go": 2,
}

counts["rust"]++

value, ok := counts["missing"]
fmt.Println(value, ok)
```

El zero value de un map es nil: puede leerse, pero no recibir assignments hasta `make`/literal. El orden de iteración es unspecified. Los maps no son seguros para writes concurrentes sin sincronización y la clave debe ser comparable.
