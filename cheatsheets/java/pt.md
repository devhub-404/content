---
locale: pt
status: published
title: "Java"
slug: java
description: "Uma referência rápida orientada a tarefas para sintaxe, APIs e workflows cotidianos de Java."
tags:
  - java
  - cheatsheet
  - quick-reference
references:
  - label: "Java SE 25 API"
    url: https://docs.oracle.com/en/java/javase/25/docs/api/
  - label: "Java Language Changes Summary"
    url: https://docs.oracle.com/en/java/javase/25/language/java-language-changes-summary.html
  - label: "Java Language Specification"
    url: https://docs.oracle.com/javase/specs/jls/se25/html/
---

# Java

Referência rápida orientada a tarefas. Pesquise na página e copie o menor exemplo que corresponde ao que você precisa.

## Linguagem, JVM e Projetos

**O que é Java**

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, Java");
    }
}
```

**JDK, JVM e Ferramentas**

```java
// Common commands:
// javac Main.java
// java Main
// jshell
// javadoc ...
// jar ...
```

**Source Files, Packages e `main`**

```java
package example.app;

public class Main {
    public static void main(String[] args) {
        System.out.println(args.length);
    }
}
```

**Imports e Static Imports**

```java
import java.time.Instant;
import static java.util.Comparator.comparing;

Instant now = Instant.now();
```

**Java Platform Module System**

```java
module example.app {
    requires java.net.http;
    exports example.api;
}
```

## Tipos, Valores e Strings

**Tipos Primitivos**

```java
int count = 42;
long population = 8_000_000_000L;
double ratio = 0.75;
boolean ready = true;
char letter = 'A';
```

**Variáveis, `final` e `var`**

```java
var name = "Mina";
final int maxRetries = 5;

name = name.toUpperCase();
```

**Reference Types, `null` e Identidade**

```java
String first = new String("hello");
String second = new String("hello");

System.out.println(first == second);      // identity
System.out.println(first.equals(second)); // value contract
```

**Strings, Text Blocks e Formatação**

```java
String name = "Mina";
String message = "Hello, " + name;

String json = """
    {"name": "Mina"}
    """;

String formatted = "id=%d".formatted(42);
```

**Arrays e Varargs**

```java
int[] values = {10, 20, 30};

static int sum(int... values) {
    int total = 0;
    for (int value : values) total += value;
    return total;
}
```

**Conversões Numéricas e Parsing**

```java
long wide = 42;
int narrow = Math.toIntExact(wide);

int value = Integer.parseInt("123");
double ratio = Double.parseDouble("0.75");
```

## Fluxo de Controle e Métodos

**`if`, `switch` e Switch Expressions**

```java
String label = switch (status) {
    case READY -> "ready";
    case FAILED -> "failed";
    case PENDING -> "pending";
};
```

**Loops e Enhanced `for`**

```java
for (String name : names) {
    System.out.println(name);
}

for (int i = 0; i < names.size(); i++) {
    System.out.println(i + ": " + names.get(i));
}
```

**Métodos, Overloading e Parâmetros**

```java
static int max(int a, int b) {
    return a >= b ? a : b;
}

static double max(double a, double b) {
    return a >= b ? a : b;
}
```

**Lambdas, Functional Interfaces e Method References**

```java
Predicate<String> nonEmpty = s -> !s.isEmpty();
Function<String, Integer> length = String::length;

names.stream()
    .filter(nonEmpty)
    .map(length)
    .forEach(System.out::println);
```

**Pattern Matching para `instanceof` e `switch`**

```java
static String describe(Object value) {
    return switch (value) {
        case Integer n when n > 0 -> "positive int";
        case String s -> "string: " + s;
        case null -> "null";
        default -> "other";
    };
}
```

## Classes, Records e Interfaces

**Classes, Fields e Constructors**

```java
public final class Account {
    private final String owner;
    private BigDecimal balance = BigDecimal.ZERO;

    public Account(String owner) {
        this.owner = Objects.requireNonNull(owner);
    }
}
```

**Records**

```java
public record User(long id, String name) {
    public User {
        Objects.requireNonNull(name);
    }
}
```

**Sealed Classes e Hierarquias Fechadas**

```java
public sealed interface Result
    permits Success, Failure { }

record Success(String value) implements Result { }
record Failure(String message) implements Result { }
```

**Herança, Abstract Classes e `final`**

```java
abstract class Shape {
    abstract double area();
}

final class Circle extends Shape {
    private final double radius;
    Circle(double radius) { this.radius = radius; }
    @Override double area() { return Math.PI * radius * radius; }
}
```

**Interfaces e Default Methods**

```java
interface Clock {
    Instant now();

    default boolean isPast(Instant value) {
        return value.isBefore(now());
    }
}
```

**Enums**

```java
enum Status {
    PENDING,
    READY,
    FAILED
}

