# Delegates, Lambdas, and Events

A delegate type describes an invocable method signature. Lambdas create delegate-compatible functions or expression trees depending on context, and events expose controlled subscription around delegate invocation. Built-in `Action` and `Func` cover many ordinary callback signatures.

```csharp
Func<int, int> square = x => x * x;

button.Clicked += (_, args) =>
{
    Console.WriteLine(args.Message);
};
```

Callbacks can capture surrounding variables, which affects lifetime and allocations. Events also create lifetime relationships between publisher and subscriber, so long-lived publishers can keep subscribers alive unless subscriptions are removed or designed carefully.
