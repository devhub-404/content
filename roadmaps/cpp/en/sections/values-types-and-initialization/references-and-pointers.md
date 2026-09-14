# References and Pointers

A reference is an alias bound to an object or function and, once initialized, does not reseat like a pointer. A pointer is an object that stores a pointer value, can be null, can be reassigned, and supports pointer operations according to the language rules.

```cpp
int value = 42;

int &ref = value;
int *ptr = &value;

ref = 50;
*ptr = 60;
```

Use references for required aliases and pointers when optionality, reseating, pointer arithmetic, or explicit pointer semantics are part of the interface. Neither raw pointer nor reference inherently expresses ownership; modern APIs should make ownership visible through value types or smart pointers.
