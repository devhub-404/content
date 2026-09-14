# Entrada do Programa e Top-level Statements

Uma aplicação console pode usar top-level statements sem declarar `Program.Main`. O compilador ainda cria o entry point, e argumentos de linha de comando ficam disponíveis pela variável implícita `args`. `static void Main` ou `static Task Main` continuam válidos.

```csharp
string name = args.Length > 0 ? args[0] : "world";
Console.WriteLine($"Hello, {name}");
```

Top-level statements são ótimos para programas pequenos e exemplos, mas aplicações maiores ainda se beneficiam de tipos e métodos normais. Não coloque toda a aplicação em um único arquivo só porque a sintaxe permite.
