# Static Assertions and Attributes

`static_assert` checks a constant condition during translation and is useful for layout, configuration, and platform assumptions. C23 also standardizes an attribute syntax that can attach supported metadata such as `[[nodiscard]]`, `[[deprecated]]`, and `[[maybe_unused]]` according to the language rules.

```c
#include <stdint.h>

static_assert(sizeof(uint32_t) == 4);

[[nodiscard]]
int write_record(const void *data, size_t size);
```

Use compile-time assertions for assumptions the implementation can prove before running the program. Attributes should communicate real API or optimization intent, while code must remain correct according to the attribute's contract. Unsupported or implementation-specific attributes require portability planning.
