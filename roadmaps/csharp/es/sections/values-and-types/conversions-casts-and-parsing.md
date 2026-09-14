# Conversiones, Casts y Parsing

C# distingue conversiones implícitas consideradas seguras de conversiones explícitas que requieren cast. El narrowing numérico puede perder información y `checked` puede convertir overflow integral en exception. Parsear texto es una operación distinta de hacer cast.

```csharp
int count = 42;
long wide = count;           // implicit
int narrow = checked((int)wide);

if (int.TryParse("123", out int value))
{
    Console.WriteLine(value);
}
```

En fronteras externas prefiere `TryParse`, validación o APIs explícitas frente a exceptions para input inválido normal. Un cast debe expresar una relación o política real, no solo silenciar al compilador.
