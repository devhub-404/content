# Translation Units, Linking, and the ODR

C++ source is traditionally compiled as translation units and then linked. Declarations tell one unit what exists elsewhere, while definitions provide storage or implementation. The One Definition Rule governs when entities must have exactly one program definition and when equivalent inline/template definitions may appear in multiple units.

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

Public declarations normally live in headers, and the implementation should include its own header so the compiler checks the contract. Linker errors often indicate a missing or duplicate definition, while ODR violations can be subtler and may produce undefined behavior rather than a clean diagnostic.
