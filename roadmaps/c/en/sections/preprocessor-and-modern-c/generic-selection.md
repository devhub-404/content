# Generic Selection with `_Generic`

`_Generic` selects an expression according to the type of a controlling expression and is the main standard mechanism for type-generic interfaces in C source. It can provide convenient wrappers around families of typed functions without runtime dispatch.

```c
#define type_name(x) _Generic((x),     int: "int",                      double: "double",                default: "other")

printf("%s
", type_name(3.14));
```

Generic selection is still compile-time macro-like metaprogramming and can become difficult to maintain when overloaded with too many cases. Keep the underlying real functions visible and test how qualifiers and conversions affect the controlling type.
