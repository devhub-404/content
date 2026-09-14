# Binary Compatibility and Library Evolution

Published Kotlin libraries have source, binary, metadata, and platform-specific compatibility concerns. Small-looking changes to default parameters, inline functions, sealed hierarchies, interfaces, or JVM signatures can affect consumers differently from ordinary application refactors.

```kotlin
public interface Clock {
    fun now(): Instant
}
```

Keep public APIs small, version libraries deliberately, and test representative consumers when compatibility matters. For multiplatform libraries, compatibility also spans target availability and metadata consumed by other Kotlin compilers.
