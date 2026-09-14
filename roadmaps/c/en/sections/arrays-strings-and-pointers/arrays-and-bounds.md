# Arrays and Bounds

A C array stores a fixed number of contiguous elements of one type. Its length is part of the array type in the scope where the array itself is known. Accessing outside the array's valid element range is undefined behavior.

```c
int values[4] = {10, 20, 30, 40};

for (size_t i = 0; i < 4; ++i) {
    printf("%d
", values[i]);
}
```

When an array expression is passed to most functions, it is converted to a pointer to its first element and the length information is lost. That is why C APIs commonly accept a pointer plus an explicit element count. Keep those values together and validate counts before indexing.
