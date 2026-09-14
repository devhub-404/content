# Funciones Variádicas

Un parámetro final `...T` permite recibir cero o más valores y da a la función un slice de esos valores. Un slice existente puede expandirse en la llamada con `slice...`.

```go
func sum(values ...int) int {
    total := 0
    for _, value := range values {
        total += value
    }
    return total
}

total := sum(1, 2, 3)
```

Las variadic functions sirven para listas opcionales homogéneas, no para sustituir configuración estructurada. Cuando las opciones tienen significados o tipos distintos, una struct o functional options comunica mejor que `...any`.
