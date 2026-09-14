# Pointer Arithmetic and Array Traversal

Pointer arithmetic is defined relative to an array object. Adding an integer moves by elements, not raw bytes, and a pointer may legally point one past the last element for comparison or subtraction but must not be dereferenced there.

```c
int values[] = {10, 20, 30};

for (int *p = values; p != values + 3; ++p) {
    printf("%d
", *p);
}
```

Subtraction and ordering comparisons are meaningful only under the standard's related-pointer rules. For generic byte-wise memory traversal use pointers to character types, which have special access permissions for object representations. Prefer indexing when it communicates intent more clearly.
