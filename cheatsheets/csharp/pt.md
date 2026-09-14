---
locale: pt
status: published
title: "C#"
slug: csharp
description: "Uma referência rápida orientada a tarefas para sintaxe, APIs e workflows cotidianos de C#."
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

Referência rápida orientada a tarefas. Pesquise na página e copie o menor exemplo que corresponde ao que você precisa.

## Linguagem e Projetos .NET

**SDK .NET e Arquivos de Projeto**

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net10.0</TargetFramework>
  </PropertyGroup>
</Project>
```

**Entrada do Programa e Top-level Statements**

```csharp
string name = args.Length > 0 ? args[0] : "world";
Console.WriteLine($"Hello, {name}");
```

**Namespaces e Diretivas `using`**

```csharp
namespace Billing;

using System.Text.Json;

public sealed class InvoiceService
{
    public string Serialize(object value) =>
        JsonSerializer.Serialize(value);
}
```

## Valores e Tipos

**Tipos Built-in e Literals**

```csharp
int count = 42;
long population = 8_000_000_000L;
double ratio = 0.75;
decimal price = 19.99m;
bool ready = true;
char letter = 'A';
```

**Variáveis, `const` e Inferência de Tipo**

```csharp
var message = "hello";
int count = 3;
const int MaxRetries = 5;

message = message.ToUpperInvariant();
```

**Conversões, Casts e Parsing**

```csharp
int count = 42;
long wide = count;           // implicit
int narrow = checked((int)wide);

if (int.TryParse("123", out int value))
{
    Console.WriteLine(value);
}
```

**Strings, Interpolação e Valores Textuais**

```csharp
string name = "Mina";
string message = $"Hello, {name}!";
string raw = """
    line one
    line two
    """;

ReadOnlySpan<char> prefix = message.AsSpan(0, 5);
```

**Tipos Value e Reference Nullable**

```csharp
int? count = null;
string? nickname = null;

string display = nickname ?? "anonymous";
int value = count.GetValueOrDefault();
```

## Fluxo de Controle e Funções

**Condicionais, `switch` e Patterns**

```csharp
string Describe(object value) => value switch
{
    int n when n > 0 => "positive int",
    string { Length: 0 } => "empty string",
    null => "null",
    _ => "other"
};
```

**Loops e Enumeração**

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

**Métodos, Parâmetros e Retornos**

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

**Local Functions e Expression-bodied Members**

```csharp
static int SumPositive(IEnumerable<int> values)
{
    return values.Sum(IsPositive);

    static int IsPositive(int value) =>
        value > 0 ? value : 0;
}
```

**Delegates, Lambdas e Events**

```csharp
Func<int, int> square = x => x * x;

button.Clicked += (_, args) =>
{
    Console.WriteLine(args.Message);
};
```

## Objetos e Abstrações

**Classes, Fields e Properties**

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

**Constructors, `init` e Required Members**

```csharp
public sealed class User
{
    public required string Name { get; init; }
    public string? Email { get; init; }
}

var user = new User { Name = "Mina" };
```

**Records e Dados Value-like**

```csharp
public record User(string Name, string Email);

var a = new User("Mina", "m@example.com");
var b = a with { Email = "new@example.com" };

Console.WriteLine(a == b);
```

**Structs e Value Types**

```csharp
public readonly struct Point
{
    public double X { get; }
    public double Y { get; }

    public Point(double x, double y) =>
        (X, Y) = (x, y);
}
```

**Herança, Members Virtual e Abstract**

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

**Interfaces e Default Members**

```csharp
public interface IClock
{
    DateTimeOffset Now { get; }

    bool IsPast(DateTimeOffset value) =>
        value < Now;
}
```

**Tipos Genéricos e Constraints**

```csharp
public sealed class Repository<T>
    where T : class
{
    private readonly List<T> _items = [];

    public void Add(T item) => _items.Add(item);
}
```

**Extension Methods e Extension Members**

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

## Collections e LINQ

**Arrays, Lists e Collection Expressions**

```csharp
int[] fixedValues = [1, 2, 3];
List<int> values = [1, 2, 3];
values.Add(4);

ReadOnlySpan<int> span = [10, 20, 30];
```

**Dictionary, HashSet e Equality**

```csharp
var counts = new Dictionary<string, int>(
    StringComparer.OrdinalIgnoreCase);

