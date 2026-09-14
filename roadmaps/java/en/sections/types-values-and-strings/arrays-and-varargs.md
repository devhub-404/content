# Arrays and Varargs

Java arrays are fixed-length objects with runtime element-type checks and zero-initialized elements. Varargs syntax `T...` is implemented as an array parameter and lets callers provide zero or more arguments.

```java
int[] values = {10, 20, 30};

static int sum(int... values) {
    int total = 0;
    for (int value : values) total += value;
    return total;
}
```

Arrays are useful for fixed contiguous data and low-level APIs, while collections are usually more flexible for application code. Generic arrays have restrictions because arrays are reified at runtime while Java generics are mostly erased.
