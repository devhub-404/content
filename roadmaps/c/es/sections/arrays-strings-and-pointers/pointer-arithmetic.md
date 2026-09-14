# Aritmética de Punteros y Recorrido de Arrays

La aritmética de punteros está definida respecto a un objeto array. Sumar un entero avanza por elementos, no por bytes, y se puede formar un puntero one-past para comparar o restar, pero no hacer dereference allí.

```c
int values[] = {10, 20, 30};

for (int *p = values; p != values + 3; ++p) {
    printf("%d
", *p);
}
```

La resta y las comparaciones de orden solo son válidas bajo las relaciones permitidas por el estándar. Para recorrer memoria byte a byte usa punteros a character types. Prefiere indexación cuando comunica mejor la intención.
