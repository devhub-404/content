# `typedef` and Type Names

`typedef` creates another name for an existing type; it does not create a new nominally distinct type. It is useful for abstracting verbose declarations, naming function pointer signatures, and presenting library types without repeatedly spelling their implementation form.

```c
typedef struct {
    double x;
    double y;
} point;

point p = { .x = 1.0, .y = 2.0 };
```

A typedef can improve readability or hide important information, depending on the name. Avoid disguising pointer ownership or constness behind surprising aliases. Public typedefs should communicate a stable abstraction rather than merely shorten syntax by a few characters.
