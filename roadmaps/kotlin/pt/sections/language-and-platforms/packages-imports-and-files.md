# Packages, Imports e Arquivos

Declarações Kotlin não precisam viver dentro de class. Functions, properties, classes, objects e type aliases podem ser top-level, enquanto packages organizam namespace. Imports podem renomear com `as`.

```kotlin
package billing.core

import java.time.Instant
import kotlin.math.max

fun now(): Instant = Instant.now()
```

Organize packages por responsabilidades estáveis. Top-level functions são idiomáticas para operações stateless; não crie utility classes apenas para imitar static methods Java.
