# `IDisposable` e `using`

Garbage collection gerencia memória, mas file handles, sockets, conexões, buffers nativos e locks precisam release determinístico. `IDisposable` descreve cleanup síncrono e `using` garante `Dispose` na saída do scope.

```csharp
using var stream = File.OpenRead(path);
using var reader = new StreamReader(stream);

string text = reader.ReadToEnd();
```

Mantenha aquisição e ownership no menor scope prático. Uma using declaration só dispõe no fim do scope ao redor, então método enorme pode manter recurso caro vivo por tempo demais.
