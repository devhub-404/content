# Structures

A `struct` groups named members into one object type. Members are laid out in declaration order with possible padding for alignment. Designated initializers make initialization clearer and less dependent on remembering positional order.

```c
struct user {
    int id;
    char name[32];
};

struct user u = {
    .id = 42,
    .name = "Mina",
};
```

Copying a struct value copies its members as a value operation, but pointers inside the struct still refer to the same pointed-to objects. Do not serialize a struct by dumping its raw bytes unless a protocol explicitly defines that representation; padding, endianness, and type representation can vary.
