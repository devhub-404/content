# `IDisposable` y `using`

Garbage collection gestiona memoria, pero file handles, sockets, conexiones, buffers nativos y locks necesitan liberación determinista. `IDisposable` describe cleanup síncrono y `using` garantiza `Dispose` al salir del scope.

```csharp
using var stream = File.OpenRead(path);
using var reader = new StreamReader(stream);

string text = reader.ReadToEnd();
```

Mantén adquisición y ownership en el scope práctico más pequeño. Una using declaration solo dispone al final del scope envolvente, así que un método enorme puede mantener un recurso costoso vivo demasiado tiempo.
