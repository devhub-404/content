# Object Lifetime and Dangling Pointers

A pointer can remain numerically non-null after the object it referred to has ended its lifetime. Such a pointer is dangling and cannot be dereferenced. Automatic local objects normally cease to exist when their block exits; allocated objects cease after the matching deallocation.

```c
int *bad_pointer(void) {
    int value = 42;
    return &value; /* wrong: value dies on return */
}
```

Do not return pointers to ordinary local variables, store borrowed pointers longer than the owner's lifetime, or access memory after `free`. Setting one pointer variable to null after free can reduce accidental reuse through that variable, but it does not repair other aliases to the same dead object.
