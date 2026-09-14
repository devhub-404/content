# Delegates, Lambdas e Events

Delegate descreve assinatura invocável. Lambdas criam funções compatíveis com delegates ou expression trees conforme contexto, e events controlam subscriptions ao redor de delegate invocation. `Action` e `Func` cobrem muitos callbacks comuns.

```csharp
Func<int, int> square = x => x * x;

button.Clicked += (_, args) =>
{
    Console.WriteLine(args.Message);
};
```

Callbacks podem capturar variáveis, afetando lifetime e allocations. Events também criam relação de lifetime entre publisher e subscriber, então publishers long-lived podem manter subscribers vivos se a inscrição não for removida.
