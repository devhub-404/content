---
locale: es
status: published
title: "Kotlin"
slug: kotlin
description: "Una referencia rápida orientada a tareas para sintaxis, APIs y workflows cotidianos de Kotlin."
tags:
  - kotlin
  - cheatsheet
  - quick-reference
references:
  - label: "Kotlin Documentation"
    url: https://kotlinlang.org/docs/home.html
  - label: "Configure a Gradle project"
    url: https://kotlinlang.org/docs/gradle-configure-project.html
  - label: "Kotlin Language Specification"
    url: https://kotlinlang.org/spec/introduction.html
---

# Kotlin

Referencia rápida orientada a tareas. Busca en la página y copia el ejemplo más pequeño que corresponda a lo que necesitas.

## Lenguaje y Plataformas

**Qué es Kotlin**

```kotlin
fun main() {
    val name = "Mina"
    println("Hello, $name")
}
```

**Compiler, Gradle y Layout de Proyecto**

```kotlin
plugins {
    kotlin("jvm") version "2.4.20"
}

kotlin {
    jvmToolchain(25)
}
```

**Packages, Imports y Archivos**

```kotlin
package billing.core

import java.time.Instant
import kotlin.math.max

fun now(): Instant = Instant.now()
```

**Source Sets Multiplatform**

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

## Valores, Tipos y Null Safety

**`val`, `var` e Inferencia de Tipo**

```kotlin
val name = "Mina"
var count = 0

count += 1
```

**Tipos Básicos y Números**

```kotlin
val age: Int = 42
val total: Long = 8_000_000_000L
val ratio: Double = 0.75
val enabled: Boolean = true
val letter: Char = 'K'
```

**Strings, Templates y Texto Multilínea**

```kotlin
val name = "Mina"
val message = "Hello, $name!"

val json = """
    {"name":"$name"}
""".trimIndent()
```

**Tipos Nullable, Safe Calls y Elvis**

```kotlin
val nickname: String? = findNickname()

val display = nickname?.trim()?.takeIf { it.isNotEmpty() }
    ?: "anonymous"
```

**Smart Casts y Type Checks**

```kotlin
fun length(value: Any): Int = when (value) {
    is String -> value.length
    is Collection<*> -> value.size
    else -> 0
}
```

## Flujo de Control y Functions

**`if` y `when` como Expressions**

```kotlin
val label = if (ready) "ready" else "waiting"

val result = when (status) {
    Status.READY -> "ready"
    Status.FAILED -> "failed"
    Status.PENDING -> "pending"
}
```

**Loops, Ranges y Progressions**

```kotlin
for (i in 0..<10) {
    println(i)
}

for (value in values) {
    println(value)
}
```

**Functions, Default, Named y Vararg Parameters**

```kotlin
fun connect(
    host: String,
    port: Int = 443,
    secure: Boolean = true
) { /* ... */ }

connect(host = "example.com", secure = false)
```

**Local Functions y Recursión**

```kotlin
fun factorial(n: Int): Long {
    tailrec fun loop(value: Int, acc: Long): Long =
        if (value <= 1) acc else loop(value - 1, acc * value)

    return loop(n, 1)
}
```

## Classes y Modelos de Dominio

**Classes, Constructors y Properties**

```kotlin
class Account(
    val owner: String,
    initialBalance: Long = 0
) {
    var balance: Long = initialBalance
        private set
}
```

**Data Classes y `copy`**

```kotlin
data class User(
    val id: Long,
    val name: String
)

val updated = user.copy(name = "Mina")
```

**Sealed Classes e Interfaces**

```kotlin
sealed interface Result {
    data class Success(val value: String) : Result
    data class Failure(val message: String) : Result
}
```

**Objects y Companion Objects**

```kotlin
object IdGenerator {
    private var next = 0L
    fun nextId(): Long = ++next
}

class User {
    companion object {
        fun guest() = User()
    }
}
```

**Interfaces, Herencia y Delegation**

```kotlin
interface Repository {
    fun save(value: String)
}

class LoggingRepository(
    private val delegate: Repository
) : Repository by delegate
```

**Value Classes y Enums**

```kotlin
@JvmInline
value class UserId(val value: String)

enum class Status { PENDING, READY, FAILED }
```

## Collections y Estilo Funcional

**Lists, Sets, Maps y Mutability**

```kotlin
val names: List<String> = listOf("Ada", "Mina")
val mutable = mutableListOf("Ada")
mutable += "Mina"

val counts = mapOf("ready" to 2)
```

**Transformaciones de Collections**

```kotlin
val activeNames = users
    .filter { it.active }
    .map { it.name }
    .sorted()
```

