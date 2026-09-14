# Source Sets Multiplatform

Kotlin Multiplatform separa código common de source sets específicos. Código common só pode depender de APIs disponíveis aos targets ou libraries multiplatform, enquanto source sets de plataforma usam JVM, JS, Native ou Wasm.

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

Compartilhe domain logic com propósito, não force toda dependency para common code. Filesystem, networking, UI, threads e interop frequentemente precisam implementação específica.
