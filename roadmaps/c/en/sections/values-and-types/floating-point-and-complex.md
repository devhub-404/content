# Floating-point and Complex Types

The core floating types are `float`, `double`, and `long double`, with implementation-defined representations that commonly follow IEC 60559/IEEE-754. Many decimal fractions are not exact in binary, so equality checks and numerical algorithms need error-aware design.

```c
#include <math.h>
#include <complex.h>

double x = 0.1;
double y = sqrt(2.0);
double complex z = 1.0 + 2.0 * I;
```

C also supports complex arithmetic through complex types and `<complex.h>`. `<float.h>` exposes floating-point characteristics and `<math.h>` common functions. Use the type and algorithm appropriate to the numerical error budget instead of assuming that more digits automatically fix an unstable calculation.
