# Copia y Aliasing de Slices

Asignar un slice copia solo el descriptor, no los elementos, por lo que ambos pueden aliasar el mismo backing array. `copy` copia elementos a un destino existente y maneja correctamente el overlap.

```go
src := []int{1, 2, 3}
dst := make([]int, len(src))

copy(dst, src)
dst[0] = 99
```

Haz una copia real cuando necesites mutación independiente. Patrones con `append` o helpers de la standard library también pueden copiar. Debes saber si una API recibe almacenamiento compartido o un valor independiente.
