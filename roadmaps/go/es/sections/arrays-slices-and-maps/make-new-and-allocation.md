# `make`, `new` y Asignación

`new(T)` asigna almacenamiento inicializado a cero para un `T` y devuelve `*T`. `make` inicializa la representación runtime de slices, maps y channels y devuelve el valor, no un puntero.

```go
values := make([]int, 10)
lookup := make(map[string]int)

ptr := new(int)
*ptr = 42
```

Mucho código Go usa literals y zero values en vez de estas funciones. El compilador decide stack o heap mediante escape analysis; `new` en el source no significa directamente «heap allocation» al estilo C.
