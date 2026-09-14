# Integer Types and Limits

C provides several signed and unsigned integer types whose exact widths depend on the implementation, subject to minimum ranges. `<stdint.h>` adds fixed-width types such as `int32_t` when the implementation can provide them, plus least-width, fast, and pointer-sized integer families.

```c
#include <stdint.h>
#include <inttypes.h>

int32_t temperature = -12;
uint64_t count = 1000;

printf("%" PRIu64 "
", count);
```

Choose a type from the range and interface you need, not by assuming that `int` is always 32 bits or `long` is always 64. `<limits.h>`, `<stdint.h>`, and `<inttypes.h>` provide limits and portable formatting tools. Unsigned arithmetic wraps modulo its range; signed overflow is undefined.
