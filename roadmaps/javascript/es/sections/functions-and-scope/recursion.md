# Recursión

Una función recursiva se llama a sí misma directa o indirectamente. Necesita un caso base que detenga las llamadas y un paso que avance hacia ese caso. Árboles, estructuras anidadas, parsers y algoritmos divide-and-conquer suelen tener formas naturalmente recursivas.

```js
function factorial(n) {
  if (n <= 1) return 1;
  return n * factorial(n - 1);
}
```

Cada llamada consume stack y los engines no optimizan tail calls de forma universal en la práctica. Con profundidades grandes o controladas por input externo, usa iteración o una pila explícita. Elige recursión cuando represente claramente la estructura del problema, no porque parezca más elegante.
