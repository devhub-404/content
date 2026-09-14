# `realloc` and Growing Buffers

`realloc` changes the size of an allocation and may return the same address or move the data to a new allocation. On failure the original allocation remains valid, which is why assigning the result directly to the only pointer can leak the original block.

```c
size_t new_count = count * 2;
int *tmp = realloc(items, new_count * sizeof *items);

if (tmp) {
    items = tmp;
    count = new_count;
}
```

Use a temporary pointer and update ownership only after success. Calculate the new byte size with overflow checks before calling `realloc`. C23 makes `realloc(ptr, 0)` undefined behavior, so handle a desired zero-size result explicitly instead of relying on older special cases.
