# Arrays, Lists e Collection Expressions

Arrays possuem length fixo e acesso indexado eficiente, enquanto `List<T>` é a collection growable padrão. Collection expressions oferecem sintaxe compacta para arrays, lists, spans e destinos compatíveis.

```csharp
int[] fixedValues = [1, 2, 3];
List<int> values = [1, 2, 3];
values.Add(4);

ReadOnlySpan<int> span = [10, 20, 30];
```

Escolha array quando storage contíguo de tamanho fixo é o contrato e list para sequências dinâmicas comuns. Exponha `IReadOnlyList<T>` ou `IEnumerable<T>` quando callers não precisam de mutation.