**Sequences y Pipelines Lazy**

```kotlin
val result = generateSequence(1) { it + 1 }
    .map { it * it }
    .filter { it % 2 == 0 }
    .take(5)
    .toList()
```

**Scope Functions**

```kotlin
val user = User().apply {
    name = "Mina"
    active = true
}

val label = user.let { "${it.name}:${it.active}" }
```

## Higher-order Functions y DSLs

**Function Types y Lambdas**

```kotlin
val transform: (Int) -> Int = { value -> value * 2 }

fun apply(value: Int, fn: (Int) -> Int): Int = fn(value)
```

**`inline`, `noinline` y `crossinline`**

```kotlin
inline fun measure(block: () -> Unit): Long {
    val start = System.nanoTime()
    block()
    return System.nanoTime() - start
}
```

**Extension Functions y Properties**

```kotlin
fun String.isBlankOrDash(): Boolean =
    isBlank() || this == "-"

val String.lastChar: Char
    get() = last()
```

**Lambdas con Receiver y Type-safe Builders**

```kotlin
class HtmlBuilder {
    fun h1(text: String) { /* ... */ }
}

fun html(block: HtmlBuilder.() -> Unit) =
    HtmlBuilder().apply(block)

html {
    h1("Hello")
}
```

## Generics y Type System

**Functions y Classes Genéricas**

```kotlin
class Box<T>(val value: T)

fun <T> first(values: List<T>): T? =
    values.firstOrNull()
```

**Varianza: `in`, `out` y Star Projections**

```kotlin
interface Producer<out T> {
    fun produce(): T
}

interface Consumer<in T> {
    fun consume(value: T)
}
```

**Type Parameters Reified**

```kotlin
inline fun <reified T> Any?.isType(): Boolean = this is T

println(value.isType<String>())
```

**Type Aliases**

```kotlin
typealias UserId = String
typealias Handler = (Request) -> Response
```

## Coroutines y Async

**Suspend Functions y Fundamentos de Coroutines**

```kotlin
suspend fun loadUser(id: Long): User {
    return api.fetchUser(id)
}
```

**Coroutine Scope, `launch` y `async`**

```kotlin
coroutineScope {
    val user = async { loadUser(id) }
    val orders = async { loadOrders(id) }

    render(user.await(), orders.await())
}
```

**Dispatchers y Coroutine Context**

```kotlin
withContext(Dispatchers.IO) {
    Files.readString(path)
}
```

**Cancellation y Timeouts**

```kotlin
withTimeout(5_000) {
    service.load()
}
```

**Flow y Streams Asíncronos**

```kotlin
fun updates(): Flow<Int> = flow {
    for (value in 1..3) {
        delay(100)
        emit(value)
    }
}

updates().collect { println(it) }
```

## Delegation, Metadata y Reflection

**Delegated Properties**

```kotlin
val config by lazy {
    loadConfiguration()
}

var name: String by Delegates.observable("") { _, old, new ->
    println("$old -> $new")
}
```

**Annotations**

```kotlin
@Deprecated("Use newApi instead")
fun oldApi() = Unit

@Target(AnnotationTarget.CLASS)
annotation class Feature(val name: String)
```

**Reflection y `KClass`**

```kotlin
val type = User::class
println(type.simpleName)

for (member in type.members) {
    println(member.name)
}
```

## Interop Java y Boundaries de Plataforma

**Llamando Java desde Kotlin**

```kotlin
val list = java.util.ArrayList<String>()
list.add("Mina")

val instant = java.time.Instant.now()
```

**Platform Types y Nullability Java**

```kotlin
val value = javaApi.findName() // may be String! internally

val safe: String? = value
val required: String = requireNotNull(value)
```

**JVM Annotations y Forma de API**

```kotlin
class Api {
    companion object {
        @JvmStatic
        fun create(): Api = Api()
    }

    @JvmOverloads
    fun connect(host: String, port: Int = 443) { }
}
```

## Testing, Tooling y Producción

**Testing con `kotlin.test` y JUnit**

```kotlin
class CalculatorTest {
    @Test
    fun addsValues() {
        assertEquals(5, Calculator().add(2, 3))
    }
}
```

**Formatting, Static Analysis y Compiler Warnings**

```kotlin
// Typical project checks may include:
// ./gradlew test
// ./gradlew check
// ktlint / detekt when configured
```

**Performance, Allocation y Boxing**

```kotlin
@JvmInline
value class UserId(val value: Long)

fun sum(values: IntArray): Int = values.sum()
```

**Compatibilidad Binaria y Evolución de Libraries**

```kotlin
public interface Clock {
    fun now(): Instant
}
```
