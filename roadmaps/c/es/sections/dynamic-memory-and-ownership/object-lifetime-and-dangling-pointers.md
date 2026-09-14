# Lifetime de Objetos y Dangling Pointers

Un puntero puede seguir siendo numéricamente no-null después de terminar el lifetime del objeto al que apuntaba. Entonces queda dangling y no puede dereferenciarse. Los locales automáticos suelen morir al salir del bloque; los objetos dinámicos terminan con su deallocation.

```c
int *bad_pointer(void) {
    int value = 42;
    return &value; /* wrong: value dies on return */
}
```

No devuelvas punteros a variables locales ordinarias, no conserves borrowed pointers más tiempo que su owner y no accedas tras `free`. Poner un alias a null puede evitar su reutilización, pero no arregla otros aliases al objeto ya muerto.
