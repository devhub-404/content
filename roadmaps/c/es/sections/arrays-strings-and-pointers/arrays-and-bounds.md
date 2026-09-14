# Arrays y Límites

Un array C almacena una cantidad fija de elementos contiguos del mismo tipo. Su longitud forma parte del tipo mientras el array en sí sea conocido. Acceder fuera del rango válido es undefined behavior.

```c
int values[4] = {10, 20, 30, 40};

for (size_t i = 0; i < 4; ++i) {
    printf("%d
", values[i]);
}
```

Al pasar un array a la mayoría de funciones se convierte en puntero al primer elemento y se pierde la longitud. Por eso las APIs C suelen recibir puntero y count explícito. Mantén ambos valores juntos y valida el count antes de indexar.
