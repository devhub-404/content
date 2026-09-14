# Tipos Fundamentais

C++ possui famílias de inteiros, floating-point, `bool`, character types e `void`. As larguras dos inteiros tradicionais dependem da implementação, enquanto `<cstdint>` fornece nomes fixed-width quando a plataforma consegue suportá-los.

```cpp
#include <cstdint>
#include <limits>

std::int32_t temperature = -12;
double ratio = 0.75;
bool ready = true;
char separator = ':';
```

Escolha tipos pelo range e interface necessários, não por assumptions como `long` sempre ter 64 bits. Overflow signed é undefined; unsigned faz wrap módulo o range. Character types também têm papéis de encoding e aliasing além de representar ASCII visível.
