# Value Classes and Enums

Value classes wrap one value in a distinct type and can often avoid wrapper allocation on supported targets, making them useful for domain-specific IDs and units. Enums model a fixed set of singleton constants with properties and methods.

```kotlin
@JvmInline
value class UserId(val value: String)

enum class Status { PENDING, READY, FAILED }
```

Use value classes for type safety where a full object identity is unnecessary, but understand boxing can still occur at generic, nullable, interface, or platform boundaries. Use enums for simple closed constants and sealed hierarchies when variants need different data.
