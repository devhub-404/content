# Formatting, Static Analysis e Compiler Warnings

Compiler Kotlin fornece diagnostics/IDE inspections e tools como ktlint/detekt adicionam formatting/static analysis. Gradle `check` normalmente agrega verification tasks.

```kotlin
// Typical project checks may include:
// ./gradlew test
// ./gradlew check
// ktlint / detekt when configured
```

Adote regras consistentemente em CI. Suppressions devem documentar por que o código é seguro ou excepcional, não desligar categorias globalmente.
