---
locale: pt
status: published
title: "Kotlin"
slug: kotlin
description: "Uma referência rápida orientada a tarefas para sintaxe, APIs e workflows cotidianos de Kotlin."
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

Referência rápida orientada a tarefas. Pesquise na página e copie o menor exemplo que corresponde ao que você precisa.

## Linguagem e Plataformas

**O que é Kotlin**

```kotlin
fun main() {
    val name = "Mina"
    println("Hello, $name")
}
```

**Compiler, Gradle e Layout de Projeto**

```kotlin
plugins {
    kotlin("jvm") version "2.4.20"
}

kotlin {
    jvmToolchain(25)
}
```

**Packages, Imports e Arquivos**

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

## Valores, Tipos e Null Safety

**`val`, `var` e Inferência de Tipo**

```kotlin
val name = "Mina"
var count = 0

count += 1
```

**Tipos Básicos e Números**

```kotlin
val age: Int = 42
val total: Long = 8_000_000_000L
val ratio: Double = 0.75
val enabled: Boolean = true
val letter: Char = 'K'
```

**Strings, Templates e Texto Multilinha**

```kotlin
val name = "Mina"
val message = "Hello, $name!"

val json = """
    {"name":"$name"}
""".trimIndent()
```

**Tipos Nullable, Safe Calls e Elvis**

```kotlin
val nickname: String? = findNickname()

val display = nickname?.trim()?.takeIf { it.isNotEmpty() }
    ?: "anonymous"
```

**Smart Casts e Type Checks**

```kotlin
fun length(value: Any): Int = when (value) {
    is String -> value.length
    is Collection<*> -> value.size
    else -> 0
}
```

## Fluxo de Controle e Funções

**`if` e `when` como Expressions**

```kotlin
val label = if (ready) "ready" else "waiting"

val result = when (status) {
    Status.READY -> "ready"
    Status.FAILED -> "failed"
    Status.PENDING -> "pending"
}
```

**Loops, Ranges e Progressions**

```kotlin
for (i in 0..<10) {
    println(i)
}

for (value in values) {
    println(value)
}
```

**Functions, Default, Named e Vararg Parameters**

```kotlin
fun connect(
    host: String,
    port: Int = 443,
    secure: Boolean = true
) { /* ... */ }

connect(host = "example.com", secure = false)
```

**Local Functions e Recursão**

```kotlin
fun factorial(n: Int): Long {
    tailrec fun loop(value: Int, acc: Long): Long =
        if (value <= 1) acc else loop(value - 1, acc * value)

    return loop(n, 1)
}
```

## Classes e Modelos de Domínio

**Classes, Constructors e Properties**

```kotlin
class Account(
    val owner: String,
    initialBalance: Long = 0
) {
    var balance: Long = initialBalance
        private set
}
```

**Data Classes e `copy`**

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

**Objects e Companion Objects**

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

**Interfaces, Herança e Delegation**

```kotlin
interface Repository {
    fun save(value: String)
}

class LoggingRepository(
    private val delegate: Repository
) : Repository by delegate
```

**Value Classes e Enums**

```kotlin
@JvmInline
value class UserId(val value: String)

enum class Status { PENDING, READY, FAILED }
```

## Collections e Estilo Funcional

**Lists, Sets, Maps e Mutability**

```kotlin
val names: List<String> = listOf("Ada", "Mina")
val mutable = mutableListOf("Ada")
mutable += "Mina"

val counts = mapOf("ready" to 2)
```

**Transformações de Collections**

```kotlin
val activeNames = users
    .filter { it.active }
    .map { it.name }
    .sorted()
```

**Sequences e Pipelines Lazy**

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

## Higher-order Functions e DSLs

**Function Types e Lambdas**

```kotlin
val transform: (Int) -> Int = { value -> value * 2 }

fun apply(value: Int, fn: (Int) -> Int): Int = fn(value)
```

**`inline`, `noinline` e `crossinline`**

```kotlin
inline fun measure(block: () -> Unit): Long {
    val start = System.nanoTime()
    block()
    return System.nanoTime() - start
}
```

**Extension Functions e Properties**

```kotlin
fun String.isBlankOrDash(): Boolean =
    isBlank() || this == "-"

val String.lastChar: Char
    get() = last()
```

**Lambdas com Receiver e Type-safe Builders**

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

## Generics e Type System

**Functions e Classes Genéricas**

```kotlin
class Box<T>(val value: T)

fun <T> first(values: List<T>): T? =
    values.firstOrNull()
```

**Variância: `in`, `out` e Star Projections**

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

## Coroutines e Async

**Suspend Functions e Fundamentos de Coroutines**

```kotlin
suspend fun loadUser(id: Long): User {
    return api.fetchUser(id)
}
```

**Coroutine Scope, `launch` e `async`**

```kotlin
coroutineScope {
    val user = async { loadUser(id) }
    val orders = async { loadOrders(id) }

    render(user.await(), orders.await())
}
```

**Dispatchers e Coroutine Context**

```kotlin
withContext(Dispatchers.IO) {
    Files.readString(path)
}
```

**Cancellation e Timeouts**

```kotlin
withTimeout(5_000) {
    service.load()
}
```

**Flow e Streams Assíncronos**

```kotlin
fun updates(): Flow<Int> = flow {
    for (value in 1..3) {
        delay(100)
        emit(value)
    }
}

updates().collect { println(it) }
```

## Delegation, Metadata e Reflection

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

**Reflection e `KClass`**

```kotlin
val type = User::class
println(type.simpleName)

for (member in type.members) {
    println(member.name)
}
```

## Interop Java e Boundaries de Plataforma

**Chamando Java a partir de Kotlin**

```kotlin
val list = java.util.ArrayList<String>()
list.add("Mina")

val instant = java.time.Instant.now()
```

**Platform Types e Nullability Java**

```kotlin
val value = javaApi.findName() // may be String! internally

val safe: String? = value
val required: String = requireNotNull(value)
```

**JVM Annotations e Formato de API**

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

## Testes, Tooling e Produção

**Testes com `kotlin.test` e JUnit**

```kotlin
class CalculatorTest {
    @Test
    fun addsValues() {
        assertEquals(5, Calculator().add(2, 3))
    }
}
```

**Formatting, Static Analysis e Compiler Warnings**

```kotlin
// Typical project checks may include:
// ./gradlew test
// ./gradlew check
// ktlint / detekt when configured
```

**Performance, Allocation e Boxing**

```kotlin
@JvmInline
value class UserId(val value: Long)

fun sum(values: IntArray): Int = values.sum()
```

**Compatibilidade Binária e Evolução de Libraries**

```kotlin
public interface Clock {
    fun now(): Instant
}
```
