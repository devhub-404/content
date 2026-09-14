# Loops `for`, `while` y `do`

`for` es cómodo cuando inicialización, condición y actualización pertenecen juntas. `while` repite mientras la condición sea distinta de cero y `do ... while` comprueba después del cuerpo, por lo que se ejecuta al menos una vez.

```c
for (size_t i = 0; i < count; ++i) {
    process(items[i]);
}

while (queue_has_items()) {
    consume_next();
}
```

`break` sale del loop o switch más interno y `continue` pasa a la siguiente iteración. Ten cuidado con límites enteros, especialmente al mezclar signed y unsigned. Para recorrer arrays, deriva el límite del tamaño real o de un count explícito pasado junto al puntero.
