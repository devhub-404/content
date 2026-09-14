# Unions and Tagged Unions

A union overlays several members in the same storage. At a given logical point, the program needs to know which representation is active and what operations the language permits on it. Unions are useful for compact variants and low-level representation work.

```c
enum value_kind { VALUE_INT, VALUE_DOUBLE };

struct value {
    enum value_kind kind;
    union {
        int as_int;
        double as_double;
    } data;
};
```

A tagged union pairs the union with an explicit discriminator so the program can select the correct member safely. Keep the tag and payload updated together. This pattern is the C equivalent of an algebraic variant, but the compiler does not enforce exhaustiveness or tag/payload consistency for you.
