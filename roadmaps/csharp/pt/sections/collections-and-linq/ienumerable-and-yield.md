# `IEnumerable<T>` e `yield`

`IEnumerable<T>` é a abstração central de sequência síncrona. Um iterator method com `yield return` permite ao compilador gerar state machine que produz valores lazy conforme o consumer pede.

```csharp
static IEnumerable<int> EvenNumbers(int max)
{
    for (int i = 0; i <= max; i += 2)
    {
        yield return i;
    }
}
```

Laziness significa que o body pode não rodar ao criar a sequência, apenas na enumeração. Tenha cuidado com exceptions, trabalho caro, contexts de banco e estado capturado cujo lifetime dura até a enumeração terminar.
