# Arrays

El tipo de un array incluye su length: `[3]int` y `[4]int` son tipos distintos. Los arrays son valores, por lo que assignment y paso por parámetro copian el array salvo que se use un puntero.

```go
var a [3]int
b := [3]int{10, 20, 30}

fmt.Println(a, b)
```

Los arrays son importantes como almacenamiento subyacente de slices y para valores de tamaño fijo, pero las APIs de colección variable suelen usar slices. Usa array cuando la longitud fija tenga significado.
