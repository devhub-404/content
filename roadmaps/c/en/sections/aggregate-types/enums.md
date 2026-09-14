# Enumerations

An enum introduces named integer constants and an enumeration type. It is useful for discrete states, flags with a separately designed representation, and APIs where symbolic names communicate much more than raw integer values.

```c
enum status {
    STATUS_PENDING,
    STATUS_READY,
    STATUS_FAILED
};

enum status state = STATUS_READY;
```

Do not assume an enum automatically prevents arbitrary integer values from entering through casts, I/O, or corrupted data. Validate external integers before interpreting them as enumeration states. C23 improves enum capabilities, but portable library APIs should still document the exact valid value set.
