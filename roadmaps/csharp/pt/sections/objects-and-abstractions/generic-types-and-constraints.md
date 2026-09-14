# Tipos Genéricos e Constraints

Generics preservam relações estáticas de tipo sem cast ou `object`. Constraints como `class`, `struct`, `notnull`, base types, interfaces, constructor requirements e generic math dizem quais operações são válidas.

```csharp
public sealed class Repository<T>
    where T : class
{
    private readonly List<T> _items = [];

    public void Add(T item) => _items.Add(item);
}
```

Adicione apenas constraints realmente necessárias. Um generic parameter que aparece uma vez e não preserva relação pode não trazer valor. Generics são mais úteis quando conectam inputs, outputs e valores armazenados.
