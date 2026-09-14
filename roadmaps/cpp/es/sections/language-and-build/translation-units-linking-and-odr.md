# Translation Units, Linking y ODR

C++ tradicionalmente compila translation units separadas y después enlaza. Las declaraciones indican qué existe en otro lugar; las definiciones aportan almacenamiento o implementación. La One Definition Rule controla cuándo una entidad necesita una única definición en el programa y cuándo definiciones equivalentes inline/template pueden aparecer en varias units.

```cpp
// math.hpp
#pragma once
int add(int a, int b);

// math.cpp
#include "math.hpp"
int add(int a, int b) { return a + b; }

// main.cpp
#include "math.hpp"
int main() { return add(2, 3) == 5 ? 0 : 1; }
```

Las declaraciones públicas suelen vivir en headers y la implementación debe incluir su propio header para que el compilador verifique el contrato. Los linker errors suelen indicar definiciones ausentes o duplicadas; las violaciones de ODR pueden ser más sutiles e incluso producir undefined behavior.
