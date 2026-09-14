# Packages, Imports y Archivos

Las declarations Kotlin no necesitan vivir dentro de una class. Functions, properties, classes, objects y type aliases pueden ser top-level, mientras packages organizan namespace. Los imports pueden renombrar con `as`.

```kotlin
package billing.core

import java.time.Instant
import kotlin.math.max

fun now(): Instant = Instant.now()
```

Organiza packages por responsabilidades estables. Las top-level functions son idiomáticas para operaciones stateless; no crees utility classes solo para imitar static methods de Java.
