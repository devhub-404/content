# Warnings, Sanitizers y Static Analysis

Un build de producción debe activar warnings fuertes y tratar los nuevos warnings inexplicados como defectos. Los sanitizers exponen muchos errores de memoria, UB y concurrencia; los static analyzers pueden encontrar rutas que los tests no ejecutan.

```cpp
// Example build:
// c++ -std=c++23 -Wall -Wextra -Wconversion //     -fsanitize=address,undefined main.cpp
```

Ninguna herramienta demuestra corrección. Usa varios compiladores cuando importe portabilidad, ejecuta sanitizers en CI y combínalos con tests, review y análisis de dependencias. Los bugs low-level son mucho más fáciles de arreglar cerca de su origen.
