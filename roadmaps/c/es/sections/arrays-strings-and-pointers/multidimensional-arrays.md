# Arrays Multidimensionales

Un array multidimensional en C es un array cuyos elementos son otros arrays. El almacenamiento de arrays anidados ordinarios es contiguo en row-major order. Las dimensiones internas forman parte del tipo y son necesarias para calcular el salto entre filas.

```c
int matrix[2][3] = {
    {1, 2, 3},
    {4, 5, 6},
};

printf("%d
", matrix[1][2]);
```

Los parámetros de función para arrays multidimensionales deben describir suficientes dimensiones para calcular direcciones, o usar un buffer plano con dimensiones/strides explícitos. Elige una representación y documenta el layout.