counts["rust"] = 2;

var tags = new HashSet<string> { "csharp", "dotnet" };
```

**`IEnumerable<T>` e `yield`**

```csharp
static IEnumerable<int> EvenNumbers(int max)
{
    for (int i = 0; i <= max; i += 2)
    {
        yield return i;
    }
}
```

**Queries LINQ e Deferred Execution**

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

**Tuples e Deconstruction**

```csharp
static (int Min, int Max) Bounds(IEnumerable<int> values)
{
    return (values.Min(), values.Max());
}

var (min, max) = Bounds([3, 8, 2]);
```

## Erros e Lifetimes de Recursos

**Exceptions, `try`, `catch` e `finally`**

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

**`IDisposable` e `using`**

```csharp
using var stream = File.OpenRead(path);
using var reader = new StreamReader(stream);

string text = reader.ReadToEnd();
```

**`IAsyncDisposable` e `await using`**

```csharp
await using var connection =
    await OpenConnectionAsync(cancellationToken);

await connection.SendAsync(data, cancellationToken);
```

**Exceptions Customizadas e Contratos de Erro**

```csharp
public sealed class InvalidOrderException : Exception
{
    public InvalidOrderException(string message)
        : base(message) { }
}
```

## Async e Concorrência

**`Task`, `async` e `await`**

```csharp
static async Task<string> LoadAsync(
    HttpClient client,
    string url,
    CancellationToken token)
{
    return await client.GetStringAsync(url, token);
}
```

**Composição de Tasks e Concorrência**

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

**Async Streams com `IAsyncEnumerable<T>`**

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

**Threads, Locks e Concurrent Collections**

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

## Runtime e Performance

**Garbage Collection e Lifetimes de Objetos**

```csharp
byte[] buffer = new byte[4096];

// The GC reclaims managed memory once it is unreachable.
UseBuffer(buffer);
```

**`Span<T>`, `Memory<T>` e Código Allocation-aware**

```csharp
static int CountCommas(ReadOnlySpan<char> text)
{
    int count = 0;
    foreach (char c in text)
        if (c == ',') count++;
    return count;
}
```

**`ref struct`, `stackalloc` e By-ref Safety**

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

## Reflection e Metadata

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

**Reflection e Type Metadata**

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

## Standard Library e Dados

**I/O de Arquivos e Streams**

```csharp
await using FileStream stream = File.OpenRead(path);
using var reader = new StreamReader(stream);

string text = await reader.ReadToEndAsync();
```

**Serialização JSON**

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};

string json = JsonSerializer.Serialize(user, options);
User? copy = JsonSerializer.Deserialize<User>(json, options);
```

**`HttpClient` e Requests de Rede**

```csharp
using var request = new HttpRequestMessage(
    HttpMethod.Get,
    new UriBuilder("https", "example.test", -1, "/api/users").Uri);

using HttpResponseMessage response =
    await client.SendAsync(request, cancellationToken);

response.EnsureSuccessStatusCode();
```

**Data, Hora e Time Zones**

```csharp
DateTimeOffset now = DateTimeOffset.UtcNow;
TimeZoneInfo zone = TimeZoneInfo.FindSystemTimeZoneById(
    "America/Los_Angeles");

DateTimeOffset local = TimeZoneInfo.ConvertTime(now, zone);
```

**Expressões Regulares**

```csharp
var match = Regex.Match(
    "user-42",
    @"^user-(\d+)$");

if (match.Success)
    Console.WriteLine(match.Groups[1].Value);
```

## Packages, Testes e Produção

**NuGet e Package References**

```xml
<ItemGroup>
  <PackageReference
      Include="Example.Library"
      Version="4.2.0" />
</ItemGroup>
```

**Unit Testing e Design Testável**

```csharp
[Fact]
public void Add_sums_two_values()
{
    var calculator = new Calculator();

    int result = calculator.Add(2, 3);

    Assert.Equal(5, result);
}
```

**Analyzers, Formatting e Warnings de Nullability**

```xml
<PropertyGroup>
  <Nullable>enable</Nullable>
  <TreatWarningsAsErrors>true</TreatWarningsAsErrors>
</PropertyGroup>
```

**Debugging, Profiling e Diagnostics**

```csharp
using var activity = new Activity("process-order");
activity.Start();

ProcessOrder(order);

activity.Stop();
```
