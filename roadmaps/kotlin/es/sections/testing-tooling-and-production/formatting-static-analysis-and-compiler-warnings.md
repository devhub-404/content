# Formatting, Static Analysis y Compiler Warnings

El compiler Kotlin ofrece diagnostics/IDE inspections y tools como ktlint/detekt añaden formatting/static analysis. Gradle `check` suele agregar verification tasks.

```kotlin
// Typical project checks may include:
// ./gradlew test
// ./gradlew check
// ktlint / detekt when configured
```

Adopta reglas consistentemente en CI. Las suppressions deben documentar por qué el código es seguro o excepcional, no desactivar categorías globalmente.
