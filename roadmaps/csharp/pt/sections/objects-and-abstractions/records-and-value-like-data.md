# Records e Dados Value-like

Record classes e record structs fornecem sintaxe concisa para tipos data-oriented com igualdade por valor, impressão e non-destructive mutation via `with`. Positional records também geram properties e deconstruction.

```csharp
public record User(string Name, string Email);

var a = new User("Mina", "m@example.com");
var b = a with { Email = "new@example.com" };

Console.WriteLine(a == b);
```

Use records quando identidade é principalmente o conteúdo, não identidade de objeto e mutation intensa. Members mutáveis dentro do record podem tornar value equality surpreendente.
