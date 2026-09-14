# Slices, Length, Capacity y `append`

Un slice es un descriptor sobre un array subyacente con length y capacity. Slicing crea otra view y `append` extiende la secuencia, pudiendo asignar un nuevo backing array cuando la capacity no basta.

```go
values := make([]int, 0, 4)
values = append(values, 10, 20, 30)

fmt.Println(len(values), cap(values))
```

Varios slices pueden compartir el mismo backing array, así que mutar uno puede afectar a otro. Usa siempre el slice devuelto por `append`. Preasigna capacity cuando haya una buena estimación, sin exagerar.
