# Multiplatform Source Sets

Kotlin Multiplatform separates common code from platform-specific source sets. Common code can depend only on APIs available to its targets or on multiplatform libraries, while platform source sets can use JVM, JS, Native, or Wasm facilities.

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

Start with a clear reason to share domain logic rather than forcing every dependency into common code. Platform boundaries are real: file systems, networking stacks, UI frameworks, threading, and native interoperability often need target-specific implementations.
