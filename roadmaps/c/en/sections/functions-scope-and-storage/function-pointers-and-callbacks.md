# Function Pointers and Callbacks

Functions can be referred to through function pointers and passed to other functions as callbacks. This is how facilities such as `qsort` receive behavior from the caller and how C libraries often model event handlers, policies, and plugin-style interfaces.

```c
typedef int (*compare_fn)(const void *, const void *);

int compare_ints(const void *a, const void *b) {
    const int left = *(const int *)a;
    const int right = *(const int *)b;
    return (left > right) - (left < right);
}
```

The function pointer type must match the actual callable signature. Generic callbacks that use `void *` move type checking into casts inside the callback, so document the data contract carefully. When possible, wrap raw callback signatures in domain-specific typedefs and helper functions.
