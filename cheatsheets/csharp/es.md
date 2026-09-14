---
locale: es
status: published
title: "C#"
slug: csharp
description: "Una referencia rápida orientada a tareas para sintaxis, APIs y workflows cotidianos de C#."
tags:
  - csharp
  - cheatsheet
  - quick-reference
references:
  - label: "Microsoft Learn: C# Guide"
    url: https://learn.microsoft.com/en-us/dotnet/csharp/
  - label: ".NET documentation"
    url: https://learn.microsoft.com/en-us/dotnet/
  - label: "C# Language Reference"
    url: https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/
---

# C#

Referencia rápida orientada a tareas. Busca en la página y copia el ejemplo más pequeño que corresponda a lo que necesitas.

## Lenguaje y Proyectos .NET

**SDK .NET y Archivos de Proyecto**

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net10.0</TargetFramework>
  </PropertyGroup>
</Project>
```

**Entrada del Programa y Top-level Statements**

```csharp
string name = args.Length > 0 ? args[0] : "world";
Console.WriteLine($"Hello, {name}");
```

**Namespaces y Directivas `using`**

```csharp
namespace Billing;

using System.Text.Json;

public sealed class InvoiceService
{
    public string Serialize(object value) =>
        JsonSerializer.Serialize(value);
}
```

## Valores y Tipos

**Tipos Built-in y Literals**

```csharp
int count = 42;
long population = 8_000_000_000L;
double ratio = 0.75;
decimal price = 19.99m;
bool ready = true;
char letter = 'A';
```

**Variables, `const` e Inferencia de Tipo**

```csharp
var message = "hello";
int count = 3;
const int MaxRetries = 5;

message = message.ToUpperInvariant();
```

**Conversiones, Casts y Parsing**

```csharp
int count = 42;
long wide = count;           // implicit
int narrow = checked((int)wide);

if (int.TryParse("123", out int value))
{
    Console.WriteLine(value);
}
```

**Strings, Interpolación y Valores Textuales**

```csharp
string name = "Mina";
string message = $"Hello, {name}!";
string raw = """
    line one
    line two
    """;

ReadOnlySpan<char> prefix = message.AsSpan(0, 5);
```

**Tipos Value y Reference Nullable**

```csharp
int? count = null;
string? nickname = null;

string display = nickname ?? "anonymous";
int value = count.GetValueOrDefault();
```

## Flujo de Control y Funciones

**Condicionales, `switch` y Patterns**

```csharp
string Describe(object value) => value switch
{
    int n when n > 0 => "positive int",
    string { Length: 0 } => "empty string",
    null => "null",
    _ => "other"
};
```

**Loops y Enumeración**

```csharp
foreach (var item in items)
{
    Console.WriteLine(item);
}

for (int i = 0; i < items.Count; i++)
{
    Console.WriteLine($"{i}: {items[i]}");
}
```

**Métodos, Parámetros y Retornos**

```csharp
static bool TryDivide(
    double a,
    double b,
    out double result)
{
    if (b == 0)
    {
        result = default;
        return false;
    }

    result = a / b;
    return true;
}
```

**Local Functions y Expression-bodied Members**

```csharp
static int SumPositive(IEnumerable<int> values)
{
    return values.Sum(IsPositive);

    static int IsPositive(int value) =>
        value > 0 ? value : 0;
}
```

**Delegates, Lambdas y Events**

```csharp
Func<int, int> square = x => x * x;

button.Clicked += (_, args) =>
{
    Console.WriteLine(args.Message);
};
```

## Objetos y Abstracciones

**Classes, Fields y Properties**

```csharp
public sealed class Account
{
    private decimal _balance;

    public string Owner { get; }
    public decimal Balance => _balance;

    public Account(string owner)
    {
        Owner = owner;
    }
}
```

**Constructors, `init` y Required Members**

```csharp
public sealed class User
{
    public required string Name { get; init; }
    public string? Email { get; init; }
}

var user = new User { Name = "Mina" };
```

**Records y Datos Value-like**

```csharp
public record User(string Name, string Email);

