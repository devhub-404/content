# `inline` y Funciones Definidas en Headers

El specifier `inline` participa en las reglas de definiciones y linkage; no es una orden que obligue al compilador a insertar el machine code. El optimizador puede inlinear sin la keyword o decidir no hacerlo aunque esté presente.

```c
static inline int min_int(int a, int b) {
    return a < b ? a : b;
}
```

Para helpers pequeños definidos en headers, `static inline` es un patrón común porque cada translation unit recibe una definición con internal linkage. Los patrones de external inline son más sutiles y conviene usarlos solo cuando sean necesarios.
