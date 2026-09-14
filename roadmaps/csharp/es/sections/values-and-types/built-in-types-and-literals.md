# Tipos Built-in y Literals

C# tiene aliases built-in para tipos enteros, floating-point, decimal, Boolean, char, string, object y otros tipos .NET. Los literals numéricos soportan sufijos, separadores, hexadecimal y binario. `decimal` está orientado a base 10 y suele ser apropiado para cantidades financieras.

```csharp
int count = 42;
long population = 8_000_000_000L;
double ratio = 0.75;
decimal price = 19.99m;
bool ready = true;
char letter = 'A';
```

Elige el tipo según el dominio y el contrato de la API, no por costumbre. `int` es el entero general habitual, pero IDs, timestamps, dinero y campos de protocolo pueden merecer otros tipos o wrappers de dominio.
