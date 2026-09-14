# `realloc` y Buffers Crecientes

`realloc` cambia el tamaño de una asignación y puede conservar la dirección o mover los datos. Si falla, la asignación original sigue siendo válida, por eso asignar el retorno directamente al único puntero puede perder el bloque anterior.

```c
size_t new_count = count * 2;
int *tmp = realloc(items, new_count * sizeof *items);

if (tmp) {
    items = tmp;
    count = new_count;
}
```

Usa un puntero temporal y actualiza ownership solo después del éxito. Calcula el nuevo tamaño comprobando overflow. En C23, `realloc(ptr, 0)` es undefined behavior, así que trata el tamaño cero explícitamente.
