# Conversões, Casts e Parsing

C# distingue conversões implícitas consideradas seguras de conversões explícitas que exigem cast. Narrowing numérico pode perder informação, e `checked` pode transformar overflow integral em exception. Parsing de texto é uma operação diferente de cast.

```csharp
int count = 42;
long wide = count;           // implicit
int narrow = checked((int)wide);

if (int.TryParse("123", out int value))
{
    Console.WriteLine(value);
}
```

Em fronteiras externas prefira `TryParse`, validação ou APIs explícitas em vez de exceptions para input inválido comum. Cast deve expressar uma relação ou política real, não apenas silenciar o compilador.
