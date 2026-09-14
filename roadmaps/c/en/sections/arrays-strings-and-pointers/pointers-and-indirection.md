# Pointers and Indirection

A pointer stores an address or pointer value referring to an object, function, or one-past array position according to C's pointer rules. `&` obtains an address and unary `*` dereferences a pointer to access the referred object.

```c
int value = 42;
int *ptr = &value;

*ptr = 50;
printf("%d
", value);
```

A pointer must have a valid provenance/lifetime relationship for the operation you perform. Dereferencing null, dangling, uninitialized, or otherwise invalid pointers is undefined behavior. Treat pointer validity and ownership as explicit invariants rather than assumptions.
