# Delegates, Lambdas y Events

Un delegate describe una firma invocable. Las lambdas crean funciones compatibles con delegates o expression trees según contexto, y los events controlan subscriptions alrededor de la invocación. `Action` y `Func` cubren muchos callbacks normales.

```csharp
Func<int, int> square = x => x * x;

button.Clicked += (_, args) =>
{
    Console.WriteLine(args.Message);
};
```

Los callbacks pueden capturar variables, afectando lifetime y allocations. Los events también crean relaciones de lifetime entre publisher y subscriber, por lo que publishers long-lived pueden mantener subscribers vivos si no se elimina la suscripción.
