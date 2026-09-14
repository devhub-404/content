---
locale: en
status: published
title: "Kotlin"
slug: kotlin
description: "A task-oriented quick reference for everyday Kotlin syntax, APIs, and workflows."
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

Task-oriented quick reference. Search the page and copy the smallest example that matches what you need.

## Language & Platforms

**What Kotlin Is**

```kotlin
fun main() {
    val name = "Mina"
    println("Hello, $name")
}
```

**Compiler, Gradle, and Project Layout**

```kotlin
plugins {
    kotlin("jvm") version "2.4.20"
}

kotlin {
    jvmToolchain(25)
}
```

**Packages, Imports, and Files**

```kotlin
package billing.core

import java.time.Instant
import kotlin.math.max

fun now(): Instant = Instant.now()
```

**Multiplatform Source Sets**

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

## Values, Types & Null Safety

**`val`, `var`, and Type Inference**

```kotlin
val name = "Mina"
var count = 0

count += 1
```

**Basic Types and Numbers**

```kotlin
val age: Int = 42
val total: Long = 8_000_000_000L
val ratio: Double = 0.75
val enabled: Boolean = true
val letter: Char = 'K'
```

**Strings, Templates, and Multiline Text**

```kotlin
val name = "Mina"
val message = "Hello, $name!"

val json = """
    {"name":"$name"}
""".trimIndent()
```

**Nullable Types, Safe Calls, and Elvis**

```kotlin
val nickname: String? = findNickname()

val display = nickname?.trim()?.takeIf { it.isNotEmpty() }
    ?: "anonymous"
```

**Smart Casts and Type Checks**

```kotlin
fun length(value: Any): Int = when (value) {
    is String -> value.length
    is Collection<*> -> value.size
    else -> 0
}
```

## Control Flow & Functions

**`if` and `when` as Expressions**

```kotlin
val label = if (ready) "ready" else "waiting"

val result = when (status) {
    Status.READY -> "ready"
    Status.FAILED -> "failed"
    Status.PENDING -> "pending"
}
```

**Loops, Ranges, and Progressions**

```kotlin
for (i in 0..<10) {
    println(i)
}

for (value in values) {
    println(value)
}
```

**Functions, Default, Named, and Vararg Parameters**

```kotlin
fun connect(
    host: String,
    port: Int = 443,
    secure: Boolean = true
) { /* ... */ }

connect(host = "example.com", secure = false)
```

**Local Functions and Recursion**

```kotlin
fun factorial(n: Int): Long {
    tailrec fun loop(value: Int, acc: Long): Long =
        if (value <= 1) acc else loop(value - 1, acc * value)

    return loop(n, 1)
}
```

## Classes & Domain Models

**Classes, Constructors, and Properties**

```kotlin
class Account(
    val owner: String,
    initialBalance: Long = 0
) {
    var balance: Long = initialBalance
        private set
}
```

**Data Classes and `copy`**

```kotlin
data class User(
    val id: Long,
    val name: String
)

val updated = user.copy(name = "Mina")
```

**Sealed Classes and Interfaces**

```kotlin
sealed interface Result {
    data class Success(val value: String) : Result
    data class Failure(val message: String) : Result
}
```

**Objects and Companion Objects**

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

**Interfaces, Inheritance, and Delegation**

```kotlin
interface Repository {
    fun save(value: String)
}

class LoggingRepository(
    private val delegate: Repository
) : Repository by delegate
```

**Value Classes and Enums**

```kotlin
@JvmInline
value class UserId(val value: String)

enum class Status { PENDING, READY, FAILED }
```

## Collections & Functional Style

**Lists, Sets, Maps, and Mutability**

```kotlin
val names: List<String> = listOf("Ada", "Mina")
val mutable = mutableListOf("Ada")
mutable += "Mina"

val counts = mapOf("ready" to 2)
```

**Collection Transformations**

```kotlin
val activeNames = users
    .filter { it.active }
    .map { it.name }
    .sorted()
```

**Sequences and Lazy Pipelines**

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

## Higher-order Functions & DSLs

**Function Types and Lambdas**

```kotlin
val transform: (Int) -> Int = { value -> value * 2 }

fun apply(value: Int, fn: (Int) -> Int): Int = fn(value)
```

**`inline`, `noinline`, and `crossinline`**

```kotlin
inline fun measure(block: () -> Unit): Long {
    val start = System.nanoTime()
    block()
    return System.nanoTime() - start
}
```

**Extension Functions and Properties**

```kotlin
fun String.isBlankOrDash(): Boolean =
    isBlank() || this == "-"

val String.lastChar: Char
    get() = last()
```

**Lambdas with Receiver and Type-safe Builders**

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

## Generics & Type System

**Generic Functions and Classes**

```kotlin
class Box<T>(val value: T)

fun <T> first(values: List<T>): T? =
    values.firstOrNull()
```

**Variance: `in`, `out`, and Star Projections**

```kotlin
interface Producer<out T> {
    fun produce(): T
}

interface Consumer<in T> {
    fun consume(value: T)
}
```

**Reified Type Parameters**

```kotlin
inline fun <reified T> Any?.isType(): Boolean = this is T

println(value.isType<String>())
```

**Type Aliases**

```kotlin
typealias UserId = String
typealias Handler = (Request) -> Response
```

## Coroutines & Async

**Suspend Functions and Coroutine Basics**

```kotlin
suspend fun loadUser(id: Long): User {
    return api.fetchUser(id)
}
```

**Coroutine Scope, `launch`, and `async`**

```kotlin
coroutineScope {
    val user = async { loadUser(id) }
    val orders = async { loadOrders(id) }

    render(user.await(), orders.await())
}
```

**Dispatchers and Coroutine Context**

```kotlin
withContext(Dispatchers.IO) {
    Files.readString(path)
}
```

**Cancellation and Timeouts**

```kotlin
withTimeout(5_000) {
    service.load()
}
```

**Flow and Asynchronous Streams**

```kotlin
fun updates(): Flow<Int> = flow {
    for (value in 1..3) {
        delay(100)
        emit(value)
    }
}

updates().collect { println(it) }
```

## Delegation, Metadata & Reflection

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

**Reflection and `KClass`**

```kotlin
val type = User::class
println(type.simpleName)

for (member in type.members) {
    println(member.name)
}
```

## Java Interop & Platform Boundaries

**Calling Java from Kotlin**

```kotlin
val list = java.util.ArrayList<String>()
list.add("Mina")

val instant = java.time.Instant.now()
```

**Platform Types and Java Nullability**

```kotlin
val value = javaApi.findName() // may be String! internally

val safe: String? = value
val required: String = requireNotNull(value)
```

**JVM Annotations and API Shaping**

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

## Testing, Tooling & Production

**Testing with `kotlin.test` and JUnit**

```kotlin
class CalculatorTest {
    @Test
    fun addsValues() {
        assertEquals(5, Calculator().add(2, 3))
    }
}
```

**Formatting, Static Analysis, and Compiler Warnings**

```kotlin
// Typical project checks may include:
// ./gradlew test
// ./gradlew check
// ktlint / detekt when configured
```

**Performance, Allocation, and Boxing**

```kotlin
@JvmInline
value class UserId(val value: Long)

fun sum(values: IntArray): Int = values.sum()
```

**Binary Compatibility and Library Evolution**

```kotlin
public interface Clock {
    fun now(): Instant
}
```
