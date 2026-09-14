# `IEnumerable<T>` y `yield`

`IEnumerable<T>` es la abstracción central de secuencia síncrona. Un iterator method con `yield return` permite al compilador generar una state machine que produce valores lazy conforme el consumer los pide.

```csharp
static IEnumerable<int> EvenNumbers(int max)
{
    for (int i = 0; i <= max; i += 2)
    {
        yield return i;
    }
}
```

La laziness significa que el body puede no ejecutarse al crear la secuencia, sino durante la enumeración. Ten cuidado con exceptions, trabajo costoso, contextos de base de datos y estado capturado cuyo lifetime dura hasta terminar la enumeración.
