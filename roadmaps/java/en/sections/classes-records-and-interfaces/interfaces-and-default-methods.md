# Interfaces and Default Methods

Interfaces define behavior contracts and support multiple implementation inheritance of interface methods. Default methods can add reusable behavior without forcing every implementation to change immediately, while static and private interface methods support shared implementation details.

```java
interface Clock {
    Instant now();

    default boolean isPast(Instant value) {
        return value.isBefore(now());
    }
}
```

Prefer small interfaces that represent capabilities. Default methods are useful for API evolution but can create conflicts when several parent interfaces provide the same signature, so keep interface inheritance understandable.
