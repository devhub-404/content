# Translation Units, Linking e ODR

C++ tradicionalmente compila translation units separadas e depois faz linking. Declarações dizem o que existe em outro lugar; definições fornecem storage ou implementação. A One Definition Rule controla quando uma entidade precisa de uma única definição no programa e quando definições equivalentes inline/template podem aparecer em várias units.

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

Declarações públicas normalmente ficam em headers e a implementação deve incluir o próprio header para o compilador verificar o contrato. Linker errors costumam indicar definição ausente ou duplicada, enquanto violações de ODR podem ser mais sutis e até virar undefined behavior.
