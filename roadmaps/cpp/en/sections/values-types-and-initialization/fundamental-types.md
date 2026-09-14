# Fundamental Types

C++ fundamental types include several integer families, floating-point types, `bool`, character types, and `void`. Exact widths of the traditional integer types depend on the implementation, while `<cstdint>` provides fixed-width names where the platform can support them.

```cpp
#include <cstdint>
#include <limits>

std::int32_t temperature = -12;
double ratio = 0.75;
bool ready = true;
char separator = ':';
```

Choose types from the domain range and interface you need rather than assumptions such as `long` always being 64 bits. Signed integer overflow is undefined; unsigned arithmetic wraps modulo its range. Character types also have encoding and aliasing roles beyond simply holding visible ASCII characters.
