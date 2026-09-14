# Bit-fields, Alignment, and Layout

Bit-fields let struct members occupy a specified number of bits, but their allocation order, packing details, and some base-type behavior are implementation-defined. They can be useful for implementation-specific hardware interfaces but are a poor default for portable wire or file formats.

```c
struct flags {
    unsigned ready : 1;
    unsigned error : 1;
    unsigned mode  : 2;
};
```

For external binary formats, encode and decode fields explicitly with integer masks and shifts and define byte order. Use `alignof`, `alignas`, `sizeof`, and static assertions when layout constraints matter, and verify assumptions on every supported ABI.
