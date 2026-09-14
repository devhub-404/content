# Loops e Enumeração

C# fornece `for`, `foreach`, `while` e `do`. `foreach` consome o enumeration pattern e é a escolha normal quando você precisa dos elementos, não do índice. `break`, `continue` e `return` controlam a saída em níveis diferentes.

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

Use indexação quando a posição importa ou a coleção oferece acesso indexado eficiente. Não altere estruturalmente uma coleção enquanto seu enumerator comum está ativo salvo quando o contrato permite.
