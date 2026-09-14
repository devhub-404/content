# Qué es C++ Moderno

C++ es un lenguaje compilado y estáticamente tipado que soporta varios estilos: programación orientada a valores, generic programming, clases que gestionan recursos, polimorfismo OO y trabajo de bajo nivel. El C++ moderno depende mucho de lifetimes deterministas, templates, la standard library y abstracciones de compile time, no de `new`/`delete` por todas partes.

```cpp
#include <iostream>
#include <string>

int main() {
    std::string name = "Mina";
    std::cout << "Hello, " << name << '
';
}
```

C++23 es la revisión ISO publicada más reciente usada como baseline estable, mientras el siguiente estándar sigue evolucionando en el draft actual. El código existente abarca décadas, así que aprender C++ moderno también implica reconocer patrones antiguos sin copiarlos cuando la biblioteca estándar ofrece alternativas más seguras.
