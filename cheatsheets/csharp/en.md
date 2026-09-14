---
locale: en
status: published
title: "C#"
slug: csharp
description: "A task-oriented quick reference for everyday C# syntax, APIs, and workflows."
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

Task-oriented quick reference. Search the page and copy the smallest example that matches what you need.

## Language & .NET Projects

**.NET SDK and Project Files**

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net10.0</TargetFramework>
  </PropertyGroup>
</Project>
```

**Program Entry and Top-level Statements**

```csharp
string name = args.Length > 0 ? args[0] : "world";
Console.WriteLine($"Hello, {name}");
```

**Namespaces and `using` Directives**

```csharp
namespace Billing;

using System.Text.Json;

public sealed class InvoiceService
{
    public string Serialize(object value) =>
        JsonSerializer.Serialize(value);
}
```

## Values & Types

**Built-in Types and Literals**

```csharp
int count = 42;
long population = 8_000_000_000L;
double ratio = 0.75;
decimal price = 19.99m;
bool ready = true;
char letter = 'A';
```

**Variables, `const`, and Type Inference**

```csharp
var message = "hello";
int count = 3;
const int MaxRetries = 5;

message = message.ToUpperInvariant();
```

**Conversions, Casts, and Parsing**

```csharp
int count = 42;
long wide = count;           // implicit
int narrow = checked((int)wide);

if (int.TryParse("123", out int value))
{
    Console.WriteLine(value);
}
```

**Strings, Interpolation, and Text Values**

```csharp
string name = "Mina";
string message = $"Hello, {name}!";
string raw = """
    line one
    line two
    """;

ReadOnlySpan<char> prefix = message.AsSpan(0, 5);
```

**Nullable Value and Reference Types**

```csharp
int? count = null;
string? nickname = null;

string display = nickname ?? "anonymous";
int value = count.GetValueOrDefault();
```

## Control Flow & Functions

**Conditionals, `switch`, and Patterns**

```csharp
string Describe(object value) => value switch
{
    int n when n > 0 => "positive int",
    string { Length: 0 } => "empty string",
    null => "null",
    _ => "other"
};
```

**Loops and Enumeration**

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

**Methods, Parameters, and Return Values**

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

**Local Functions and Expression-bodied Members**

```csharp
static int SumPositive(IEnumerable<int> values)
{
    return values.Sum(IsPositive);

    static int IsPositive(int value) =>
        value > 0 ? value : 0;
}
```

**Delegates, Lambdas, and Events**

```csharp
Func<int, int> square = x => x * x;

button.Clicked += (_, args) =>
{
    Console.WriteLine(args.Message);
};
```

## Objects & Abstractions

**Classes, Fields, and Properties**

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

**Constructors, `init`, and Required Members**

```csharp
public sealed class User
{
    public required string Name { get; init; }
    public string? Email { get; init; }
}

var user = new User { Name = "Mina" };
```

**Records and Value-like Data**

```csharp
public record User(string Name, string Email);

var a = new User("Mina", "m@example.com");
var b = a with { Email = "new@example.com" };

Console.WriteLine(a == b);
```

**Structs and Value Types**

```csharp
public readonly struct Point
{
    public double X { get; }
    public double Y { get; }

    public Point(double x, double y) =>
        (X, Y) = (x, y);
}
```

**Inheritance, Virtual, and Abstract Members**

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

**Interfaces and Default Members**

```csharp
public interface IClock
{
    DateTimeOffset Now { get; }

    bool IsPast(DateTimeOffset value) =>
        value < Now;
}
```

**Generic Types and Constraints**

```csharp
public sealed class Repository<T>
    where T : class
{
    private readonly List<T> _items = [];

    public void Add(T item) => _items.Add(item);
}
```

**Extension Methods and Extension Members**

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

## Collections & LINQ

**Arrays, Lists, and Collection Expressions**

```csharp
int[] fixedValues = [1, 2, 3];
List<int> values = [1, 2, 3];
values.Add(4);

ReadOnlySpan<int> span = [10, 20, 30];
```

**Dictionary, HashSet, and Equality**

```csharp
var counts = new Dictionary<string, int>(
    StringComparer.OrdinalIgnoreCase);

counts["rust"] = 2;

