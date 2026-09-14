# I/O de Archivos y Streams

`System.IO` ofrece paths, files, directories, streams, readers y writers. Los métodos de conveniencia funcionan bien para datos bounded; los streams son mejores para contenido grande o incremental sin cargar todo en memoria.

```csharp
await using FileStream stream = File.OpenRead(path);
using var reader = new StreamReader(stream);

string text = await reader.ReadToEndAsync();
```

Modela ownership y fallos: los archivos pueden desaparecer, los permisos cambiar y procesos externos modificar el filesystem. Usa async I/O cuando la aplicación se beneficie de esperas no bloqueantes.
