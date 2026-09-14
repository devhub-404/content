# Variables, `const`, and Type Inference

Local variables can use explicit types or `var`, which asks the compiler to infer one static type from the initializer. `var` is not dynamic typing: the inferred type is fixed after compilation. `const` values are compile-time constants restricted to types and expressions that the language can represent as constants.

```csharp
var message = "hello";
int count = 3;
const int MaxRetries = 5;

message = message.ToUpperInvariant();
```

Use `var` when the type is obvious from the right side or verbose without adding meaning. Prefer an explicit type when it communicates an important unit, abstraction, or conversion. Use `const` for true compile-time constants and `static readonly` for values initialized at runtime.
