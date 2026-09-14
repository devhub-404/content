# File and Stream I/O

`System.IO` provides paths, files, directories, streams, readers, and writers. Convenience methods are excellent for bounded data, while streams are better for large or incremental content because they avoid loading everything into memory at once.

```csharp
await using FileStream stream = File.OpenRead(path);
using var reader = new StreamReader(stream);

string text = await reader.ReadToEndAsync();
```

Always model resource ownership and failure: files may disappear, permissions can change, partial reads can occur, and external processes can modify the filesystem. Use async I/O when the surrounding application benefits from nonblocking waits.
