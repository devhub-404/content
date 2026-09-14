# Loops y Enumeración

C# ofrece `for`, `foreach`, `while` y `do`. `foreach` consume el enumeration pattern y es la opción normal cuando necesitas elementos, no índices. `break`, `continue` y `return` controlan la salida a distintos niveles.

```csharp
foreach (var item in items)
{
    Console.WriteLine(item);
}

for (int i = 0; i < items.Count; i++)
{
    Console.WriteLine($"{i}: {items[i]}");
}
```

Usa indexación cuando importe la posición o la colección ofrezca acceso indexado eficiente. No modifiques estructuralmente una colección mientras su enumerator normal esté activo salvo que el contrato lo permita.
