# Tipos Genéricos y Constraints

Los generics conservan relaciones estáticas de tipo sin cast ni `object`. Constraints como `class`, `struct`, `notnull`, base types, interfaces, constructor requirements y generic math indican qué operaciones son válidas.

```csharp
public sealed class Repository<T>
    where T : class
{
    private readonly List<T> _items = [];

    public void Add(T item) => _items.Add(item);
}
```

Añade solo constraints realmente necesarias. Un generic parameter que aparece una vez y no conserva relación puede no aportar valor. Los generics son más útiles cuando conectan inputs, outputs y valores almacenados.
