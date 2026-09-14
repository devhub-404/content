# Formatting, Static Analysis, and Compiler Warnings

The Kotlin compiler provides diagnostics and IDE inspections, while ecosystem tools such as ktlint and detekt add formatting and static-analysis policies. Gradle `check` commonly aggregates tests and verification tasks.

```kotlin
// Typical project checks may include:
// ./gradlew test
// ./gradlew check
// ktlint / detekt when configured
```

Adopt style and analysis rules consistently in CI rather than arguing per file. Treat suppressions as local documentation: explain why the code is safe or intentionally exceptional instead of disabling broad categories globally.
