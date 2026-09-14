# Compiler, Gradle e Layout de Projeto

Projetos Kotlin normalmente usam Gradle, embora o compiler possa ser invocado diretamente. O build declara plugin Kotlin, targets, dependencies, compiler options, testes e source sets específicos.

```kotlin
plugins {
    kotlin("jvm") version "2.4.20"
}

kotlin {
    jvmToolchain(25)
}
```

Entenda o que pertence ao compiler, ao Gradle e ao runtime target. JVM, Android e Multiplatform podem compartilhar linguagem, mas têm grafos de build e constraints diferentes.
