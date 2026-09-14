# Compiler, Gradle y Layout de Proyecto

Los proyectos Kotlin suelen usar Gradle, aunque el compiler también puede invocarse directamente. El build declara plugin Kotlin, targets, dependencies, compiler options, tests y source sets específicos.

```kotlin
plugins {
    kotlin("jvm") version "2.4.20"
}

kotlin {
    jvmToolchain(25)
}
```

Distingue qué pertenece al compiler, a Gradle y al runtime target. JVM, Android y Multiplatform pueden compartir lenguaje, pero tienen grafos de build y constraints distintos.
