# `malloc`, `calloc`, and `free`

Dynamic allocation obtains storage whose lifetime is controlled explicitly. `malloc` allocates uninitialized storage, `calloc` allocates and zeroes the bytes according to its contract, and `free` releases a live allocation obtained from the appropriate allocation family.

```c
size_t count = 100;
int *items = malloc(count * sizeof *items);
if (!items) {
    return -1;
}

/* use items */

free(items);
items = nullptr;
```

Every successful allocation needs an ownership plan: who frees it, on which paths, and whether ownership can move. Check size arithmetic for overflow before allocating arrays, check the returned pointer, and avoid double-free, use-after-free, and lost allocations.
