# Source Sets Multiplatform

Kotlin Multiplatform separa código common de source sets específicos. El código common solo puede depender de APIs disponibles en sus targets o libraries multiplatform, mientras source sets de plataforma usan JVM, JS, Native o Wasm.

```kotlin
kotlin {
    jvm()
    js()

    sourceSets {
        commonMain.dependencies {
            implementation(kotlin("stdlib"))
        }
    }
}
```

Comparte domain logic con propósito, no fuerces cada dependency a common code. Filesystem, networking, UI, threads e interop suelen necesitar implementación específica.
