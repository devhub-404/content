# Punto Flotante y Tipos Complejos

Los tipos principales de punto flotante son `float`, `double` y `long double`, con representaciones definidas por la implementación y a menudo basadas en IEC 60559/IEEE-754. Muchas fracciones decimales no son exactas en binario, así que comparaciones y algoritmos deben considerar el error numérico.

```c
#include <math.h>
#include <complex.h>

double x = 0.1;
double y = sqrt(2.0);
double complex z = 1.0 + 2.0 * I;
```

C también soporta aritmética compleja mediante tipos complejos y `<complex.h>`. `<float.h>` expone características de floating-point y `<math.h>` funciones comunes. Elige el tipo y el algoritmo según el presupuesto de error en vez de suponer que más dígitos arreglan un cálculo inestable.
