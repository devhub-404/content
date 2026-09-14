# Conversions and Integer Promotions

C performs many implicit conversions. Small integer types usually undergo integer promotions before arithmetic, and expressions mixing signed, unsigned, integer, and floating types follow the usual arithmetic conversions. A conversion can change value when the destination cannot represent the source.

```c
#include <stdint.h>

uint8_t a = 250;
uint8_t b = 10;

int sum = a + b;   /* promoted before addition */
```

Do not rely on intuition from the declared type alone: the operands of an expression may be promoted before the operator executes. Enable compiler warnings for conversion-sensitive code and use explicit checked conversions at API or storage boundaries where truncation or sign changes would be bugs.
