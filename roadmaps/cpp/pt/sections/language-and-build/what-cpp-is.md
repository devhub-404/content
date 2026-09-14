# O que é C++ Moderno

C++ é uma linguagem compilada e estaticamente tipada que suporta vários estilos: programação orientada a valores, generic programming, classes que gerenciam recursos, polimorfismo OO e trabalho de baixo nível. C++ moderno depende muito de lifetimes determinísticos, templates, standard library e abstrações de compile time, não de `new`/`delete` espalhados pelo código.

```cpp
#include <iostream>
#include <string>

int main() {
    std::string name = "Mina";
    std::cout << "Hello, " << name << '
';
}
```

C++23 é a revisão ISO publicada mais recente usada como baseline estável, enquanto o próximo padrão continua em desenvolvimento no draft atual. Código existente cobre décadas, então aprender C++ moderno também significa reconhecer padrões antigos sem copiá-los quando a biblioteca padrão oferece alternativas mais seguras.
