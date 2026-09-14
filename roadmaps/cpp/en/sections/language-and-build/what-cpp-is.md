# What Modern C++ Is

C++ is a statically typed compiled language designed to support several programming styles: value-oriented programming, generic programming, resource-managing classes, object-oriented polymorphism, and low-level systems work. Modern C++ relies heavily on deterministic lifetimes, templates, the standard library, and compile-time abstraction rather than manual memory management everywhere.

```cpp
#include <iostream>
#include <string>

int main() {
    std::string name = "Mina";
    std::cout << "Hello, " << name << '
';
}
```

C++23 is the latest published ISO revision widely treated as the stable language baseline, while work on the next standard continues in the current draft. Existing code spans decades, so learning modern C++ also means recognizing older patterns without copying them into new code when safer standard-library facilities exist.
