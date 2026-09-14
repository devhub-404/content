# `typeof`, `auto`, and C23 Type Inference

C23 adds standardized type inference and type-query facilities including `auto` in inferred object declarations and `typeof`/`typeof_unqual`. They reduce repetition in declarations whose type is already determined by an initializer or expression.

```c
auto x = 42;
typeof(x) y = 7;
typeof_unqual(x) z = 9;
```

These features do not turn C into a dynamically typed language: the compiler still determines one static type during translation. Use inference where it removes brittle duplication without hiding an important interface type, and be conscious of qualifiers and conversions in the expression being queried.
