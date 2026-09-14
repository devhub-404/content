# Ownership Conventions in C APIs

C has no language-level ownership checker, so APIs must establish conventions. A pointer may be borrowed for a call, retained by the callee, transferred to the callee, or returned with ownership to the caller. These cases should be documented and reflected in function names and types where possible.

```c
struct buffer {
    unsigned char *data;
    size_t length;
};

void buffer_destroy(struct buffer *buffer) {
    free(buffer->data);
    buffer->data = nullptr;
    buffer->length = 0;
}
```

Pair resource-producing functions with clear destroy/free functions, initialize owners to safe empty states, and make cleanup paths idempotent only when the contract deliberately supports that. Encapsulating pointer plus length/capacity in structs reduces the number of invariants callers must manage separately.
