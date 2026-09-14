# I/O de Arquivos e Streams

`System.IO` fornece paths, files, directories, streams, readers e writers. Métodos convenientes funcionam bem para dados bounded; streams são melhores para conteúdo grande ou incremental sem carregar tudo em memória.

```csharp
await using FileStream stream = File.OpenRead(path);
using var reader = new StreamReader(stream);

string text = await reader.ReadToEndAsync();
```

Modele ownership e falhas: arquivos podem desaparecer, permissions mudar e processos externos modificar o filesystem. Use async I/O quando a aplicação se beneficia de waits não bloqueantes.
