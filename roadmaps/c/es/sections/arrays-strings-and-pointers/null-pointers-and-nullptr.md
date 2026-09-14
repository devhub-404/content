# Punteros Nulos y `nullptr`

Un null pointer representa ausencia de objeto o función. C23 añade la keyword `nullptr` y `nullptr_t`, ofreciendo una constante específica en vez de depender solo del entero cero o de la macro `NULL`.

```c
int *find_value(int *items, size_t n, int target) {
    for (size_t i = 0; i < n; ++i) {
        if (items[i] == target) return &items[i];
    }
    return nullptr;
}
```

Comprobar un puntero en una condición sigue siendo idiomático y hacer dereference de null sigue siendo inválido. Las APIs públicas deben documentar si null es una opción válida o un error. Distingue un puntero null de un array vacío o de un puntero válido con longitud cero.
