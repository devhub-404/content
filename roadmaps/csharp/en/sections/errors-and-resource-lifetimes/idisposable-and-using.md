# `IDisposable` and `using`

Garbage collection manages memory, but resources such as file handles, sockets, database connections, native buffers, and locks often need deterministic release. `IDisposable` describes synchronous cleanup, and `using` ensures `Dispose` runs when control leaves the scope.

```csharp
using var stream = File.OpenRead(path);
using var reader = new StreamReader(stream);

string text = reader.ReadToEnd();
```

Place acquisition and ownership in the smallest practical scope. A `using` declaration disposes at the end of the surrounding scope, so a very large method can accidentally keep an expensive resource alive longer than necessary.
