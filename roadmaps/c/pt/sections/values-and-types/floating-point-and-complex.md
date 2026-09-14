# Ponto Flutuante e Tipos Complexos

Os tipos de ponto flutuante principais são `float`, `double` e `long double`, com representações definidas pela implementação e frequentemente baseadas em IEC 60559/IEEE-754. Muitas frações decimais não são exatas em binário, então comparações e algoritmos precisam considerar erro numérico.

```c
#include <math.h>
#include <complex.h>

double x = 0.1;
double y = sqrt(2.0);
double complex z = 1.0 + 2.0 * I;
```

C também suporta aritmética complexa com tipos complexos e `<complex.h>`. `<float.h>` expõe características de floating-point e `<math.h>` funções comuns. Escolha tipo e algoritmo conforme o orçamento de erro em vez de presumir que mais dígitos corrigem cálculo numericamente instável.
