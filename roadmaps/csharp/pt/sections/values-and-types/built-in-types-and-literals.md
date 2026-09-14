# Tipos Built-in e Literals

C# possui aliases built-in para tipos integrais, floating-point, decimal, Boolean, char, string, object e outros tipos .NET. Literals numéricos suportam sufixos, separators, hexadecimal e binário. `decimal` é orientado a base 10 e costuma ser adequado para valores financeiros.

```csharp
int count = 42;
long population = 8_000_000_000L;
double ratio = 0.75;
decimal price = 19.99m;
bool ready = true;
char letter = 'A';
```

Escolha tipo pelo domínio e contrato da API, não por hábito. `int` é o inteiro geral mais comum, mas IDs, timestamps, dinheiro e campos de protocolo podem merecer tipos diferentes ou wrappers de domínio.
