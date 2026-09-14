# Cópia e Aliasing de Slices

Assignment de slice copia apenas o descriptor, não elementos, então slices podem aliasar o mesmo backing array. `copy` copia elementos para destino existente e lida corretamente com overlap.

```go
src := []int{1, 2, 3}
dst := make([]int, len(src))

copy(dst, src)
dst[0] = 99
```

Faça cópia real quando mutation independente for necessária. Padrões com `append` ou helpers da standard library também podem copiar. Saiba se uma API recebe storage compartilhado ou valor independente.
