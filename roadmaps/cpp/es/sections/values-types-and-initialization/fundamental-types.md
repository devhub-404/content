# Tipos Fundamentales

C++ tiene familias de enteros, tipos floating-point, `bool`, character types y `void`. Las anchuras de los enteros tradicionales dependen de la implementación, mientras `<cstdint>` proporciona nombres fixed-width cuando la plataforma puede soportarlos.

```cpp
#include <cstdint>
#include <limits>

std::int32_t temperature = -12;
double ratio = 0.75;
bool ready = true;
char separator = ':';
```

Elige tipos según el rango y la interfaz necesarios, no por assumptions como que `long` siempre tenga 64 bits. El overflow signed es undefined; unsigned hace wrap módulo su rango. Los character types también tienen funciones de encoding y aliasing más allá de representar ASCII visible.
