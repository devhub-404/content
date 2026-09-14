# `malloc`, `calloc` y `free`

La asignación dinámica obtiene almacenamiento cuyo lifetime se controla explícitamente. `malloc` reserva bytes no inicializados, `calloc` reserva y pone a cero según su contrato y `free` libera una asignación viva de la familia correspondiente.

```c
size_t count = 100;
int *items = malloc(count * sizeof *items);
if (!items) {
    return -1;
}

/* use items */

free(items);
items = nullptr;
```

Toda asignación exitosa necesita un plan de ownership: quién la libera, por qué caminos y si ese ownership puede transferirse. Comprueba overflow en los tamaños, valida el puntero devuelto y evita double-free, use-after-free y leaks.
