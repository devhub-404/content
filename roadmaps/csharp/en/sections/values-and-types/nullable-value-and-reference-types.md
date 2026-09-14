# Nullable Value and Reference Types

Value types use `T?` to represent either a value or null through `Nullable<T>`. Nullable reference types are primarily a compiler analysis feature: annotations such as `string?` describe whether null is expected and enable warnings when code may dereference a missing reference.

```csharp
int? count = null;
string? nickname = null;

string display = nickname ?? "anonymous";
int value = count.GetValueOrDefault();
```

Nullable annotations improve contracts but do not make runtime data trustworthy. Validate deserialized, database, reflection, and interop inputs as needed. Prefer `?`, `??`, pattern matching, and explicit guards over scattering the null-forgiving `!` operator through code.