var a = new User("Mina", "m@example.com");
var b = a with { Email = "new@example.com" };

Console.WriteLine(a == b);
```

**Structs y Value Types**

```csharp
public readonly struct Point
{
    public double X { get; }
    public double Y { get; }

    public Point(double x, double y) =>
        (X, Y) = (x, y);
}
```

**Herencia, Members Virtual y Abstract**

```csharp
public abstract class Shape
{
    public abstract double Area { get; }
}

public sealed class Circle(double radius) : Shape
{
    public override double Area => Math.PI * radius * radius;
}
```

**Interfaces y Default Members**

```csharp
public interface IClock
{
    DateTimeOffset Now { get; }

    bool IsPast(DateTimeOffset value) =>
        value < Now;
}
```

**Tipos Genéricos y Constraints**

```csharp
public sealed class Repository<T>
    where T : class
{
    private readonly List<T> _items = [];

    public void Add(T item) => _items.Add(item);
}
```

**Extension Methods y Extension Members**

```csharp
public static class TextExtensions
{
    public static bool IsBlank(this string? value) =>
        string.IsNullOrWhiteSpace(value);
}

if (input.IsBlank())
{
    Console.WriteLine("empty");
}
```

## Collections y LINQ

**Arrays, Lists y Collection Expressions**

```csharp
int[] fixedValues = [1, 2, 3];
List<int> values = [1, 2, 3];
values.Add(4);

ReadOnlySpan<int> span = [10, 20, 30];
```

**Dictionary, HashSet y Equality**

```csharp
var counts = new Dictionary<string, int>(
    StringComparer.OrdinalIgnoreCase);

counts["rust"] = 2;

var tags = new HashSet<string> { "csharp", "dotnet" };
```

**`IEnumerable<T>` y `yield`**

```csharp
static IEnumerable<int> EvenNumbers(int max)
{
    for (int i = 0; i <= max; i += 2)
    {
        yield return i;
    }
}
```

**Queries LINQ y Deferred Execution**

```csharp
var activeNames = users
    .Where(user => user.IsActive)
    .OrderBy(user => user.Name)
    .Select(user => user.Name);

foreach (string name in activeNames)
{
    Console.WriteLine(name);
}
```

**Tuples y Deconstruction**

```csharp
static (int Min, int Max) Bounds(IEnumerable<int> values)
{
    return (values.Min(), values.Max());
}

var (min, max) = Bounds([3, 8, 2]);
```

## Errores y Lifetimes de Recursos

**Exceptions, `try`, `catch` y `finally`**

```csharp
try
{
    Process(path);
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine(ex.Message);
}
finally
{
    Console.WriteLine("finished");
}
```

**`IDisposable` y `using`**

```csharp
using var stream = File.OpenRead(path);
using var reader = new StreamReader(stream);

string text = reader.ReadToEnd();
```

**`IAsyncDisposable` y `await using`**

```csharp
await using var connection =
    await OpenConnectionAsync(cancellationToken);

await connection.SendAsync(data, cancellationToken);
```

**Exceptions Personalizadas y Contratos de Error**

```csharp
public sealed class InvalidOrderException : Exception
{
    public InvalidOrderException(string message)
        : base(message) { }
}
```

## Async y Concurrencia

**`Task`, `async` y `await`**

```csharp
static async Task<string> LoadAsync(
    HttpClient client,
    string url,
    CancellationToken token)
{
    return await client.GetStringAsync(url, token);
}
```

**Composición de Tasks y Concurrencia**

```csharp
Task<User> userTask = LoadUserAsync(id);
Task<Order[]> ordersTask = LoadOrdersAsync(id);

await Task.WhenAll(userTask, ordersTask);

User user = await userTask;
Order[] orders = await ordersTask;
```

**Cancellation Tokens**

```csharp
using var timeout = new CancellationTokenSource(
    TimeSpan.FromSeconds(5));

