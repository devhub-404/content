# Compiler, Gradle, and Project Layout

Kotlin projects are usually built with Gradle, although the compiler can also be invoked directly. The build declares the Kotlin plugin, target platforms, dependencies, compiler options, test setup, and platform-specific source sets.

```kotlin
plugins {
    kotlin("jvm") version "2.4.20"
}

kotlin {
    jvmToolchain(25)
}
```

Understand what comes from the Kotlin compiler versus Gradle and the target runtime. A JVM project, Android app, and multiplatform library may use the same language syntax while having different build graphs, standard-library variants, and deployment constraints.