Status status = Status.READY;
```

## Generics e Type System

**Tipos e Métodos Genéricos**

```java
public final class Box<T> {
    private final T value;
    public Box(T value) { this.value = value; }
    public T value() { return value; }
}

static <T> T first(List<T> values) {
    return values.getFirst();
}
```

**Bounds e Wildcards**

```java
static double total(List<? extends Number> values) {
    double sum = 0;
    for (Number value : values) sum += value.doubleValue();
    return sum;
}

static void addDefaults(List<? super Integer> values) {
    values.add(0);
}
```

**Type Erasure e Tipos em Runtime**

```java
List<String> names = new ArrayList<>();
List<Integer> counts = new ArrayList<>();

System.out.println(names.getClass() == counts.getClass());
```

**Annotations e Reflection**

```java
@Deprecated
public void oldApi() { }

Class<?> type = User.class;
for (var method : type.getDeclaredMethods()) {
    System.out.println(method.getName());
}
```

## Collections e Streams

**`List`, `Set` e `Map`**

```java
List<String> names = new ArrayList<>();
names.add("Mina");

Set<String> tags = new HashSet<>();
tags.add("java");

Map<String, Integer> counts = new HashMap<>();
counts.put("ready", 2);
```

**Collections Unmodifiable e Cópias**

```java
List<String> names = List.of("Ada", "Mina");
List<String> snapshot = List.copyOf(source);
```

**`Iterable`, `Iterator` e Percurso**

```java
Iterator<String> it = names.iterator();
while (it.hasNext()) {
    String name = it.next();
    if (name.isBlank()) it.remove();
}
```

**Pipelines de Stream**

```java
List<String> names = users.stream()
    .filter(User::active)
    .map(User::name)
    .sorted()
    .toList();
```

**Collectors, Grouping e Reduction**

```java
Map<String, Long> counts = users.stream()
    .collect(Collectors.groupingBy(
        User::country,
        Collectors.counting()));
```

**Parallel Streams**

```java
long count = values.parallelStream()
    .filter(this::expensiveCheck)
    .count();
```

## Exceptions, Recursos e I/O

**Exceptions Checked e Unchecked**

```java
try {
    Files.readString(path);
} catch (IOException ex) {
    System.err.println(ex.getMessage());
}
```

**Try-with-resources**

```java
try (var reader = Files.newBufferedReader(path)) {
    System.out.println(reader.readLine());
}
```

**NIO Files, Paths e Buffers**

```java
Path path = Path.of("data", "report.txt");
String text = Files.readString(path);
Files.writeString(path, text + "
updated");
```

**Texto, Libraries JSON e HTTP**

```java
HttpClient client = HttpClient.newHttpClient();
HttpRequest request = HttpRequest.newBuilder(uri).GET().build();
HttpResponse<String> response = client.send(
    request,
    HttpResponse.BodyHandlers.ofString());
```

## Concorrência e Virtual Threads

**Threads e Executors**

```java
try (var executor = Executors.newFixedThreadPool(4)) {
    for (Runnable task : tasks) {
        executor.submit(task);
    }
}
```

**Virtual Threads**

```java
try (var executor = Executors.newVirtualThreadPerTaskExecutor()) {
    Future<String> result = executor.submit(() -> loadData());
    System.out.println(result.get());
}
```

**Sincronização, Locks e Atomics**

```java
private final Object lock = new Object();
private int count;

void increment() {
    synchronized (lock) {
        count++;
    }
}
```

**`CompletableFuture`**

```java
CompletableFuture<User> user = loadUser(id);
CompletableFuture<Orders> orders = loadOrders(id);

CompletableFuture<Summary> summary = user.thenCombine(
    orders,
    Summary::new);
```

## Runtime, Memória e Performance

**Garbage Collection e Reachability**

```java
List<byte[]> cache = new ArrayList<>();
cache.add(new byte[1024]);

// Objects are collectible once no live roots reach them.
```

**Boxing, Unboxing e Allocation**

```java
Integer boxed = 42;
int value = boxed;

List<Integer> values = List.of(1, 2, 3);
```

**JIT Compilation e Warmup**

```java
static long work(int value) {
    return (long) value * value;
}
```

## Tooling, Testes e Produção

**Maven, Gradle e Dependencies**

```java
// Maven coordinates example:
// groupId: com.example
// artifactId: billing-core
// version: 1.4.0
```

**Unit Testing com JUnit**

```java
@Test
void add_sumsValues() {
    var calculator = new Calculator();
    assertEquals(5, calculator.add(2, 3));
}
```

**Debugging, Profiling e Flight Recorder**

```java
// Useful JVM diagnostics include:
// jcmd
// jstack
// jmap
// jfr
// jconsole
```

**Releases, LTS e Preview Features**

```java
// Compile a preview experiment only when intended:
// javac --enable-preview --release 25 Example.java
// java --enable-preview Example
```