var tags = new HashSet<string> { "csharp", "dotnet" };
```

**`IEnumerable<T>` and `yield`**

```csharp
static IEnumerable<int> EvenNumbers(int max)
{
    for (int i = 0; i <= max; i += 2)
    {
        yield return i;
    }
}
```

**LINQ Querying and Deferred Execution**

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

**Tuples and Deconstruction**

```csharp
static (int Min, int Max) Bounds(IEnumerable<int> values)
{
    return (values.Min(), values.Max());
}

var (min, max) = Bounds([3, 8, 2]);
```

## Errors & Resource Lifetimes

**Exceptions, `try`, `catch`, and `finally`**

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

**`IDisposable` and `using`**

```csharp
using var stream = File.OpenRead(path);
using var reader = new StreamReader(stream);

string text = reader.ReadToEnd();
```

**`IAsyncDisposable` and `await using`**

```csharp
await using var connection =
    await OpenConnectionAsync(cancellationToken);

await connection.SendAsync(data, cancellationToken);
```

**Custom Exceptions and Error Contracts**

```csharp
public sealed class InvalidOrderException : Exception
{
    public InvalidOrderException(string message)
        : base(message) { }
}
```

## Async & Concurrency

**`Task`, `async`, and `await`**

```csharp
static async Task<string> LoadAsync(
    HttpClient client,
    string url,
    CancellationToken token)
{
    return await client.GetStringAsync(url, token);
}
```

**Task Composition and Concurrency**

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

**Async Streams with `IAsyncEnumerable<T>`**

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

**Threads, Locks, and Concurrent Collections**

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

## Runtime & Performance

**Garbage Collection and Object Lifetimes**

```csharp
byte[] buffer = new byte[4096];

// The GC reclaims managed memory once it is unreachable.
UseBuffer(buffer);
```

**`Span<T>`, `Memory<T>`, and Allocation-aware Code**

```csharp
static int CountCommas(ReadOnlySpan<char> text)
{
    int count = 0;
    foreach (char c in text)
        if (c == ',') count++;
    return count;
}
```

**`ref struct`, `stackalloc`, and By-ref Safety**

```csharp
Span<int> values = stackalloc int[4];
values[0] = 10;

ref int first = ref values[0];
first = 20;
```

**Unsafe Code and Native Interop**

```csharp
unsafe
{
    int value = 42;
    int* pointer = &value;
    Console.WriteLine(*pointer);
}
```

## Reflection & Metadata

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

**Reflection and Type Metadata**

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

## Standard Library & Data

**File and Stream I/O**

```csharp
await using FileStream stream = File.OpenRead(path);
using var reader = new StreamReader(stream);

string text = await reader.ReadToEndAsync();
```

**JSON Serialization**

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};

string json = JsonSerializer.Serialize(user, options);
User? copy = JsonSerializer.Deserialize<User>(json, options);
```

**`HttpClient` and Network Requests**

```csharp
using var request = new HttpRequestMessage(
    HttpMethod.Get,
    new UriBuilder("https", "example.test", -1, "/api/users").Uri);

using HttpResponseMessage response =
    await client.SendAsync(request, cancellationToken);

response.EnsureSuccessStatusCode();
```

**Date, Time, and Time Zones**

```csharp
DateTimeOffset now = DateTimeOffset.UtcNow;
TimeZoneInfo zone = TimeZoneInfo.FindSystemTimeZoneById(
    "America/Los_Angeles");

DateTimeOffset local = TimeZoneInfo.ConvertTime(now, zone);
```

**Regular Expressions**

```csharp
var match = Regex.Match(
    "user-42",
    @"^user-(\d+)$");

if (match.Success)
    Console.WriteLine(match.Groups[1].Value);
```

## Packages, Testing & Production

**NuGet and Package References**

```xml
<ItemGroup>
  <PackageReference
      Include="Example.Library"
      Version="4.2.0" />
</ItemGroup>
```

**Unit Testing and Testable Design**

```csharp
[Fact]
public void Add_sums_two_values()
{
    var calculator = new Calculator();

    int result = calculator.Add(2, 3);

    Assert.Equal(5, result);
}
```

**Analyzers, Formatting, and Nullability Warnings**

```xml
<PropertyGroup>
  <Nullable>enable</Nullable>
  <TreatWarningsAsErrors>true</TreatWarningsAsErrors>
</PropertyGroup>
```

**Debugging, Profiling, and Diagnostics**

```csharp
using var activity = new Activity("process-order");
activity.Start();

ProcessOrder(order);

activity.Stop();
```
