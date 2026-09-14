# Depuración de Programas C Nativos

Los debuggers nativos permiten breakpoints, inspección de stack frames y memoria, stepping y análisis de crashes/core dumps. Compila con información de debug y un nivel de optimización adecuado para que el estado a nivel de source sea comprensible.

```c
int divide(int a, int b) {
    return a / b;
}
```

Cuando un crash aparece lejos de la causa, busca corrupción anterior, use-after-free o aritmética de tamaños inválida. Reproduce con input mínimo, combina debugger y sanitizers y conserva el binario y símbolos exactos de producción al investigar.
