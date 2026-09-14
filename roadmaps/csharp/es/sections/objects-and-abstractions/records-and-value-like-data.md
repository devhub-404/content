# Records y Datos Value-like

Las record classes y record structs ofrecen sintaxis concisa para tipos orientados a datos con igualdad por valor, impresión y non-destructive mutation mediante `with`. Los positional records también generan properties y deconstruction.

```csharp
public record User(string Name, string Email);

var a = new User("Mina", "m@example.com");
var b = a with { Email = "new@example.com" };

Console.WriteLine(a == b);
```

Usa records cuando la identidad sea principalmente el contenido, no la identidad del objeto y mutation intensa. Members mutables dentro de un record pueden volver sorprendente la value equality.