await service.RunAsync(timeout.Token);
```

**Async Streams con `IAsyncEnumerable<T>`**

```csharp
static async IAsyncEnumerable<int> CountAsync()
{
    for (int i = 0; i < 3; i++)
    {
        await Task.Delay(100);
        yield return i;
    }
}

await foreach (int value in CountAsync())
    Console.WriteLine(value);
```

**Threads, Locks y Concurrent Collections**

```csharp
private readonly object _gate = new();
private int _count;

void Increment()
{
    lock (_gate)
    {
        _count++;
    }
}
```

## Runtime y Performance

**Garbage Collection y Lifetimes de Objetos**

```csharp
byte[] buffer = new byte[4096];

// The GC reclaims managed memory once it is unreachable.
UseBuffer(buffer);
```

**`Span<T>`, `Memory<T>` y Código Allocation-aware**

```csharp
static int CountCommas(ReadOnlySpan<char> text)
{
    int count = 0;
    foreach (char c in text)
        if (c == ',') count++;
    return count;
}
```

**`ref struct`, `stackalloc` y By-ref Safety**

```csharp
Span<int> values = stackalloc int[4];
values[0] = 10;

ref int first = ref values[0];
first = 20;
```

**Código Unsafe e Interop Nativo**

```csharp
unsafe
{
    int value = 42;
    int* pointer = &value;
    Console.WriteLine(*pointer);
}
```

## Reflection y Metadata

**Attributes**

```csharp
[Obsolete("Use NewApi instead")]
public void OldApi() { }

[AttributeUsage(AttributeTargets.Class)]
public sealed class FeatureAttribute : Attribute
{
    public FeatureAttribute(string name) => Name = name;
    public string Name { get; }
}
```

**Reflection y Type Metadata**

```csharp
Type type = typeof(User);

foreach (PropertyInfo property in type.GetProperties())
{
    Console.WriteLine(property.Name);
}
```

**Expression Trees**

```csharp
Expression<Func<User, bool>> filter =
    user => user.IsActive && user.Age >= 18;

Console.WriteLine(filter);
```

## Standard Library y Datos

**I/O de Archivos y Streams**

```csharp
await using FileStream stream = File.OpenRead(path);
using var reader = new StreamReader(stream);

string text = await reader.ReadToEndAsync();
```

**Serialización JSON**

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};

string json = JsonSerializer.Serialize(user, options);
User? copy = JsonSerializer.Deserialize<User>(json, options);
```

**`HttpClient` y Requests de Red**

```csharp
using var request = new HttpRequestMessage(
    HttpMethod.Get,
    new UriBuilder("https", "example.test", -1, "/api/users").Uri);

using HttpResponseMessage response =
    await client.SendAsync(request, cancellationToken);

response.EnsureSuccessStatusCode();
```

**Fecha, Hora y Time Zones**

```csharp
DateTimeOffset now = DateTimeOffset.UtcNow;
TimeZoneInfo zone = TimeZoneInfo.FindSystemTimeZoneById(
    "America/Los_Angeles");

DateTimeOffset local = TimeZoneInfo.ConvertTime(now, zone);
```

**Expresiones Regulares**

```csharp
var match = Regex.Match(
    "user-42",
    @"^user-(\d+)$");

if (match.Success)
    Console.WriteLine(match.Groups[1].Value);
```

## Packages, Testing y Producción

**NuGet y Package References**

```xml
<ItemGroup>
  <PackageReference
      Include="Example.Library"
      Version="4.2.0" />
</ItemGroup>
```

**Unit Testing y Diseño Testable**

```csharp
[Fact]
public void Add_sums_two_values()
{
    var calculator = new Calculator();

    int result = calculator.Add(2, 3);

    Assert.Equal(5, result);
}
```

**Analyzers, Formatting y Warnings de Nullability**

```xml
<PropertyGroup>
  <Nullable>enable</Nullable>
  <TreatWarningsAsErrors>true</TreatWarningsAsErrors>
</PropertyGroup>
```

**Debugging, Profiling y Diagnostics**

```csharp
using var activity = new Activity("process-order");
activity.Start();

ProcessOrder(order);

activity.Stop();
```
