# Packages, Imports, and Files

Kotlin declarations do not need to live inside a class. Functions, properties, classes, objects, and type aliases can be declared at file level, while packages provide namespace organization across files. Imports can rename declarations with `as`.

```kotlin
package billing.core

import java.time.Instant
import kotlin.math.max

fun now(): Instant = Instant.now()
```

Organize packages around stable responsibilities instead of mirroring every directory. Top-level functions are idiomatic for stateless operations; do not create utility classes merely to imitate Java static methods.
